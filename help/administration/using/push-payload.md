---
solution: Campaign Standard
product: campaign
title: 瞭解Campaign Standard推播通知有效負載結構
description: 本檔案旨在說明行動應用程式中所接收的負載結構。
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
feature: Instance Settings
role: Administrator
level: Experienced
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '1152'
ht-degree: 3%

---


# 瞭解 推播通知裝載結構 {#push-payload}

Adobe Campaign可讓您將iOS和Android行動裝置上的個人化和分段推播通知傳送至行動應用程式（行動應用程式）。

在行動應用程式上收到的每個推播通知都會攜帶一些資訊，當傳送「警報」推播通知時，應用程式會使用這些資訊來顯示推播通知，而且很可能還會進一步計算，尤其是傳送無訊息推播通知時。

此資訊由行動應用程式程式碼在事件處理常式中接收，指出已收到推播通知。 從Adobe Campaign Standard傳送推播通知時，行動應用程式中收到的資訊也可能包含Campaign Standard特定資訊，這些資訊可用來運用Campaign Standard提供的某些功能。 此外，裝載可包含行動應用程式可使用的自訂資料。

本檔案說明從Adobe Campaign Standard成功將推播通知傳送至應用程式時，行動應用程式中收到的裝載結構。

>[!NOTE]
>
>裝載結構會依行動應用程式類型而異（例如iOS應用程式、啟用FCM的Android應用程式）。

## 推送裝載結構{#push-payload-structure}

本節詳細說明適用於各種行動平台的範例裝載結構，並說明其中包含的主要屬性。 這是事件處理常式中行動應用程式程式程式碼所接收之裝載的結構，表示已收到推播通知。

有效負載屬性及其值會依「推播通知」進階選項中提供的組態而有所不同。 本節還提供Campaign StandardUI中這些配置與裝載中屬性之間的映射，以釐清Campaign Standard中配置選項時裝載的變更方式。

### 針對iOS行動應用程式{#payload-structure-ios}

**從Adobe Campaign傳送至iOS應用程式的裝載範例：**

```
{

    "aps":{

            "alert":{

                    "body":"This is the content of my push notification",

                    "title":"Push Notification Title"

            },

            "content-available":1,

            "category":"NEW_MESSAGE_CATEGORY",

            "badge":2,

            "mutable-content":1,

            "sound":"default"

        },

    "custom_field1":"custom_value1",

    "custom_field2":"custom_value2",

    "media-attachment-url":"https://2.img-dpreview.com/files/p/articles/9440145363/Creative_Cloud.jpeg",

    "uri":"https://mydeeplinkurl.com",

    "_dId":"56c4",

    "_mId":"h138a"} 
```

