---
title: 實施推播追蹤
description: 本檔案可讓您確保推播通知追蹤已在iOS和Android上正確實作。
page-status-flag: never-activated
uuid: 961aaeb5-6948-4fd2-b8d7-de4510c10566
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: push-notifications
discoiquuid: 23b4212e-e878-4922-be20-50fb7fa88ae8
context-tags: mobileApp,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 02fa55789449efe03af75779892303941b8a2871
workflow-type: tm+mt
source-wordcount: '839'
ht-degree: 0%

---


# 實施推播追蹤 {#push-tracking}

## 關於推播追蹤 {#about-push-tracking}

若要確保已完全開發推播通知，您必須確定追蹤部分已正確實作。

下列步驟可讓您確保推播追蹤已正確實作。 這假設您已實作推播通知實作的第一部分： 註冊應用程式使用者並處理推播通知訊息。

推播追蹤分為三種類型：

* **推播印象** -當推播通知已傳送至裝置且位於通知中心，但完全未觸及時。  這被視為一種印象。  在大多數情況下，印象數應與傳送的數字相同，如果與傳送的數字不相同。 它確保設備收到消息並將該資訊轉發回伺服器。

* **推播點按** -當推播通知已傳送至裝置且使用者已點按裝置時。  使用者要麼想要檢視通知（此通知會接著移至「推播開啟追蹤」），要麼就要關閉通知。

* **推播開啟** -當推播通知已傳送至裝置，且使用者已點按通知導致應用程式開啟時。  這類似於推播點按，但是當通知關閉時，不會觸發推播開啟。

若要實作Campaign Standard的追蹤，行動應用程式必須包含Mobile SDK。 這些SDK可在Adobe Mobile Services上取得。

若要傳送追蹤資訊，有三個變數需要傳送。 兩個是從「促銷活動標準」收到的資料的一部分，另一個是指定印象、按一下或開 **啟的****動作** 變 **數**。

| 變數 | 值 |
|:-:|:-:|
| broadlogId | 資料的_mId |
| deliveryId | _dId來自資料 |
| 動作 | 1代表開啟，2代表點按，7代表印象 |

## Android的實作 {#implementation-android}

### 如何實施推播曝光追蹤 {#push-impression-tracking-android}

若是印象追蹤，在呼叫trackAction()函式時，您必須傳送值&quot;7&quot;以取得動作。

```
@Override
public void onMessageReceived(RemoteMessage remoteMessage) {
....{Handle push messages}....
  if (data.size() > 0) {
    String deliveryId = data.get("_dId");
    String messageId = data.get("_mId");
    HashMap<String, String> contextData = new HashMap<>();
    if (deliveryId != null && messageId != null) {
                contextData.put("deliveryId", deliveryId);
                contextData.put("broadlogId", messageId);
                contextData.put("action", "7");
                MobileCore.trackAction("tracking", contextData);
    }
  }
}
```

### 如何實施點按追蹤 {#push-click-tracking-android}

若是點按追蹤，您必須在呼叫trackAction()函式時傳送動作值&quot;2&quot;。

若要追蹤點按，需要處理兩種情況：

* 使用者會看到通知，但會將其清除。
* 使用者會看到通知，並按一下通知，將其轉換為開啟的追蹤。

若要處理此問題，您必須使用兩種方式： 一個用於按一下通知，另一個用於關閉通知。

MyFirebaseMessagingService.java

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

