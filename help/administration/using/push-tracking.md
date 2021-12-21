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
exl-id: 950d24e2-358f-44f8-98ea-643be61d4573
source-git-commit: 95d4b9fbb41f5204f387971be3710817a281a8c4
workflow-type: tm+mt
source-wordcount: '954'
ht-degree: 1%

---

# 實施推送追蹤 {#push-tracking}

## 關於推播追蹤 {#about-push-tracking}

若要確保推播通知已完全開發，您必須確定追蹤部分已正確實作，因為並非所有推播通知都已啟用追蹤。 若要啟用此功能，開發人員需要識別已啟用追蹤的傳送，Adobe Campaign Standard會傳送標幟，稱為 `_acsDeliveryTracking` 兩個值 **on** 或 **關閉**. 應用程式開發人員只應在將變數設為的傳送時傳送追蹤請求 **on**.

>[!IMPORTANT]
>
>此變數無法供21.1版之前設定的傳送或使用自訂範本的傳送使用。

推播追蹤分為三種類型：

* **推播曝光數**  — 推播通知已傳送至裝置，且位於通知中心，但完全未接觸時。  這會視為曝光。  在大多數情況下，曝光數數字若與傳送的數字不同，則應相似。 它確保設備確實收到消息並將該資訊轉發回伺服器。

* **推送點按**  — 推送通知已傳送至裝置，且使用者已點按裝置時。  使用者要麼想要檢視通知（這進而會移至「推播開啟」追蹤），要麼要關閉通知。

* **推送開啟**  — 推播通知已傳送至裝置，且使用者已點按通知導致應用程式開啟時。  這類似於推播點擊，但若關閉通知，則不會觸發推播開啟。

若要實作Campaign Standard的追蹤，行動應用程式必須包含行動SDK。 這些SDK可在AdobeMobile Services上使用。 如需關於此項目的詳細資訊，請參閱此[頁面](../../administration/using/configuring-a-mobile-application.md)。

若要傳送追蹤資訊，有三個變數需要傳送。 兩個是從Campaign Standard接收資料的一部分，另一個是指定其是否為 **曝光**, **按一下** 或 **開啟**.

| 變數 | 值 |
|:-:|:-:|
| broadlogId | 來自資料的_mId |
| deliveryId | 資料的_dId |
| 動作 | 1代表開啟，2代表點按，7代表曝光 |

## Android適用的實作 {#implementation-android}

### 如何實作推播曝光追蹤 {#push-impression-tracking-android}

若是曝光追蹤，您必須在呼叫時傳送值「7」以執行動作 **[!UICONTROL trackAction()]** 函式。

