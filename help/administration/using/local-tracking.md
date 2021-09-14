---
title: 實施推送追蹤
description: 本檔案可讓您確保推播通知追蹤已在iOS和Android上正確實作。
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
feature: Instance Settings
role: Admin
level: Experienced
exl-id: b983d0a3-c345-44d4-bc82-202bf6ed26ab
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '577'
ht-degree: 0%

---

# 實作本機追蹤 {#local-tracking}

## 關於本機追蹤 {#about-local-tracking}

在本頁面中，了解如何確保已正確實作本機通知追蹤。 請注意，這表示本機通知已設定。

本機通知追蹤可分割為三種類型：

* **本機曝光次數**  — 將本機通知傳送至裝置，且位於通知中心，但完全未接觸時。在大多數情況下，曝光數數若與傳送的數字不同，則應類似。 它確保設備確實獲取消息並將該資訊轉發回伺服器。

* **本機點按**  — 將本機通知傳送至裝置，且使用者已點按通知時。使用者要麼想要檢視通知（這進而會移至本機開啟追蹤），要麼要關閉通知。

* **本機開啟**  — 將本機通知傳送至裝置，且使用者按一下通知而導致應用程式開啟時。這類似於本機點按，除非通知關閉時不會觸發本機開啟。

若要實作Adobe Campaign Standard的追蹤，行動應用程式必須將行動SDK納入應用程式中。 這些SDK可在[!DNL Adobe Mobile Services]中使用。

若要傳送追蹤資訊，需傳送三個變數：兩者是從Adobe Campaign收到資料的一部分，另一個是動作變數，會指定其為曝光、點按或開啟。

| 變數 | 值 |
| :-: | :-: |
| deliveryId | `deliveryId` 從傳入資料(類似於使用的推 `_dld` 送追蹤) |
| broadlogId | `broadlogId` 從傳入資料(類似於使用的推 `_mld` 送追蹤) |
| 動作 | 「1」代表開啟，「2」代表點按，「7」代表曝光 |

## 實作本機曝光追蹤 {#implement-local-impression-tracking}

Adobe Experience Platform Mobile SDK會自動傳送Android和iOS的曝光事件，而不需進行任何額外設定。

## 實作點擊追蹤 {#implementing-click-tracking}

若為點擊追蹤，呼叫`collectMessageInfo()`或`trackAction()`函式時，您需要傳送動作的值「2」。

### 適用於Android {#implement-click-tracking-android}

若要追蹤點按，需處理兩種情況：

* 使用者會看見通知，但將其清除。

   若要在解除案例時追蹤點擊，請在應用程式模組的AndroidManifest檔案中新增廣播接收器`NotificationDismissalHandler`。

   ```
   <receiver
   android:name="com.adobe.marketing.mobile.NotificationDismissalHandler">
   </receiver>
   ```

* 使用者看見通知並點按，這會轉為開啟追蹤。

   此情境應會產生一次點按，並開啟。 追蹤此點按將是追蹤開啟所需實施的一部分。 請參閱[實作開啟追蹤](#implement-open-tracking)。

### 適用於iOS {#implement-click-tracking-ios}

若要傳送點擊追蹤資訊，您需要新增下列項目：

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

## 實作開放追蹤 {#implement-open-tracking}

您必須傳送「1」和「2」，因為使用者必須按一下通知才能開啟應用程式。 如果應用程式未透過本機通知啟動/開啟，則不會發生追蹤事件。

### 適用於Android {#implement-open-tracking-android}

若要追蹤開啟，我們需要建立意圖。 目的物件可讓Android作業系統在完成某些動作時呼叫您的方法，在此例中是按一下通知以開啟應用程式。

此程式碼以點擊曝光追蹤的實作為基礎。 透過目的設定，您現在需要將追蹤資訊傳回Adobe Campaign。 在此情況下，會因使用者點按而開啟或帶入前景的觸發通知的Android檢視([!DNL Activity])。 [!DNL Activity]中的目的對象包含可用於追蹤開啟的通知資料。

MainActivity.java（延伸[!DNL Activity]）

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
