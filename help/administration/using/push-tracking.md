---
title: 實施推送追蹤
description: 瞭解如何確保推送通知跟蹤已在iOS和Android上正確實施
audience: channels
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 950d24e2-358f-44f8-98ea-643be61d4573
source-git-commit: bfba6b156d020e8d2656239e713d2d24625bda54
workflow-type: tm+mt
source-wordcount: '952'
ht-degree: 1%

---

# 實施推送追蹤 {#push-tracking}

## 關於推式跟蹤 {#about-push-tracking}

要確保推送通知已完全開發，您需要確保跟蹤部分已正確實施，因為並非每個推送通知都已啟用跟蹤。 為了實現這一點，開發商需要確定哪些交付已啟用跟蹤，Adobe Campaign Standard將發送一個名為 `_acsDeliveryTracking` 有兩個值 **上** 或 **關**。 應用開發者應僅在將變數設定為的交貨上發送跟蹤請求 **上**。

>[!IMPORTANT]
>
>此變數不可用於在21.1版本之前設定的交貨或使用自定義模板進行交貨。

推送跟蹤分為三種類型：

* **推送印象**  — 當推送通知已送達設備且位於通知中心，但完全未觸碰時。  這被認為是一種印象。  在大多數情況下，印數應與已交付的數字相同。 它確保設備確實收到消息並將該資訊轉發回伺服器。

* **推式按一下**  — 將推送通知發送給設備且用戶已按一下該設備時。  用戶要麼想查看通知（通知將進而轉到「推送開啟」跟蹤），要麼就取消通知。

* **推開**  — 將推送通知傳送到設備，並且用戶按一下了導致應用開啟的通知。  這與「推式按一下」類似，但「推式開啟」在通知被撤消時不會觸發。

要實現Campaign Standard跟蹤，移動應用需要包括移動SDK。 這些SDK可用於Adobe移動服務。 如需關於此項目的詳細資訊，請參閱此[頁面](../../administration/using/configuring-a-mobile-application.md)。

要發送跟蹤資訊，需要發送三個變數。 兩個是從Campaign Standard接收的資料的一部分，並且是一個操作變數，指示它是否是 **印象**。 **按一下** 或 **開啟**。

| 變數 | 值 |
|:-:|:-:|
| broadlogId | 資料的mId(_M) |
| 交貨ID | 資料的dId(_D) |
| 動作 | 1表示「開啟」，2表示「按一下」，7表示「印象」 |

## Android的實現 {#implementation-android}

### 如何實現推印跟蹤 {#push-impression-tracking-android}

要進行印象跟蹤，您必須在呼叫時發送值「7」以執行操作 **[!UICONTROL trackAction()]** 的子菜單。

有關在21.1版本之前建立的交貨或使用自定義模板建立的交貨，請參閱 [節](../../administration/using/push-tracking.md#about-push-tracking)。

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

### 如何實現點擊跟蹤 {#push-click-tracking-android}

要進行按一下跟蹤，您必須在調用時發送值「2」以執行操作 **[!UICONTROL trackAction()]** 的子菜單。

要跟蹤按一下，需要處理兩個方案：

* 用戶看到通知但將其清除。
* 用戶看到通知並點擊它，將其變為開啟的跟蹤。

要處理此問題，您需要使用兩種方式：一個用於按一下通知，另一個用於取消通知。

有關在21.1版本之前建立的交貨或使用自定義模板建立的交貨，請參閱 [節](../../administration/using/push-tracking.md#about-push-tracking)。

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

為了 **[!UICONTROL BroadcastReceiver]** 你需要註冊到 **[!UICONTROL AndroidManifest.xml]**

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

### 如何實現開放式跟蹤 {#push-open-tracking-android}

您需要發送「1」和「2」，因為用戶必須按一下通知才能開啟應用。 如果應用未通過推送通知啟動/開啟，則不會發生跟蹤事件。

要跟蹤開啟，需要建立「目的」。 目的對象允許Android OS在執行某些操作時調用方法。 在這種情況下，按一下通知以開啟應用。

此代碼基於點擊印象跟蹤的實現。 與 **[!UICONTROL Intent]** 設定，現在需要將跟蹤資訊發回Adobe Campaign Standard。 在這種情況下，你需要 **[!UICONTROL Open Intent]** 若要開啟到應用中的某個視圖，此操作將調用onResume方法，其中的通知資料 **[!UICONTROL Intent Object]**。

有關在21.1版本之前建立的交貨或使用自定義模板建立的交貨，請參閱 [節](../../administration/using/push-tracking.md#about-push-tracking)。

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

## 執行iOS {#implementation-iOS}

### 如何實現推印跟蹤 {#push-impression-tracking-iOS}

要進行印象跟蹤，您必須在呼叫時發送值「7」以執行操作 **[!UICONTROL trackAction()]** 的子菜單。

要瞭解iOS通知的工作原理，需要詳細說明應用的三種狀態：

* **前景**:當應用當前處於活動狀態且當前處於螢幕上時（在前台）。
* **背景**:當is應用未在螢幕上但進程未關閉時。 按兩下「首頁」按鈕時，通常會顯示背景中的所有應用。
* **關閉/關閉**:一個程式已被終止的應用。

為了還能 **[!UICONTROL Impression]** 在應用程式處於後台時跟蹤工作，我們需要發送 **[!UICONTROL Content-Available]** 讓應用知道必須進行跟蹤。

>[!CAUTION]
>
> 如果某個應用被關閉，Apple將不會調用該應用，直到該應用被重新啟動。 這意味著您將無法知道何時在iOS收到通知。 </br> 因此，iOS印象跟蹤可能不準確，不應被視為可靠。

有關在21.1版本之前建立的交貨或使用自定義模板建立的交貨，請參閱 [節](../../administration/using/push-tracking.md#about-push-tracking)。

以下代碼針對後台應用：

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

以下代碼針對前台應用：

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

### 如何實現點擊跟蹤 {#push-click-tracking-iOS}

要進行按一下跟蹤，您必須在調用時發送值「2」以執行操作 **[!UICONTROL trackAction()]** 的子菜單。
有關在21.1版本之前建立的交貨或使用自定義模板建立的交貨，請參閱 [節](../../administration/using/push-tracking.md#about-push-tracking)。

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

現在，當您發送推送通知時，需要添加類別。 在本例中，我們稱其為DEFAULT。

![](assets/tracking_push.png)

然後處理 **[!UICONTROL Dismiss]** 併發送需要添加以下內容的跟蹤資訊：

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

### 如何實現開放式跟蹤 {#push-open-tracking-iOS}

您需要發送「1」和「2」，因為用戶必須按一下通知才能開啟應用。 如果應用未通過推送通知啟動/開啟，則不會發生跟蹤事件。

有關在21.1版本之前建立的交貨或使用自定義模板建立的交貨，請參閱 [節](../../administration/using/push-tracking.md#about-push-tracking)。

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
