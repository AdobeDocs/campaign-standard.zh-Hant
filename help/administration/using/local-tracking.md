---
solution: Campaign Standard
product: campaign
title: 實施推播追蹤
description: 本檔案可讓您確保推播通知追蹤已在iOS和Android上正確實作。
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '726'
ht-degree: 0%

---


# 實作本機追蹤 {#local-tracking}

## 關於本機追蹤 {#about-local-tracking}

在本頁中，瞭解如何確保已正確實施本機通知追蹤。 請注意，這表示本機通知已設定。

本機通知追蹤可分割為三種類型：

* **當地印象** -當本地通知已傳送至裝置且位於通知中心，但完全未觸及時。 在大多數情況下，曝光數位應與傳送的數字相同，但是與傳送的數字不相同。 它可確保裝置收到訊息並將該資訊傳回伺服器。

* **本機點按** -當本機通知已傳送至裝置且使用者已點按裝置時。 使用者要麼想檢視通知（此通知將會移至本機開啟追蹤），要麼想要關閉通知。

* **本機開啟** -當傳送本機通知給裝置且使用者按一下通知導致應用程式開啟時。 這類似於本機點按，除非通知已關閉，否則不會觸發本機開啟。

若要實作Adobe Campaign Standard的追蹤，行動應用程式必須在應用程式中加入Mobile SDK。 這些SDK可在中取 [!DNL Adobe Mobile Services]得。

若要傳送追蹤資訊，需要傳送三個變數：兩者是從Adobe Campaign收到的資料的一部分，另一則是動作變數，決定是曝光、點按或開啟。

| 變數 | 值 |
| :-: | :-: |
| deliveryId | 來自傳入資料的&quot;deliveryId&quot;（類似於使用&quot;_dld&quot;的推送追蹤） |
| broadlogId | 來自傳入資料的&quot;broadlogId&quot;（類似於使用&quot;_mld&quot;的推播追蹤） |
| 動作 | 「1」代表開啟，「2」代表點按，「7」代表印象 |

## 實作本機印象追蹤 {#implement-local-impression-tracking}

若是印象追蹤，在呼叫collectMessageInfo()或trackAction()函式時，您必須傳送值&quot;7&quot;以取得動作。

### 適用於Android {#implement-local-impression-tracking-android}

Adobe Experience Platform Mobile SDK會在觸發本機通知時啟動印象追蹤。

### 適用於iOS {#implement-local-impression-tracking-ios}

若要說明如何實作曝光追蹤，我們需要瞭解應用程式的三種狀態：

* **前景**:當應用程式目前處於作用中，且在前景的螢幕上時。

* **背景**:當應用程式未在螢幕上，但程式也未關閉時。 當連按兩下「首頁」按鈕時，通常會在背景顯示所有應用程式。

* **關閉／關閉**:當應用程式的程式被終止時。 如果應用程式已關閉，Apple會在應用程式重新啟動之前呼叫它。 這表示您永遠無法真正知道iOS上的通知是何時收到的。

為了讓曝光追蹤在應用程式背景時仍能運作，我們需要傳送「可用內容」讓應用程式知道必須進行追蹤。

Adobe Experience Platform Mobile SDK會在觸發本機通知時啟動印象追蹤。

>[!CAUTION]
>
>iOS曝光追蹤不準確，因此不應進行可靠的檢視。

## 實作點按追蹤 {#implementing-click-tracking}

若是點按追蹤，在呼叫collectMessageInfo()或trackAction()函式時，您必須傳送動作值&quot;2&quot;。

### 適用於Android {#implement-click-tracking-android}

若要追蹤點按，需要處理兩種情況：

* 使用者會看到通知，但會將其清除。

* 使用者會看到通知並點按，這會轉為開啟的追蹤。

Adobe Experience Platform Mobile SDK會追蹤第一個點按案例。

### 適用於iOS {#implement-click-tracking-ios}

```
// AppDelegate.swift
...
import os.log
import UserNotifications
...
  
func registerForPushNotifications() {
        let center = UNUserNotificationCenter.current()
        center.delegate = notificationDelegate
        //Here we are creating a new Category that allows us to handle Dismiss Actions
        let defaultCategory = UNNotificationCategory(identifier: "DEFAULT", actions: [], intentIdentifiers: [], options: .customDismissAction)
        //Add it to our array of Category, in this case we only have one
        center.setNotificationCategories([defaultCategory])
        center.requestAuthorization(options: [.alert, .sound, .badge]) {
            (granted, error) in
            os_log("Permission granted: %{public}@", type:. debug, granted.description)
            if error != nil {
                return
            }
            if granted {
                os_log("Notifications allowed", type: .debug)
            }
            else {
                os_log("Notifications denied", type: .debug)
            }
  
            // 2. Attempt registration for remote notifications on the main thread
            DispatchQueue.main.async {
                UIApplication.shared.registerForRemoteNotifications()
            }
        }
    }
```

