---
title: 實施推送追蹤
description: 瞭解如何確保推送通知跟蹤已在iOS和Android上正確實施
audience: channels
feature: Instance Settings
role: Admin
level: Experienced
exl-id: b983d0a3-c345-44d4-bc82-202bf6ed26ab
source-git-commit: bfba6b156d020e8d2656239e713d2d24625bda54
workflow-type: tm+mt
source-wordcount: '568'
ht-degree: 0%

---

# 實現本地跟蹤 {#local-tracking}

## 關於本地跟蹤 {#about-local-tracking}

在本頁中，瞭解如何確保正確實施本地通知跟蹤。 請注意，這意味著已配置了本地通知。

本地通知跟蹤可分為三種類型：

* **當地印象**  — 當本地通知已送達設備且位於通知中心，但完全未接觸時。 在大多數情況下，印數應與已交付的數字相同。 它確保設備確實收到消息並將該資訊轉發回伺服器。

* **本地按一下**  — 當本地通知已傳送到設備且用戶已按一下該通知時。 用戶要麼想查看通知（通知將進而轉到本地開啟跟蹤），要麼想取消通知。

* **本地開啟**  — 當本地通知已傳送到設備，並且用戶已按一下導致應用程式開啟的通知時。 這與本地按一下類似，除非當通知被取消時不會觸發本地開啟。

為了實現對Adobe Campaign Standard的跟蹤，移動應用需要將移動SDK包括在應用中。 這些SDK在 [!DNL Adobe Mobile Services]。

要發送跟蹤資訊，必須發送三個變數：其中兩個是從Adobe Campaign接收的資料的一部分，另一個是一個操作變數，它指示是印象、點擊還是開啟。

| 變數 | 值 |
| :-: | :-: |
| 交貨ID | `deliveryId` 從傳入資料(類似於推送跟蹤 `_dld` ) |
| broadlogId | `broadlogId` 從傳入資料(類似於推送跟蹤 `_mld` ) |
| 動作 | 「1」表示開啟，「2」表示按一下，「7」表示印象 |

## 實施本地印象跟蹤 {#implement-local-impression-tracking}

Adobe Experience Platform移動軟體開發工具包將自動發送Android和iOS的印象事件，而無需進行任何其他配置。

## 實現點擊跟蹤 {#implementing-click-tracking}

對於按一下跟蹤，在調用時必須發送值&quot;2&quot;以執行操作 `collectMessageInfo()` 或 `trackAction()` 的子菜單。

### 對於Android {#implement-click-tracking-android}

要跟蹤點擊量，必須實施兩種方案：

* 用戶看到通知但將其清除。

   若要在解除方案時跟蹤按一下，請添加廣播接收器 `NotificationDismissalHandler` 應用程式模組的AndroidManifest檔案。

   ```
   <receiver
   android:name="com.adobe.marketing.mobile.NotificationDismissalHandler">
   </receiver>
   ```

* 用戶看到通知並按一下它，這將轉為開啟的跟蹤。

   此方案應產生按一下並開啟。 跟蹤此按一下將是跟蹤開啟時所需的實現的一部分。 請參閱 [實現開放跟蹤](#implement-open-tracking)。

### 為iOS {#implement-click-tracking-ios}

要發送按一下跟蹤資訊，必須添加以下內容：

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

## 實現開放跟蹤 {#implement-open-tracking}

您必須發送「1」和「2」，因為用戶必須按一下通知才能開啟應用程式。 如果應用程式未通過本地通知啟動/開啟，則不會發生跟蹤事件。

### 對於Android {#implement-open-tracking-android}

要跟蹤開啟，我們必須建立意圖。 目的對象允許Android OS在完成某些操作時調用您的方法，在這種情況下，按一下通知以開啟應用。

此代碼基於點擊印象跟蹤的實現。 如果設定了目的，您現在必須將跟蹤資訊發回Adobe Campaign。 在本例中，Android View([!DNL Activity])，觸發通知後，用戶將因按一下而開啟或置於前台。 中的目的對象 [!DNL Activity] 包含可用於跟蹤開啟的通知資料。

MainActivity.java（擴展） [!DNL Activity])

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

### 為iOS {#implement-open-tracking-ios}

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
