---
title: 瞭解Campaign Standard推播通知裝載結構
description: 瞭解行動應用程式中接收的裝載結構
audience: channels
feature: Instance Settings
role: Admin
level: Experienced
exl-id: a6515795-1006-4f27-bc44-5ae8b8edc018
source-git-commit: bfba6b156d020e8d2656239e713d2d24625bda54
workflow-type: tm+mt
source-wordcount: '1088'
ht-degree: 3%

---

# 瞭解推送通知裝載結構 {#push-payload}

Adobe Campaign可讓您在iOS和Android行動裝置上，將個人化和分段的推播通知傳送至行動應用程式（行動應用程式）。

行動應用程式收到的每個推播通知都會攜帶一些資訊，在傳送警報推播通知時，應用程式會使用這些資訊來顯示推播通知，而且極有可能還會進行一些進一步計算，尤其是在傳送無訊息推播通知時。

行動應用程式程式碼會在事件處理常式中接收這項資訊，指出已收到推播通知。 從Adobe Campaign Standard傳送推播通知時，行動應用程式中收到的資訊也可能包含Campaign Standard特定資訊，這些資訊可用來運用Campaign Standard提供的某些功能。 此外，裝載可包含行動應用程式可使用的自訂資料。

本檔案說明當推送通知成功從Adobe Campaign Standard傳送至應用程式時，行動應用程式中收到的裝載結構。

>[!NOTE]
>
>裝載結構依行動應用程式的型別而異(即iOS應用程式、啟用FCM的Android應用程式)。

## 推播裝載結構 {#push-payload-structure}

本節詳細說明各種行動平台的裝載範例結構，並說明其中所含的主要屬性。 這是行動應用程式程式碼中接收的裝載結構，在事件處理常式中指出已收到推播通知。

裝載屬性及其值會因推播通知進階選項中提供的設定而異。 本節也提供Campaign Standard UI中這些設定與裝載中屬性之間的對應，以釐清在Campaign Standard中設定選項時裝載會發生什麼變更。

### 適用於iOS行動應用程式 {#payload-structure-ios}

從Adobe Campaign傳送到iOS應用程式的&#x200B;**範例承載：**

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

**要與[iOS APNS Tester](https://pushtry.com/)**&#x200B;搭配使用的JSON裝載範例

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

裝載中最重要的部分是aps字典，它包含Apple定義的索引鍵，並用來決定接收通知的系統應如何提醒使用者（如果有的話）。 本節包含行動應用程式用來制定推播通知行為的預先定義金鑰。

您可以在Apple開發人員檔案中找到aps內屬性的深入詳細資料： [建立遠端通知承載](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CreatingtheNotificationPayload.html#//apple_ref/doc/uid/TP40008194-CH10-SW1)。

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

**使用[Google FCM測試器](https://pushtry.com/)**&#x200B;的JSON範例承載

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

裝載包含資料訊息，其中包含所有推播通知傳送內容，包括自訂索引鍵/值組，而使用者端應用程式必須處理該訊息以建置和顯示推播通知（如果需要）或新增任何其他商業邏輯。

若要瞭解Android裝載的各個層面，請參閱[傳訊概念與選項(fcm)](https://firebase.google.com/docs/cloud-messaging/concept-options)。

>[!NOTE]
>
>自2018年1月起，Android承載中已移除通知訊息的支援，以便啟用喚醒應用程式並將控制項傳遞至行動應用程式，而無需使用者與應用程式互動。

### Campaign Standard設定與裝載屬性之間的對應 {#mapping-payload}

| Campaign設定 | iOS中受影響的屬性 | Android中受影響的屬性 | 說明 |
|:-:|:-:|:-:|:-:|
| 訊息標題<br>訊息本文 | 警示→標題<br>警示→本文 | 標題<br>內文 | 此資料包含警示訊息的細節。<br>標題和正文索引鍵提供警示的內容。 |
| 播放音效 | 聲音 | 聲音 | 要播放警示的自訂音效。 |
| 徽章的值 | 徽章 | 徽章 | 用於標示應用程式圖示的整數值。 |
| 新增深層連結 | URI | 不適用 | 開發人員可讓您將使用者直接導向到應用程式內的內容（而非開啟網頁瀏覽器頁面）。 |
| 類別 | 類別 | 類別 | 顯示具有遠端通知的自訂動作。 <br>類別索引鍵可協助系統將該類別的動作顯示為警示介面中的按鈕。 |
| 自訂欄位 | custom_field1， custom_field2 ... | custom_field1， custom_field2 ... | 您要傳送至應用程式的任何自訂資料。 |
| 多媒體內容URL （影像、gif、音訊和視訊檔案）<br> (僅適用於iOS 10或更新版本) | media-attachment-url | 不適用 | 用於將豐富內容新增到通知的媒體檔案URL。 <br>在提供此URL的值時，可變內容旗標會自動傳送至裝載。 <br> (僅適用於iOS 10或更新版本) |
| 可變內容<br> (僅適用於iOS 10或更新版本) | mutable-content | 不適用 | 應用程式中的Notification Service擴充功能會使用可變內容金鑰「攔截」所有遠端通知，並允許您處理/操控要求裝載的內容，然後可以使用這些內容來自訂通知。 此功能的使用案例包括下載和顯示多個媒體、解密推播裝載中存在的任何加密資料。 如需詳細資訊，請參閱[修改遠端通知的承載](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/ModifyingNotifications.html)。 <br> (僅適用於iOS 10或更新版本) |
| 可用內容 | content-available | 不適用 | 選取此選項可讓iOS應用程式在處於背景/暫停狀態時喚醒。 喚醒表示應用程式會在背景執行，而負責接收推播通知資料裝載的適當事件處理常式會取得控制項，並可使用資料執行任何計算，包含但不限於建立自訂推播通知及顯示該通知。 更多資訊可在[通知傳送喚醒應用程式](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CreatingtheNotificationPayload.html)中找到。 |
| 多媒體內容URL （影像檔案）<br> （僅適用於Android） | 不適用 | media-attachment-url | 影像檔案的URL，用於將豐富內容新增至您的通知。 |
| 不適用 | _mId<br>_dId | _mId <br>_dId | broadlogId和deliveryId的值。<br>如果您的應用程式想要呼叫追蹤回傳，以追蹤何時點選/開啟推播通知，則需要這些屬性。 此資訊由應用程式伺服器內部計算及傳送，使用者毋須另行干預。<br>回傳資訊可在此[頁面](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback)中找到。 |

### 如何在行動應用程式程式碼中擷取裝載資訊 {#payload-information}

行動應用程式程式碼會在事件處理常式中接收應用程式伺服器傳送的裝載資訊，指出已收到推播通知。 此事件會因使用的行動平台而異，也會因應用程式是在前景或背景執行而有所不同。 以下檔案可協助您根據使用案例來識別您要處理的事件處理常式。

* iOS應用程式： **正在處理[遠端通知](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/HandlingRemoteNotifications.html)中的遠端通知**&#x200B;區段。
* Android應用程式： [在Android使用者端應用程式上接收訊息](https://firebase.google.com/docs/cloud-messaging/android/receive)

iOS行動應用程式的&#x200B;**範例**

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

Android Mobile FCM應用程式的&#x200B;**範例**

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