為了讓BroadcastReceiver運作，您必須將它註冊至AndroidManifest.xml

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
  
        HashMap<String, Object> contextData = new HashMap<>();
  
        //We only send the click tracking since the user dismissed the notification
        if (deliveryId != null && messageId != null) {
            contextData.put("deliveryId", deliveryId);
            contextData.put("broadlogId", messageId);
            contextData.put("action", "1");
            MobileCore.trackAction("tracking", contextData);
        }
    }
}
```

### 如何實施開放追蹤 {#push-open-tracking-android}

您需要傳送「1」和「2」，因為使用者必須按一下通知才能開啟應用程式。 如果應用程式未透過推播通知啟動／開啟，則不會發生追蹤事件。

若要追蹤開啟，您必須建立「方式」。 目的物件可讓Android OS在執行特定動作時呼叫您的方法。 在此情況下，按一下通知以開啟應用程式。

此程式碼是以點按印象追蹤的實施為基礎。 在設定「方式」後，您現在需要將追蹤資訊傳回至「促銷活動」。 在這種情況下，您必須將「開啟方式」設定為在應用程式中開啟至特定檢視，這會呼叫onResume方法，並在「方式物件」中提供通知資料。

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
        String deliveryId = data.getString("_dId");
        String messageId = data.getString("_mId");
  
        HashMap<String, Object> contextData = new HashMap<>();
  
        if (deliveryId != null && messageId != null) {
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

## iOS的實作 {#implementation-iOS}

### 如何實施推播曝光追蹤 {#push-impression-tracking-iOS}

若是印象追蹤，在呼叫trackAction()函式時，您必須傳送值&quot;7&quot;以取得動作。

若要瞭解iOS通知的運作方式，應用程式的三種狀態必須詳細說明：

* **前景**: 當應用程式目前處於作用中且目前在畫面上（在前景中）時。
* **背景**: 當is應用程式未在螢幕上，但程式未關閉時。 當您按兩下「首頁」按鈕時，通常會展示背景中的所有應用程式。
* **關閉／關閉**: 應用程式的程式已經中斷。

如果應用程式關閉，Apple會在應用程式重新啟動之前呼叫該應用程式。 這表示您無法得知iOS上的通知何時收到。

為了在應用程式處於背景時仍能進行曝光追蹤，我們需要傳送 **Content-Available** ，讓應用程式知道必須進行追蹤。

>[!CAUTION]
>
>iOS曝光追蹤不準確，不應視為可靠。

下列程式碼以背景應用程式為目標：

```
// In didReceiveRemoteNotification event handler in AppDelegate.m
  
//In order to handle push notification when only in background with content-available: 1
func application(_ application: UIApplication, didReceiveRemoteNotification userInfo: [AnyHashable : Any], fetchCompletionHandler completionHandler: @escaping (UIBackgroundFetchResult) -> Void) {
  
        //Check if the app is not in the foreground right now
        if(UIApplication.shared.applicationState != .active) {
            let deliveryId = userInfo["_dId"] as? String
            let broadlogId = userInfo["_mId"] as? String
            if (deliveryId != nil && broadlogId != nil) {
               ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"7"])
            }
        }
        completionHandler(UIBackgroundFetchResult.noData)
    }
```

下列程式碼針對前景應用程式：

```
// This will get called when the app is in the foreground
  
func userNotificationCenter(_ center: UNUserNotificationCenter, willPresent notification: UNNotification, withCompletionHandler completionHandler: @escaping (UNNotificationPresentationOptions) -> Void) {
  
  
        let userInfo = notification.request.content.userInfo
        let deliveryId = userInfo["_dId"] as? String
        let broadlogId = userInfo["_mId"] as? String
        if (deliveryId != nil && broadlogId != nil) {
             ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"7"])
        }
        completionHandler([.alert,.sound])
    }
```

### 如何實施點按追蹤 {#push-click-tracking-iOS}

若是點按追蹤，您必須在呼叫trackAction()函式時傳送動作值&quot;2&quot;。

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

現在，當您傳送推播通知時，需要新增類別。 在本例中，我們稱之為「DEFAULT」。

![](assets/tracking_push.png)

然後，若要處理「關閉」並傳送您需要新增下列項目的追蹤資訊：

```
func userNotificationCenter(_ center: UNUserNotificationCenter, didReceive response: UNNotificationResponse, withCompletionHandler completionHandler: @escaping () -> Void) {
        let userInfo = response.notification.request.content.userInfo
        switch response.actionIdentifier {
        case UNNotificationDismissActionIdentifier:
            print("Dismiss Action")
            let deliveryId = userInfo["_dId"] as? String
            let broadlogId = userInfo["_mId"] as? String
            if (deliveryId != nil && broadlogId != nil) {
                ADBMobile.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
            }
        default:
            ////MORE CODE
        }
        completionHandler()
    }
```

### 如何實施開放追蹤 {#push-open-tracking-iOS}

您需要傳送「1」和「2」，因為使用者必須按一下通知才能開啟應用程式。 如果應用程式未透過推播通知啟動／開啟，則不會發生追蹤事件。

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
            if (deliveryId != nil && broadlogId != nil) {
                ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
            }
        default:
            //This is to handle the tracking when the app opens
            let deliveryId = userInfo["_dId"] as? String
            let broadlogId = userInfo["_mId"] as? String
            if (deliveryId != nil && broadlogId != nil) {
                ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
                ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"1"])
            }
        }
        completionHandler()
    }
}
```
