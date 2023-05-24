---
title: 瞭解Campaign Standard推送通知負載結構
description: 瞭解在移動應用程式中接收的負載的結構
audience: channels
feature: Instance Settings
role: Admin
level: Experienced
exl-id: a6515795-1006-4f27-bc44-5ae8b8edc018
source-git-commit: bfba6b156d020e8d2656239e713d2d24625bda54
workflow-type: tm+mt
source-wordcount: '1137'
ht-degree: 3%

---

# 瞭解推送通知裝載結構 {#push-payload}

Adobe Campaign允許您將iOS和Android移動設備上的個性化分段推送通知發送到移動應用程式（移動應用）。

在移動應用上收到的每個推送通知都包含一些資訊，如果發送了警報推送通知，應用程式將使用這些資訊來顯示推送通知，並且很可能還會執行一些進一步的計算，尤其是如果發送了靜默推送通知。

該資訊由移動應用代碼在事件處理程式中接收，該事件處理程式指示已接收推送通知。 當從Adobe Campaign Standard發送推送通知時，在移動應用中接收的資訊也可能包含Campaign Standard特定資訊，這些資訊可用於利用Campaign Standard提供的某些功能。 此外，負載可以包含可由移動應用使用的自定義資料。

本文檔描述在成功將推送通知發送到來自Adobe Campaign Standard的應用程式時在移動應用程式中接收的負載的結構。

>[!NOTE]
>
>負載結構因移動應用(即iOS應用、支援FCM的Android應用)類型而異。

## 推式有效載荷結構 {#push-payload-structure}

本節詳細介紹了用於各種移動平台的示例負載的結構，並描述了其中包含的主要屬性。 這是事件處理程式中移動應用代碼中接收的負載的結構，它指示已接收推式通知。

負載屬性及其值將根據推送通知高級選項中提供的配置而有所不同。 本節還提供Campaign StandardUI中這些配置與負載中屬性之間的映射，以便闡明在Campaign Standard中配置選項時負載將如何更改。

### 對於iOS移動應用 {#payload-structure-ios}

**從Adobe Campaign發送到iOS應用的負載示例：**

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

**要與一起使用的JSON示例負載 [iOSAPNS測試器](https://pushtry.com/)**

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

負載最重要的部分是aps字典，該字典包含Apple定義的鍵，用於確定接收通知的系統應如何向用戶發出警報。 本節包含由移動應用用於表達推送通知行為的預定義鍵。

有關aps中屬性的詳細資訊，請參閱Apple開發人員文檔： [建立遠程通知負載](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CreatingtheNotificationPayload.html#//apple_ref/doc/uid/TP40008194-CH10-SW1)。

### 適用於Android應用 {#payload-structure-android}

**從Adobe Campaign向Android應用發送負載示例**

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

**要使用的JSON示例負載 [GoogleFCM檢測儀](https://pushtry.com/)**

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

負載包含包括所有推送通知傳遞內容（包括自定義密鑰/值對）的資料消息，如果需要，客戶端應用必須處理該消息以生成和顯示推送通知，否則必須添加任何其他業務邏輯。

要瞭解android負載的各個方面，請參閱 [消息傳遞概念和選項(fcm)](https://firebase.google.com/docs/cloud-messaging/concept-options)。

>[!NOTE]
>
>自2018年1月起，Android負載中對通知消息的支援已被刪除，以便能夠喚醒應用並將控制權傳遞給移動應用，而無需用戶與應用交互。

### Campaign Standard配置和負載屬性之間的映射 {#mapping-payload}

| 市場活動配置 | 受影響的屬性在iOS | Android中的影響屬性 | 說明 |
|:-:|:-:|:-:|:-:|
| 消息標題 <br>消息正文 | 警報→標題 <br> 警→ | 標題 <br>體 | 此資料包含警報消息的具體資訊。<br>標題和正文鍵提供警報的內容。 |
| 播放音效 | 聲音 | 聲音 | 用於播放警報的自定義聲音。 |
| 徽章的值 | 徽章 | 徽章 | 用於標籤應用表徵圖的整數值。 |
| 新增深層連結 | URI | 納 | 開發人員可讓您將使用者直接導向到應用程式內的內容（而非開啟網頁瀏覽器頁面）。 |
| 類別 | 類別 | 類別 | 顯示具有遠程通知的自定義操作。 <br>類別鍵幫助系統將該類別的操作顯示為警報介面中的按鈕。 |
| 自定義欄位 | custom_field1、custom_field2... | custom_field1、custom_field2... | 要發送到應用的任何自定義資料。 |
| 富媒體內容URL（影像、gif、音頻和視頻檔案）<br>(僅適用於iOS10歲以上) | 媒體附件URL | 納 | 將富內容添加到通知的媒體檔案的URL。 <br>在為此URL提供值時，可變內容標誌將自動發送到負載中。 <br> (僅適用於iOS10歲以上) |
| 可變內容 <br> (僅適用於iOS10歲以上) | 可變內容 | 納 | 應用中的通知服務擴展將使用可變內容密鑰「截取」所有遠程通知，並允許您處理/處理請求負載的內容，然後，這些內容可用於自定義通知。 此功能的使用情形包括下載和顯示多個介質、解密在推送負載中存在的任何加密資料。 有關詳細資訊，請參閱 [修改遠程通知的負載](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/ModifyingNotifications.html)。 <br>(僅適用於iOS10歲以上) |
| 可用內容 | 內容可用 | 納 | 選擇此選項可在iOS應用處於後台/掛起狀態時喚醒它。 喚醒意味著應用程式在後台運行，負責接收推送通知資料負載的相應事件處理程式將獲得控制，並可以使用資料執行任何計算，包括但不限於構建自定義推送通知和顯示該資料。 有關詳細資訊，請參閱 [通過通知傳遞喚醒應用](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CreatingtheNotificationPayload.html)。 |
| 富媒體內容URL（影像檔案）<br>（僅適用於Android） | 納 | 媒體附件URL | 將豐富內容添加到通知的影像檔案的URL。 |
| 納 | _mId<br>_dId | _mId <br>_dId | broadlogId和deliveryId的值。<br>如果您的應用希望調用跟蹤後退來跟蹤按一下/開啟推送通知的時間，則需要這些屬性。 此資訊由應用伺服器在內部計算和發送，無需用戶干預。<br>有關回郵的資訊可在此中找到 [頁](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback)。 |

### 如何在移動應用代碼中檢索負載資訊 {#payload-information}

應用伺服器發送的負載資訊由移動應用代碼在事件處理程式中接收，該事件處理程式指示已接收到推送通知。 此事件將因正在處理的移動平台而異，也因應用程式是否在前台或後台運行而異。 以下文檔可幫助您根據使用案例確定要處理的事件處理程式。

* iOS應用程式： **處理遠程通知** 部分 [遠程通知](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/HandlingRemoteNotifications.html)。
* Android應用程式： [在Android客戶端應用上接收消息](https://firebase.google.com/docs/cloud-messaging/android/receive)

**iOS移動應用示例**

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

**Android Mobile FCM應用示例**

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