若為21.1版之前建立的傳送，或使用自訂範本的傳送，請參閱 [節](../../administration/using/push-tracking.md#about-push-tracking).

```
@Override
public void onMessageReceived(RemoteMessage remoteMessage) {
....{Handle push messages}....
  if (data.size() > 0) {
    String deliveryId = data.get("_dId");
    String messageId = data.get("_mId");
    String acsDeliveryTracking = data.get("_acsDeliveryTracking");
 
    /*
    This is to handle deliveries created before 21.1 release or deliveries with custom template
    where acsDeliveryTracking is not available.
    */
    if( acsDeliveryTracking == null ) {
        acsDeliveryTracking = "on";
    }
 
    HashMap<String, String> contextData = new HashMap<>();
    if (deliveryId != null && messageId != null && acsDeliveryTracking.equals("on")) {
                contextData.put("deliveryId", deliveryId);
                contextData.put("broadlogId", messageId);
                contextData.put("action", "7");
                MobileCore.trackAction("tracking", contextData);
    }
  }
}
```

### 如何實作點擊追蹤 {#push-click-tracking-android}

若是點擊追蹤，您必須在呼叫時傳送值「2」以執行動作 **[!UICONTROL trackAction()]** 函式。

若要追蹤點按，需處理兩種情況：

* 使用者會看見通知，但將其清除。
* 使用者會看見通知，並點按通知，將其轉換為開啟追蹤。

若要處理此問題，您必須使用兩種意圖：一個用於按一下通知，另一個用於關閉通知。

若為21.1版之前建立的傳送，或使用自訂範本的傳送，請參閱 [節](../../administration/using/push-tracking.md#about-push-tracking).

**[!UICONTROL MyFirebaseMessagingService.java]**

```
private void sendNotification(Map<String, String> data) {
    Intent openIntent = new Intent(this, CollectPIIActivity.class);
    Intent dismissIntent = new Intent(this, NotificationDismissedReceiver.class);
    openIntent.addFlags(Intent.FLAG_ACTIVITY_CLEAR_TOP);
  
    //put the data map into the intent to track clickthroughs
    Bundle pushData = new Bundle();
    Set<String> keySet = data.keySet();
    for (String key : keySet) {
        pushData.putString(key, data.get(key));
    }
    openIntent.putExtras(pushData);
    dissmissIntent.putExtras(pushData);
  
  
    PendingIntent pendingIntent = PendingIntent.getActivity(this, 0, openIntent,
        PendingIntent.FLAG_UPDATE_CURRENT);
    PendingIntent onDismissPendingIntent = PendingIntent.getBroadcast(this.getApplicationContext(), 0, dismissIntent, 0);
  
    //<BUILD NOTIFICATION using notification builder>
    //Add both Intents to the notification
    notificationBuilder.setContentIntent(pendingIntent);
    notificationBuilder.setDeleteIntent(onDismissPendingIntent);
}
```

為了 **[!UICONTROL BroadcastReceiver]** 要工作，您需要將其註冊到 **[!UICONTROL AndroidManifest.xml]**

```
<manifest>
    <application>
        <receiver android:name=".NotificationDismissedReceiver">
        </receiver>
    </application>
</manifest>
```

NotificationDismessedReceiver.java

```
public class NotificationDismissedReceiver extends BroadcastReceiver {
    private static final String TAG = NotificationDismissedReceiver.class.getSimpleName();
    @Override
    public void onReceive(Context context, Intent intent) {
        Bundle data = intent.getExtras();
        String deliveryId = data.getString("_dId");
        String messageId = data.getString("_mId");
        String acsDeliveryTracking = data.get("_acsDeliveryTracking");
         
        /*
        This is to handle deliveries created before 21.1 release or deliveries with custom template
        where acsDeliveryTracking is not available.
        */
        if( acsDeliveryTracking == null ) {
            acsDeliveryTracking = "on";
        }
 
        HashMap<String, Object> contextData = new HashMap<>();
 
        //We only send the click tracking since the user dismissed the notification
        if (deliveryId != null && messageId != null && acsDeliveryTracking.equals("on")) {
            contextData.put("deliveryId", deliveryId);
            contextData.put("broadlogId", messageId);
            contextData.put("action", "2");
            MobileCore.trackAction("tracking", contextData);
        }
    }
}
```

### 如何實作開啟追蹤 {#push-open-tracking-android}

由於使用者必須按一下通知才能開啟應用程式，因此您需要傳送「1」和「2」。 如果應用程式未透過推播通知啟動/開啟，則不會發生追蹤事件。

若要追蹤開啟，您需要建立Intent。 目的物件可讓Android作業系統在完成特定動作時呼叫您的方法。 在此情況下，按一下通知以開啟應用程式。

此程式碼以點擊曝光追蹤的實作為基礎。 使用 **[!UICONTROL Intent]** 設定後，您現在需要將追蹤資訊傳回Adobe Campaign Standard。 在此情況下，您需要設定 **[!UICONTROL Open Intent]** 若要在您的應用程式中開啟至特定檢視，這會呼叫onResume方法，其中包含 **[!UICONTROL Intent Object]**.

若為21.1版之前建立的傳送，或使用自訂範本的傳送，請參閱 [節](../../administration/using/push-tracking.md#about-push-tracking).

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
        //This was opened based on the notification, you need to get the tracking that was passed on.
        String deliveryId = data.getString("_dId");
        String messageId = data.getString("_mId");
        String acsDeliveryTracking = data.get("_acsDeliveryTracking");
        /*
        This is to handle deliveries created before 21.1 release or deliveries with custom template
        where acsDeliveryTracking is not available.
        */
        if( acsDeliveryTracking == null) {
            acsDeliveryTracking = "on";
        }
 
        HashMap<String, String> contextData = new HashMap<>();
 
        if (deliveryId != null && messageId != null && acsDeliveryTracking.equals("on")) {
            contextData.put("deliveryId", deliveryId);
            contextData.put("broadlogId", messageId);
 
            //Send Click Tracking since the user did click on the notification
            contextData.put("action", "2");
            MobileCore.trackAction("tracking", contextData);
 
            //Send Open Tracking since the user opened the app
            contextData.put("action", "1");
            MobileCore.trackAction("tracking", contextData);
        }
    }
}
```

## 實作iOS {#implementation-iOS}

### 如何實作推播曝光追蹤 {#push-impression-tracking-iOS}

若是曝光追蹤，您必須在呼叫時傳送值「7」以執行動作 **[!UICONTROL trackAction()]** 函式。

若要了解iOS通知的運作方式，應用程式的三種狀態必須詳細說明：

* **前景**:應用程式目前處於作用中狀態且目前處於畫面上時（在前景中）。
* **背景**:當is應用程式未在畫面上，但程式未關閉時。 當您按兩下「首頁」按鈕時，通常會顯示背景中的所有應用程式。
* **關閉/關閉**:一個程式被殺的應用。

為了還有 **[!UICONTROL Impression]** 在應用程式於背景執行時進行追蹤，我們需要傳送 **[!UICONTROL Content-Available]** 讓應用程式知道必須執行追蹤。

>[!CAUTION]
>
> 如果應用程式關閉，在應用程式重新啟動前，Apple不會呼叫應用程式。 這表示您將無法知道iOS上何時收到通知。 </br> 因此，iOS曝光追蹤可能不準確，也不應視為可靠。

若為21.1版之前建立的傳送，或使用自訂範本的傳送，請參閱 [節](../../administration/using/push-tracking.md#about-push-tracking).

下列程式碼會鎖定背景應用程式：

```
// In didReceiveRemoteNotification event handler in AppDelegate.m
 
//In order to handle push notification when only in background with content-available: 1
func application(_ application: UIApplication, didReceiveRemoteNotification userInfo: [AnyHashable : Any], fetchCompletionHandler completionHandler: @escaping (UIBackgroundFetchResult) -> Void) {
 
        //Check if the app is not in the foreground right now
        if(UIApplication.shared.applicationState != .active) {
            let deliveryId = userInfo["_dId"] as? String
            let broadlogId = userInfo["_mId"] as? String
            let acsDeliveryTracking = userInfo["_acsDeliveryTracking"] as? String
            /*
            This is to handle deliveries created before 21.1 release or deliveries with custom template where acsDeliveryTracking is not available.
            */
            if( acsDeliveryTracking == nil ) {
                acsDeliveryTracking = "on";
            }
            if (deliveryId != nil && broadlogId != nil && acsDeliveryTracking?.caseInsensitiveCompare("on") == ComparisonResult.orderedSame) {
               ADBMobile.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"7"])
            }
        }
        completionHandler(UIBackgroundFetchResult.noData)
    }
