---
title: 實施推送追蹤
description: 瞭解如何確保在iOS和Android上正確實作推播通知追蹤
audience: channels
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 950d24e2-358f-44f8-98ea-643be61d4573
source-git-commit: 1346f7d833515fb2e6feabb39d199ffd5610c88e
workflow-type: tm+mt
source-wordcount: '932'
ht-degree: 0%

---

# 實施推送追蹤 {#push-tracking}

## 關於推播追蹤 {#about-push-tracking}

若要確保推播通知已完全開發，您必須確保追蹤部分已正確實施，因為並非每個推播通知都啟用追蹤。 若要啟用此功能，開發人員需要識別哪些傳遞已啟用追蹤，Adobe Campaign Standard會傳送稱為的標幟 `_acsDeliveryTracking` 具有兩個值 **於** 或 **關閉**. 應用程式開發人員應僅針對將變數設為的傳遞傳送傳送追蹤請求 **於**.

>[!IMPORTANT]
>
>在21.1版本之前設定的傳送或使用自訂範本的傳送無法使用此變數。

推播追蹤分為三種型別：

* **推播曝光次數**  — 當推播通知成功傳送到裝置時，位於通知中心且沒有任何使用者互動。

* **推送點按**  — 當推播通知已傳送至裝置，且使用者已按一下裝置時。  使用者想要檢視通知（進而將移至推播開啟追蹤）或關閉通知。

* **推送開啟**  — 當推播通知已傳送至裝置，且使用者已按一下導致應用程式開啟的通知。 這類似於「推送點按」，但如果通知已關閉，則不會觸發「推送開啟」。

若要實作Campaign Standard追蹤，行動應用程式必須包含Adobe Experience Platform SDK。 這些SDK可在 [Adobe Experience Platform SDK檔案](https://github.com/Adobe-Marketing-Cloud/acp-sdks).

若要傳送追蹤資訊，有三個變數需要傳送。 其中兩個是從Campaign Standard收到的資料的一部分，另一個是指示其是否為的動作變數 **印象**， **按一下** 或 **開啟**.

| 變數 | 值 |
|:-:|:-:|
| broadlogId | 來自資料的_mId |
| deliveryId | 來自資料的_dId |
| 動作 | 「1」代表「開啟」，「2」代表「點選」，「7」代表「印象」 |

## Android實作 {#implementation-android}

### 如何實作推播曝光追蹤 {#push-impression-tracking-android}

針對曝光追蹤，您必須傳送值「7」才能在呼叫時執行動作 `collectMessageInfo()` 或 `trackAction()` 函式。

對於21.1版本之前建立的傳送或使用自訂範本的傳送，請參閱此 [區段](../../administration/using/push-tracking.md#about-push-tracking).

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
    if( deliveryId != null && messageId != null && acsDeliveryTracking.equals("on")) {
      contextData.put("deliveryId", deliveryId);
      contextData.put("broadlogId", messageId);
      contextData.put("action", "7");

    //If you are using ACPCore v1.4.0 or later, use the next line.
      
      MobileCore.collectMessageInfo(contextData);
      
    //Else comment out the above line and uncomment the line below
        
    //MobileCore.trackAction("tracking", contextData) ;
    }
  }
}
```

### 如何實作點選追蹤 {#push-click-tracking-android}

針對點選追蹤，您必須傳送值「2」才能在呼叫時執行動作 `collectMessageInfo()` 或 `trackAction()` 函式。
若要追蹤點選，需要處理兩個案例：

* 使用者看到通知但將其清除。
* 使用者看到通知並按一下即可將其轉換為開啟追蹤。

若要處理此問題，您需要使用兩個意圖：一個用於按一下通知，另一個用於解除通知。

對於21.1版本之前建立的傳送或使用自訂範本的傳送，請參閱此 [區段](../../administration/using/push-tracking.md#about-push-tracking).

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

為了的 **[!UICONTROL BroadcastReceiver]** 若要使用，您需要將它註冊到 **[!UICONTROL AndroidManifest.xml]**

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
            
        //If you are using ACPCore v1.4.0 or later, use the next line.
        
            MobileCore.collectMessageInfo(contextData);
            
        //Else comment out the above line and uncomment the line below
        
            //MobileCore.trackAction("tracking", contextData);
        }
    }
}
```

### 如何實作開啟追蹤 {#push-open-tracking-android}

您必須傳送「1」和「2」，因為使用者必須按一下「通知」才能開啟應用程式。 如果未透過推播通知啟動/開啟應用程式，則不會發生追蹤事件。

若要追蹤開啟，您需要建立目的。 意圖物件可讓Android作業系統在完成某些動作時呼叫方法。 在此情況下，請按一下通知以開啟應用程式。

