---
title: 實作本機追蹤
description: 瞭解如何確保在iOS和Android上正確實作推播通知追蹤
audience: channels
feature: Instance Settings
role: Admin
level: Experienced
exl-id: b983d0a3-c345-44d4-bc82-202bf6ed26ab
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '574'
ht-degree: 0%

---

# 實作本機追蹤 {#local-tracking}

## 關於本機追蹤 {#about-local-tracking}

在本頁面中，瞭解如何確保本機通知追蹤已正確實作。 請注意，這表示本機通知已設定。

本機通知追蹤可以分割成三種型別：

* **本機曝光次數** — 本機通知已傳送至裝置，且位於通知中心，但完全沒有接觸時。 在大多數情況下，如果不與遞送的數字相同，則曝光數應該類似。 這可確保裝置確實收到訊息，並將該資訊轉送回伺服器。

* **本機點按** — 本機通知已傳送至裝置，且使用者已點按通知時。 使用者想要檢視通知（接著會移至本機開啟追蹤）或關閉通知。

* **本機開啟** — 本機通知已傳送至裝置，且使用者已按一下通知導致應用程式開啟時。 這類似於本機點按，但如果通知已關閉，則不會觸發本機開啟。

若要實作Adobe Campaign Standard的追蹤，行動應用程式必須在應用程式中包含行動SDK。 這些SDK可在[!DNL Adobe Mobile Services]中使用。

若要傳送追蹤資訊，有三個變數必須傳送：兩個是從Adobe Campaign接收的資料的一部分，另一個是動作變數，可指定是曝光、點選或開啟。

| 變數 | 值 |
| :-: | :-: |
| deliveryId | 來自傳入資料的`deliveryId` （類似於使用`_dld`的推播追蹤） |
| broadlogId | 來自傳入資料的`broadlogId` （類似於使用`_mld`的推播追蹤） |
| 動作 | 「1」代表「開啟」，「2」代表「點選」，「7」代表「印象」 |

## 實作本機曝光追蹤 {#implement-local-impression-tracking}

Adobe Experience Platform Mobile SDK將自動傳送Android和iOS的曝光事件，無需任何其他設定。

## 實作點選追蹤 {#implementing-click-tracking}

針對點選追蹤，呼叫`collectMessageInfo()`或`trackAction()`函式時，您必須傳送值「2」才能執行動作。

### 適用於Android {#implement-click-tracking-android}

若要追蹤點按，必須實作兩種情況：

* 使用者看到通知但將其清除。

  若要追蹤在解除情況下發生的點按，請在應用程式模組的AndroidManifest檔案中新增廣播接收器`NotificationDismissalHandler`。

  ```
  <receiver
  android:name="com.adobe.marketing.mobile.NotificationDismissalHandler">
  </receiver>
  ```

* 使用者看到通知並按一下後，就會轉向開啟的追蹤。

  此情境應該會產生點按並開啟。 追蹤此點按將是追蹤開啟所需實施作業的一部分。 請參閱[實作開啟追蹤](#implement-open-tracking)。

### 適用於iOS {#implement-click-tracking-ios}

若要傳送點選追蹤資訊，您必須新增下列專案：

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

## 實作開啟追蹤 {#implement-open-tracking}

您必須傳送「1」和「2」，因為使用者必須按一下通知才能開啟應用程式。 如果未透過本機通知啟動/開啟應用程式，則不會發生追蹤事件。

### 適用於Android {#implement-open-tracking-android}

若要追蹤開啟，我們必須建立目的。 意圖物件可讓Android作業系統在完成某些動作時，呼叫您的方法，在此案例中是按一下通知以開啟應用程式。

此程式碼以點按曝光追蹤的實施為基礎。 在設定意圖後，您現在必須將追蹤資訊傳送回Adobe Campaign。 在此情況下，觸發通知的Android檢視([!DNL Activity])將會開啟或因使用者點按而進入前景。 [!DNL Activity]中的目的物件包含可用來追蹤開啟的通知資料。

MainActivity.java （延伸[!DNL Activity]）

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

        //Opened based on the notification, you must get the tracking that was passed on.

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

### 適用於iOS {#implement-open-tracking-ios}

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