```

下列程式碼會鎖定前景應用程式：

```
// This will get called when the app is in the foreground
 
func userNotificationCenter(_ center: UNUserNotificationCenter, willPresent notification: UNNotification, withCompletionHandler completionHandler: @escaping (UNNotificationPresentationOptions) -> Void) {
 
 
        let userInfo = notification.request.content.userInfo
        let deliveryId = userInfo["_dId"] as? String
        let broadlogId = userInfo["_mId"] as? String
        let acsDeliveryTracking = userInfo["_acsDeliveryTracking"] as? String
        /*
        This is to handle deliveries created before 21.1 release or deliveries with custom template where acsDeliveryTracking is not available.
        */
        if( acsDeliveryTracking == nil ) {
            acsDeliveryTracking = "on";
        }
        if (deliveryId != nil && broadlogId != nil && acsDeliveryTracking?.caseInsensitiveCompare("on") == ComparisonResult.orderedSame) {
             ADBMobile.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"7"])
        }
        completionHandler([.alert,.sound])
    }
```

### 如何實作點擊追蹤 {#push-click-tracking-iOS}

若是點擊追蹤，您必須在呼叫時傳送值「2」以執行動作 **[!UICONTROL trackAction()]** 函式。
若為21.1版之前建立的傳送，或使用自訂範本的傳送，請參閱 [節](../../administration/using/push-tracking.md#about-push-tracking).

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

現在，當您傳送推播通知時，需要新增類別。 在此案例中，我們稱為「DEFAULT」。

![](assets/tracking_push.png)

然後處理 **[!UICONTROL Dismiss]** 並傳送您需要新增下列項目的追蹤資訊：

```
func userNotificationCenter(_ center: UNUserNotificationCenter, didReceive response: UNNotificationResponse, withCompletionHandler completionHandler: @escaping () -> Void) {
        let userInfo = response.notification.request.content.userInfo
        switch response.actionIdentifier {
        case UNNotificationDismissActionIdentifier:
            print("Dismiss Action")
            let deliveryId = userInfo["_dId"] as? String
            let broadlogId = userInfo["_mId"] as? String
            let acsDeliveryTracking = userInfo["_acsDeliveryTracking"] as? String
            /*
            This is to handle deliveries created before 21.1 release or deliveries with custom template where acsDeliveryTracking is not available.
            */
            if( acsDeliveryTracking == nil ) {
                acsDeliveryTracking = "on";
            }
            if (deliveryId != nil && broadlogId != nil && acsDeliveryTracking?.caseInsensitiveCompare("on") == ComparisonResult.orderedSame) {
                ADBMobile.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
            }
        default:
            ////MORE CODE
        }
        completionHandler()
    }
