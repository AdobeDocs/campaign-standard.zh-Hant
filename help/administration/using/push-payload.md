---
title: 了解Campaign Standard推播通知裝載結構
description: 本檔案旨在說明行動應用程式中接收之裝載的結構。
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
feature: Instance Settings
role: Admin
level: Experienced
exl-id: a6515795-1006-4f27-bc44-5ae8b8edc018
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '1147'
ht-degree: 3%

---

# 瞭解推送通知裝載結構 {#push-payload}

Adobe Campaign可讓您在iOS和Android行動裝置上，將個人化和分段的推播通知傳送至行動應用程式（行動應用程式）。

在行動應用程式上收到的每個推播通知，都會包含應用程式在傳送「警報」推播通知時用來顯示推播通知的一些資訊，而且最有可能還會執行一些進一步的計算，尤其是在傳送無提示推播通知時。

行動應用程式程式碼會在事件處理常式中接收此資訊，指出已收到推播通知。 從Adobe Campaign Standard傳送推播通知時，行動應用程式中收到的資訊可能也包含Campaign Standard特定資訊，這些資訊可用來運用Campaign Standard提供的某些功能。 此外，裝載可包含行動應用程式可使用的自訂資料。

本檔案說明從Adobe Campaign Standard成功將推播通知傳送至應用程式時，行動應用程式中收到的裝載結構。

>[!NOTE]
>
>裝載結構會依行動應用程式類型而異（例如iOS應用程式、啟用FCM的Android應用程式）。

## 推送裝載結構 {#push-payload-structure}

本節詳細說明各種行動平台的裝載範例結構，並說明其中包含的主要屬性。 這是事件處理常式中行動應用程式程式碼中接收之裝載的結構，可指出已接收推播通知。

裝載屬性及其值會根據推播通知進階選項中提供的設定而有所不同。 本節也提供Campaign StandardUI中這些設定與裝載中屬性之間的對應，以釐清裝載在設定Campaign Standard中的選項時將如何變更。

### 適用於iOS行動應用程式 {#payload-structure-ios}

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

**搭配iOS APNS測試器使用的JSON [裝載範例](https://pushtry.com/)**

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

裝載最重要的區段是應用程式字典，該字典包含Apple定義的索引鍵，用於判斷接收通知的系統應如何（如果有的話）向使用者發出警報。 本節包含預先定義的索引鍵，行動應用程式會使用這些索引鍵來制定推播通知的行為。

您可以在Apple開發人員檔案中找到aps中屬性的深入詳細資訊：[建立遠程通知裝載](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CreatingtheNotificationPayload.html#//apple_ref/doc/uid/TP40008194-CH10-SW1)。

### 適用於Android應用程式 {#payload-structure-android}

**從Adobe Campaign傳送至Android應用程式的裝載範例**

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

**使用Google FCM測試器的 [JSON裝載範例](https://pushtry.com/)**

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

裝載包含資料訊息，包含所有推播通知傳送內容，包括自訂金鑰/值組，而用戶端應用程式必須處理訊息以建立和顯示推播通知（如有需要），否則必須處理以新增任何其他業務邏輯。

若要了解android裝載的方面，請參閱[傳訊概念與選項(fcm)](https://firebase.google.com/docs/cloud-messaging/concept-options)。

>[!NOTE]
>
>自2018年1月起，Android裝載中對通知訊息的支援已移除，以啟用喚醒應用程式並將控制項傳遞至行動應用程式，而不需要使用者與應用程式互動。

### Campaign Standard設定和裝載屬性之間的對應 {#mapping-payload}

| 促銷活動設定 | iOS中的受影響屬性 | Android中的受影響屬性 | 說明 |
|:-:|:-:|:-:|:-:|
| 訊息標題<br>訊息內文 | 警報→標題<br>警報→主體 | 標題<br>正文 | 此資料包含警報訊息的細節。<br>標題和正文鍵提供警報的內容。 |
| 播放音效 | 聲音 | 聲音 | 與警報一起播放的自訂音效。 |
| 徽章的值 | 徽章 | 徽章 | 要用來標示應用程式圖示的整數值。 |
| 新增深層連結 | uri | 不適用 | 開發人員可讓您將使用者直接導向到應用程式內的內容（而非開啟網頁瀏覽器頁面）。 |
| 類別 | 類別 | 類別 | 顯示具有遠端通知的自訂動作。 <br>類別鍵可協助系統將該類別的動作顯示為警報介面中的按鈕。 |
| 自訂欄位 | custom_field1、custom_field2... | custom_field1、custom_field2... | 您要傳送至應用程式的任何自訂資料。 |
| 多媒體內容URL（影像、gif、音訊和視訊檔案）<br>（僅適用於iOS 10或更新版本） | media-attachment-url | 不適用 | 媒體檔案的URL，以新增豐富內容至通知。 <br>為此URL提供值時，可變內容標幟會自動傳送至裝載中。<br> （僅適用於iOS 10或更新版本） |
| 可變內容<br>（僅適用於iOS 10或更新版本） | 可變內容 | 不適用 | 應用程式中的通知服務擴充功能將會使用可變內容金鑰「截取」所有遠端通知，並可讓您處理/操控要求裝載的內容，這些內容之後可用來自訂通知。 此功能的使用案例包括下載和顯示多個媒體、解密推送裝載中出現的任何加密資料。 如需詳細資訊，請參閱[修改遠程通知的有效負載](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/ModifyingNotifications.html)。 <br>（僅適用於iOS 10或更新版本） |
| 可用內容 | 內容可用 | 不適用 | 選取此選項，可讓iOS應用程式在背景/暫停狀態時喚醒。 喚醒表示應用程式會在背景執行，而負責接收推播通知資料裝載的適當事件處理常式會取得控制，並可使用資料執行任何計算，包括但不限於建立自訂推播通知和顯示相同內容。 如需詳細資訊，請參閱[使用通知傳送喚醒應用程式](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CreatingtheNotificationPayload.html)。 |
| 多媒體內容URL（影像檔案）<br>（僅適用於Android） | 不適用 | media-attachment-url | 影像檔案的URL，以新增豐富內容至通知。 |
| 不適用 | _mId<br>_dId | _mId <br>_dId | broadlogId和deliveryId的值。<br>如果您的應用程式想要呼叫追蹤回傳，以追蹤推播通知的點按/開啟時間，則需要這些屬性。此資訊由應用程式伺服器計算並由內部傳送，使用者不需干預。<br>有關回傳的資訊，請參閱本 [頁面](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#PIIpostback)。 |

### 如何擷取行動應用程式程式碼中的裝載資訊 {#payload-information}

應用程式伺服器所傳送的裝載資訊會由行動應用程式程式碼在事件處理常式中接收，指出已接收推播通知。 此事件會依正在運作的行動平台而異，也依應用程式在前景或背景執行而定。 下列檔案可協助您根據使用案例，識別您要處理的事件處理常式。

* iOS應用程式：**處理[遠程通知](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/HandlingRemoteNotifications.html)中的遠程通知**&#x200B;部分。
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

**Android行動FCM應用程式範例**

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