**搭配 [iOS APNS測試程式使用的JSON範例裝載](https://pushtry.com/)**

```
{

  "aps": {

    "alert": {

      "title": "Push Notification Title",

      "body": "body of push"

    },

    "badge": 33,

    "sound": "default"

  },

  "custom_field1": "custom_value1",

  "uri": "https://mydeeplinkurl.com"

}
```

裝載的最重要部分是aps字典，該字典包含Apple定義的鍵，用於確定接收通知的系統應如何提醒用戶（如果有的話）。 本節包含行動應用程式用來規定推播通知行為的預先定義金鑰。

有關應用程式中屬性的深入詳細資訊，請參閱Apple開發人員檔案：[建立遠程通知裝載](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CreatingtheNotificationPayload.html#//apple_ref/doc/uid/TP40008194-CH10-SW1)。

### 對於Android應用程式{#payload-structure-android}

**從Adobe Campaign傳送至Android應用程式的範例裝載**

```
{

  "collapseKey": "1476005",

  "priority": "high",

  "data": {

    "_dId": "d57fd6",

    "_mId": "h1685a5",

    "body": "adobe body 123",

    "category": "adobe category 123",

    "custom key 1": "value 1",

    "custom key 2": "test value 2",

    "custom key 3": "foo bar android",

    "media-attachment-url": "http://adobegiphy.com?test=123",

    "sound": "http://testcampaign.instance.com/r/?id=s1685a5,d57fd6,d57ff5",

    "title": "adobe title 123",

    "uri": "http://testcampaign.instance.com/r/?id=d1685a5,d57fd6,d57ff6",

    "badge": 1817

  }

}
```

**使用 [Google FCM測試程式的JSON範例裝載](https://pushtry.com/)**

```
{

  "to": "<==========ENTER your device token==============>",

  "collapseKey": "1476005",

  "priority": "high",

  "data": {

    "_dId": "d57fd6",

    "_mId": "h1685a5",

    "title": "adobe title 123",

    "body": "adobe body 123",

    "category": "adobe category 123",

    "custom key 1": "value 1",

    "custom key 2": "test value 2",

    "custom key 3": "foo bar android",

    "media-attachment-url": "http://adobegiphy.com?test=123",

    "sound": "http://testcampaign.instance.com/r/?id=s1685a5,d57fd6,d57ff5",

    "uri": "http://testcampaign.instance.com/r/?id=d1685a5,d57fd6,d57ff6",

    "badge": 1817

  }

}
```

裝載包含包含所有推播通知傳送內容的資料訊息，包括自訂金鑰／值配對，而用戶端應用程式必須處理訊息以建立和顯示推播通知（如有需要），或是其他要新增任何商業邏輯。

若要瞭解Android裝載的各方面，請參閱[訊息概念與選項(fcm)](https://firebase.google.com/docs/cloud-messaging/concept-options)。

>[!NOTE]
>
>自2018年1月起，Android裝載中對「通知」訊息的支援已移除，以啟用應用程式喚醒並將控制項傳遞至行動應用程式，而不需要使用者與應用程式互動。

### Campaign Standard配置和裝載屬性之間的映射{#mapping-payload}

| 促銷活動設定 | iOS中受影響的屬性 | Android中的影響屬性 | 說明 |
|:-:|:-:|:-:|:-:|
| 消息標題<br>消息正文 | 警報→標題<br>警報→主體 | title &lt;a0/body<br> | 此資料包含警報消息的具體資訊。<br>標題和正文鍵提供警報的內容。 |
| 播放音效 | sound | sound | 自訂音效以播放警報。 |
| 徽章的值 | 徽章 | 徽章 | 用於標籤應用程式圖示的整數值。 |
| 新增深層連結 | uri | 納 | 開發人員可讓您將使用者直接導向到應用程式內的內容（而非開啟網頁瀏覽器頁面）。 |
| 類別 | 類別 | 類別 | 顯示具有遠程通知的自定義操作。 <br>類別鍵可協助系統將該類別的動作顯示為警報介面中的按鈕。 |
| 自訂欄位 | custom_field1, custom_field2 ... | custom_field1, custom_field2 ... | 您想要傳送至應用程式的任何自訂資料。 |
| 多媒體內容URL（影像、gif、音訊和視訊檔案）<br>（僅適用於iOS 10或更新版本） | media-attachment-url | 納 | 媒體檔案的URL，以新增豐富內容至通知。 <br>當提供此URL的值時，可變內容標幟會自動傳送至裝載。<br> （僅適用於iOS 10或更新版本） |
| 可變內容<br>（僅適用於iOS 10或更高版本） | 可變內容 | 納 | 您應用程式中的通知服務延伸模組將會使用可變內容金鑰「截取」所有遠端通知，並可讓您處理／控制請求裝載的內容，然後再用來自訂通知。 此功能的使用案例包括下載和顯示多種媒體、解密推播裝載中所有加密資料。 有關詳細資訊，請參閱[修改遠程通知的有效負載。 ](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/ModifyingNotifications.html)<br>（僅適用於iOS 10或更新版本） |
| 可用內容 | 內容可用 | 納 | 選取此選項可讓iOS應用程式處於背景／暫停狀態時喚醒。 喚醒表示應用程式會在背景執行，負責接收推播通知資料裝載的適當事件處理常式會取得控制項，並可使用資料進行任何計算，包括但不限於建立自訂推播通知和顯示相同內容。 如需詳細資訊，請參閱[「使用通知傳送喚醒應用程式」](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CreatingtheNotificationPayload.html)。 |
| 多媒體內容URL（影像檔案）<br>（僅適用於Android） | 納 | media-attachment-url | 影像檔案的URL，以新增豐富內容至通知。 |
| 納 | _mId<br>_dId | _mId <br>_dId | broadlogId和deliveryId的值。<br>如果您的應用程式想要呼叫追蹤回傳以追蹤何時點按／開啟推播通知，則需要這些屬性。此資訊由應用程式伺服器在內部計算並傳送，而不需使用者干預。<br>有關回傳的資訊，請參閱本 [頁](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#PIIpostback)。 |

### 如何擷取行動應用程式程式碼{#payload-information}中的裝載資訊

應用程式伺服器所傳送的裝載資訊會由行動應用程式程式碼在事件處理常式中接收，指出已收到推播通知。 此事件會因正在運作的行動平台而異，也會因應用程式在前景或背景中執行而異。 下列檔案將協助您根據您的使用案例，識別您要處理的事件處理常式。

* iOS應用程式：**處理遠程通知[遠程通知](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/HandlingRemoteNotifications.html)中的「遠程通知」部分。**
* Android應用程式：[在Android用戶端應用程式上接收訊息](https://firebase.google.com/docs/cloud-messaging/android/receive)

**iOS行動應用程式範例**

```
 - (void)application:(UIApplication *)application

didReceiveRemoteNotification:(NSDictionary *)userInfo {

    

    NSDictionary *apsDict = [userInfo objectForKey:@"aps"];

    NSDictionary *alertDict = [apsDict objectForKey:@"alert"];

    NSString *title = [alertDict objectForKey:@"title"];

    NSString *body = [alertDict objectForKey:@"body"];

    NSString *category = [apsDict objectForKey:@"category"];

    NSString *deliveryId = userInfo[@"_dId"];

    NSString *broadlogId = userInfo[@"_mId"];

    NSString *mediaAttachmentURL = userInfo[@"media-attachment-url"];

    NSString *deeplinkURL = userInfo[@"uri"];

    NSString *customValue1 = userInfo[@"custom_field1"];   

}
```

**Android Mobile FCM應用程式範例**

```
public void onMessageReceived(RemoteMessage message) {

    Map<String, String> dataMap = message.getData();

     

    String title = dataMap.get("title");

    String body = dataMap.get("body");

    String category = dataMap.get("category");

    String deliveryId = dataMap.get("_dId");

    String broadlogId = dataMap.get("_mId");

    String mediaAttachmentURL = dataMap.get("media-attachment-url");

    String deeplinkURL = dataMap.get("uri");

    String customValue1 = dataMap.get("custom_field1");

}
```