```

### 如何實作開啟追蹤 {#push-open-tracking-iOS}

由於使用者必須按一下通知才能開啟應用程式，因此您需要傳送「1」和「2」。 如果應用程式未透過推播通知啟動/開啟，則不會發生追蹤事件。

若為21.1版之前建立的傳送，或使用自訂範本的傳送，請參閱 [節](../../administration/using/push-tracking.md#about-push-tracking).

```
import Foundation
import UserNotifications
import UserNotificationsUI
 
class NotificationDelegate: NSObject, UNUserNotificationCenterDelegate {
 
    // Called when user clicks the push notification or also called from willPresent()
    func userNotificationCenter(_ center: UNUserNotificationCenter, didReceive response: UNNotificationResponse, withCompletionHandler completionHandler: @escaping () -> Void) {
 
        let userInfo = response.notification.request.content.userInfo
        os_log("App push data %{public}@, in userNotificationCenter:didReceive()", type: .debug, userInfo)
        switch response.actionIdentifier {
        case UNNotificationDismissActionIdentifier:
            //This is to handle the Dismiss Action
            let deliveryId = userInfo["_dId"] as? String
            let broadlogId = userInfo["_mId"] as? String
            let acsDeliveryTracking = userInfo["_acsDeliveryTracking"] as? String
            /*
            This is to handle deliveries created before 21.1 release or deliveries with custom template where acsDeliveryTracking is not available.
            */
            if( acsDeliveryTracking == nil ) {
                acsDeliveryTracking = "on";
            }
            if (deliveryId != nil && broadlogId != nil && acsDeliveryTracking?.caseInsensitiveCompare("on") == ComparisonResult.orderedSame) {
                ADBMobile.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
            }
        default:
            //This is to handle the tracking when the app opens
            let deliveryId = userInfo["_dId"] as? String
            let broadlogId = userInfo["_mId"] as? String
            let acsDeliveryTracking = userInfo["_acsDeliveryTracking"] as? String
            /*
            This is to handle deliveries created before 21.1 release or deliveries with custom template where acsDeliveryTracking is not available.
            */
            if( acsDeliveryTracking == nil ) {
                acsDeliveryTracking = "on";
            }
            if (deliveryId != nil && broadlogId != nil && acsDeliveryTracking?.caseInsensitiveCompare("on") == ComparisonResult.orderedSame) {
                ADBMobile.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
                ADBMobile.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"1"])
            }
        }
        completionHandler()
    }
}
```
