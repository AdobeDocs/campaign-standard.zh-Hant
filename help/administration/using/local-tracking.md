---
solution: Campaign Standard
product: campaign
title: 實施推播追蹤
description: 本檔案可讓您確保推播通知追蹤已在iOS和Android上正確實作。
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
feature: 例項設定
role: 管理員
level: 經驗豐富
translation-type: tm+mt
source-git-commit: a7a1aa2841410674597264927325c073fef4ce26
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 0%

---


# 實作本機追蹤{#local-tracking}

## 關於本機追蹤{#about-local-tracking}

在本頁中，瞭解如何確保已正確實施本機通知追蹤。 請注意，這表示本機通知已設定。

本機通知追蹤可分割為三種類型：

* **當地印象** -當本地通知已傳送至裝置且位於通知中心，但完全未觸及時。在大多數情況下，曝光數位應與傳送的數字相同，但是與傳送的數字不相同。 它可確保裝置收到訊息並將該資訊傳回伺服器。

* **本機點按** -當本機通知已傳送至裝置且使用者已點按通知時。使用者要麼想檢視通知（此通知將會移至本機開啟追蹤），要麼想要關閉通知。

* **本機開啟** -當本機通知已傳送至裝置，且使用者已按一下通知，導致應用程式開啟時。這類似於本機點按，除非通知已關閉，否則不會觸發本機開啟。

若要實作Adobe Campaign Standard的追蹤，行動應用程式必須在應用程式中加入Mobile SDK。 這些SDK可在[!DNL Adobe Mobile Services]中使用。

若要傳送追蹤資訊，需要傳送三個變數：2是從Adobe Campaign收到的資料的一部分，2則是動作變數，決定是曝光、點按或開啟。

| 變數 | 值 |
| :-: | :-: |
| deliveryId | `deliveryId` 從傳入資料(類似於使用的推 `_dld` 送追蹤) |
| broadlogId | `broadlogId` 從傳入資料(類似於使用的推 `_mld` 送追蹤) |
| 動作 | 「1」代表開啟，「2」代表點按，「7」代表印象 |

## 實施本機印象追蹤{#implement-local-impression-tracking}

Adobe Experience Platform行動SDK將自動傳送Android和iOS的曝光事件，毋需額外設定。

## 實作點按追蹤{#implementing-click-tracking}

若是點按追蹤，在呼叫`collectMessageInfo()`或`trackAction()`函式時，您需要傳送值&quot;2&quot;以執行動作。

### 對於Android {#implement-click-tracking-android}

若要追蹤點按，需要處理兩種情況：

* 使用者會看到通知，但會將其清除。

   若要在解雇情形時追蹤點按，請將廣播接收器`NotificationDismissalHandler`新增至應用程式模組的AndroidManifest檔案。

   ```
   <receiver
   android:name="com.adobe.marketing.mobile.NotificationDismissalHandler">
   </receiver>
   ```

* 使用者會看到通知並點按，這會轉為開啟的追蹤。

   此藍本應產生點按和開啟。 追蹤此點按次數是追蹤開啟次數所需實施的一部分。 請參閱[實作開放追蹤](#implement-open-tracking)。

### 對於iOS {#implement-click-tracking-ios}

若要傳送點按追蹤資訊，您必須新增下列項目：

```
class NotificationDelegate: NSObject, UNUserNotificationCenterDelegate {

   func userNotificationCenter(_ center: UNUserNotificationCenter, didReceive response: UNNotificationResponse, withCompletionHandler completionHandler: @escaping () -> Void) {
        let userInfo = response.notification.request.content.userInfo
        switch response.actionIdentifier {
        case UNNotificationDismissActionIdentifier:
            print("Dismiss Action")
            let deliveryId = userInfo["deliveryId"] as? String
            let broadlogId = userInfo["broadlogId"] as? String
            if (deliveryId != nil && broadlogId != nil) {
                
                //If you are using ACPCore v2.3.0 or later, use the next line.
                
                ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
                
                //Else comment out the above line and uncomment the line below
                
                // ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
            }
        default:
            
            ////MORE CODE
        }
        completionHandler()
    }
}
```

## 實作開放追蹤{#implement-open-tracking}

您必須傳送「1」和「2」，因為使用者必須按一下通知才能開啟應用程式。 如果應用程式未透過本機通知啟動／開啟，則不會發生追蹤事件。

### 對於Android {#implement-open-tracking-android}

若要追蹤開放，我們需要建立意圖。 目的物件可讓Android OS在完成特定動作時呼叫您的方法，在此例中，按一下通知以開啟應用程式。

此程式碼是以點按印象追蹤的實施為基礎。 在設定意圖後，您現在需要將追蹤資訊傳回Adobe Campaign。 在這種情況下，觸發通知的Android檢視([!DNL Activity])將會因使用者點按而開啟或帶入前景。 [!DNL Activity]中的意圖對象包含可用於跟蹤開啟的通知資料。

MainActivity.java(extends [!DNL Activity])

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

        //Opened based on the notification, you need to get the tracking that was passed on.

        Map<String, String> notificationData = (Map<String, Object>)data.getSerializableExtra("NOTIFICATION_USER_INFO");
        String deliveryId = (String)notificationData.get("deliveryId");
        String messageId = (String)notificationData.get("broadlogId");

        if (deliveryId != null && messageId != null) {
            HashMap<String, String> contextData = new HashMap<>();
            contextData.put("deliveryId", deliveryId);
            contextData.put("broadlogId", messageId);
 
            //Send click tracking since the user did click on the notification

            contextData.put("action", "2");

            //If you are using ACPCore v1.4.0 or later, use the next line.
    
            MobileCore.collectMessageInfo(contextData);

            //Else comment out the above line and uncomment the line below

            // MobileCore.trackAction("tracking", contextData);
 
            //Send open tracking since the user opened the app

            contextData.put("action", "1");

            //If you are using  ACPCore v1.4.0 or later, use the next line.

            MobileCore.collectMessageInfo(contextData);

            //Else comment out the above line and uncomment the line below

            // MobileCore.trackAction("tracking", contextData);
        }
    }
}
```

### 對於iOS {#implement-open-tracking-ios}

```
import os.log
import Foundation
import UserNotifications
import UserNotificationsUI
import ACPCore
 
class NotificationDelegate: NSObject, UNUserNotificationCenterDelegate {
 
    //Called when user clicks the local notification or also called from willPresent()

    func userNotificationCenter(_ center: UNUserNotificationCenter, didReceive response: UNNotificationResponse, withCompletionHandler completionHandler: @escaping () -> Void) {
 
        let userInfo = response.notification.request.content.userInfo
        os_log("App push data %{public}@, in userNotificationCenter:didReceive()", type: .debug, userInfo)
        switch response.actionIdentifier {
        case UNNotificationDismissActionIdentifier:

            //This is to handle the Dismiss action

            let deliveryId = userInfo["deliveryId"] as? String
            let broadlogId = userInfo["broadlogId"] as? String
            if (deliveryId != nil && broadlogId != nil) {

                //If you are using ACPCore v2.3.0 or later, use the next line.

                ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])

                //Else comment out the above line and uncomment the line below

                // ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
            }
        default:
            //This is to handle the tracking when the app opens
            let deliveryId = userInfo["deliveryId"] as? String
            let broadlogId = userInfo["broadlogId"] as? String
            if (deliveryId != nil && broadlogId != nil) {

               //If you are using ACPCore v2.3.0 or later, use the next line.

               ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
               ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"1"])

               //Else comment out the above line and uncomment the line below

               // ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
               // ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"1"])
            }
        }
        completionHandler()
    }
}
```