然後，若要處理關閉並傳送追蹤資訊，您必須新增下列項目：

```
func userNotificationCenter(_ center: UNUserNotificationCenter, didReceive response: UNNotificationResponse, withCompletionHandler completionHandler: @escaping () -> Void) {
        let userInfo = response.notification.request.content.userInfo
        switch response.actionIdentifier {
        case UNNotificationDismissActionIdentifier:
            print("Dismiss Action")
            let deliveryId = userInfo["deliveryId"] as? String
            let broadlogId = userInfo["broadlogId"] as? String
            if (deliveryId != nil && broadlogId != nil) {
                // If you're using  ACPCore v2.3.0 or later, use the line below.
                ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
                // Else comment out the above line and uncomment the line below
                // ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
            }
        default:
            ////MORE CODE
        }
        completionHandler()
    }
```

## 實作開放追蹤 {#implement-open-tracking}

您必須傳送「1」和「2」，因為使用者必須按一下通知才能開啟應用程式。 如果應用程式未透過本機通知啟動／開啟，則不會發生追蹤事件。

### 適用於Android {#implement-open-tracking-android}

若要追蹤開放，我們需要建立意圖。 目的物件可讓Android OS在完成特定動作時呼叫您的方法，在此例中，按一下通知以開啟應用程式。

此程式碼是以點按印象追蹤的實施為基礎。 在設定意圖後，您現在需要將追蹤資訊傳回至Adobe Campaign。 在這種情況下，觸發通知的Android檢視[!DNL Activity]()會因使用者點按而開啟或帶至前景。 中的目的對 [!DNL Activity] 像包含可用於跟蹤開啟的通知資料。

MainActivity.java(延伸 [!DNL Activity])

```
@Override
protected void onResume() {
    super.onResume();
    handleTracking();
}
  
  
private void handleTracking() {
    //Check to see if this view was opened based on a notification
    Intent intent = getIntent();
    Bundle data = intent.getExtras();
  
    if (data != null) {
        //Looks it was opened based on the notification, lets get the tracking we passed on.
        Map<String, String> notificationData = (Map<String, Object>)data.getSerializableExtra("NOTIFICATION_USER_INFO");
        String deliveryId = (String)notificationData.get("deliveryId");
        String messageId = (String)notificationData.get("broadlogId");
  
  
  
        if (deliveryId != null && messageId != null) {
            HashMap<String, String> contextData = new HashMap<>();
            contextData.put("deliveryId", deliveryId);
            contextData.put("broadlogId", messageId);
  
            //Send Click Tracking since the user did click on the notification
            contextData.put("action", "2");
            // If you're using  ACPCore v1.4.0 or later, use the next line.
            MobileCore.collectMessageInfo(contextData);
            // Else comment out the above line and uncomment the line below
            // MobileCore.trackAction("tracking", contextData);
  
            //Send Open Tracking since the user opened the app
            contextData.put("action", "1");
            // If you're using  ACPCore v1.4.0 or later, use the next line.
            MobileCore.collectMessageInfo(contextData);
            // Else comment out the above line and uncomment the line below
            // MobileCore.trackAction("tracking", contextData);
        }
    }
}
```

### 適用於iOS {#implement-open-tracking-ios}

```
import os.log
import Foundation
import UserNotifications
import UserNotificationsUI
import ACPCore
  
class NotificationDelegate: NSObject, UNUserNotificationCenterDelegate {
  
    // Called when user clicks the local notification or also called from willPresent()
    func userNotificationCenter(_ center: UNUserNotificationCenter, didReceive response: UNNotificationResponse, withCompletionHandler completionHandler: @escaping () -> Void) {
  
        let userInfo = response.notification.request.content.userInfo
        os_log("App push data %{public}@, in userNotificationCenter:didReceive()", type: .debug, userInfo)
        switch response.actionIdentifier {
        case UNNotificationDismissActionIdentifier:
            //This is to handle the Dismiss Action
            let deliveryId = userInfo["deliveryId"] as? String
            let broadlogId = userInfo["broadlogId"] as? String
            if (deliveryId != nil && broadlogId != nil) {
            // If you're using  ACPCore v2.3.0 or later, use the line below.
                ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
            // Else comment out the above line and uncomment the line below
            // ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
            }
        default:
            //This is to handle the tracking when the app opens
            let deliveryId = userInfo["deliveryId"] as? String
            let broadlogId = userInfo["broadlogId"] as? String
            if (deliveryId != nil && broadlogId != nil) {
               // If you're using  ACPCore v2.3.0 or later, use the line below.
               ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
               ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"1"])
               // Else comment out the above line and uncomment the line below
               // ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
               // ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"1"])
            }
        }
        completionHandler()
    }
}
```