此程式碼以點按曝光追蹤的實施為基礎。 替換為 **[!UICONTROL Intent]** 已設定，您現在需要將追蹤資訊傳回Adobe Campaign Standard。 在此情況下，您需要將 **[!UICONTROL Open Intent]** 若要開啟應用程式中的特定檢視，這會呼叫onResume方法，並在其中加入通知資料 **[!UICONTROL Intent Object]**.

對於21.1版本之前建立的傳送或使用自訂範本的傳送，請參閱此 [區段](../../administration/using/push-tracking.md#about-push-tracking).

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
            contextData.put("action", "2");
            
            //Send Click Tracking since the user did click on the notification
              
                //If you are using ACPCore v1.4.0 or later, use the next line.

                MobileCore.collectMessageInfo(contextData);
                  
                //Else comment out the above line and uncomment the line below
        
                //MobileCore.trackAction("tracking", contextData);
 
                //Send Open Tracking since the user opened the app
            
                contextData.put("action", "1");
                
                //If you are using ACPCore v1.4.0 or later, use the next line.

                MobileCore.collectMessageInfo(contextData);
                //Else comment out the above line and uncomment the line below
        
                //MobileCore.trackAction("tracking", contextData);
        }
    }
}
```

## iOS實作 {#implementation-iOS}

### 如何實作推播曝光追蹤 {#push-impression-tracking-iOS}

針對曝光追蹤，您必須傳送值「7」才能在呼叫時執行動作 `collectMessageInfo()` 或 `trackAction()` 函式。

若要瞭解iOS通知的運作方式，應用程式的三種狀態需要詳細說明：

* **前景**：當應用程式目前作用中並位於熒幕上（在前景中）時。
* **背景**：當應用程式不在熒幕上，但程式未關閉時。 按兩下「首頁」按鈕時，通常會顯示背景中的所有應用程式。
* **關閉/關閉**：其程式已終止的應用程式。

為了仍然擁有 **[!UICONTROL Impression]** 應用程式於背景執行時，追蹤系統仍需運作，我們需傳送 **[!UICONTROL Content-Available]** 讓應用程式知道必須完成追蹤。

>[!CAUTION]
>
> 如果應用程式已關閉，Apple將不會呼叫應用程式，直到重新啟動應用程式為止。 這表示您將無法知道何時在iOS上收到通知。 </br> 基於此原因，iOS曝光追蹤可能不準確，且不應被視為可靠。

對於21.1版本之前建立的傳送或使用自訂範本的傳送，請參閱此 [區段](../../administration/using/push-tracking.md#about-push-tracking).

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

            //If you are using ACPCore v2.3.0 or later, use the next line.

                ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"7"])
                
            //Else comment out the above line and uncomment the line below
        
                //ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"7"])
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

            //If you are using ACPCore v2.3.0 or later, use the next line.

                ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"7"])
                
            //Else comment out the above line and uncomment the line below
        
                //ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"7"])        
            }
        completionHandler([.alert,.sound])
    }
```

### 如何實作點選追蹤 {#push-click-tracking-iOS}

針對點選追蹤，您必須傳送值「2」才能在呼叫時執行動作 `collectMessageInfo()` 或 `trackAction()` 函式。
對於21.1版本之前建立的傳送或使用自訂範本的傳送，請參閱此 [區段](../../administration/using/push-tracking.md#about-push-tracking).

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

現在，當您傳送推播通知時，您需要新增類別。 在此案例中，我們將其命名為「DEFAULT」。

![](assets/tracking_push.png)

然後處理 **[!UICONTROL Dismiss]** 並傳送您需要新增下列專案的追蹤資訊：

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

            //If you are using ACPCore v2.3.0 or later, use the next line.

                ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
                
            //Else comment out the above line and uncomment the line below
        
                //ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])   
            }
        default:
            ////MORE CODE
        }
        completionHandler()
    }
```

### 如何實作開啟追蹤 {#push-open-tracking-iOS}

您必須傳送「1」和「2」，因為使用者必須按一下「通知」才能開啟應用程式。 如果未透過推播通知啟動/開啟應用程式，則不會發生追蹤事件。

對於21.1版本之前建立的傳送或使用自訂範本的傳送，請參閱此 [區段](../../administration/using/push-tracking.md#about-push-tracking).

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

            //If you are using ACPCore v2.3.0 or later, use the next line.

                ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
                
            //Else comment out the above line and uncomment the line below
        
                //ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])

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
            //If you are using ACPCore v2.3.0 or later, use the next line.

                ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
                
            //Else comment out the above line and uncomment the line below
        
                //ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])                
                
            //If you are using ACPCore v2.3.0 or later, use the next line.

                ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"1"])
                
            //Else comment out the above line and uncomment the line below
        
                //ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"1"])
                
            }
        }
        completionHandler()
    }
}
```
