---
title: 管理交易式訊息
description: 瞭解如何使用API管理交易訊息。
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d54f036c394db7abdba805ea2c21436c0ef5212c

---


# 管理交易式訊息 {#managing-transactional-messages}

## 關於交易式訊息傳遞

建立事件後，您必須將此事件的觸發整合至您的網站。

>[!NOTE]
>
>建立和發佈事件會顯示在「促銷活 <a href="https://helpx.adobe.com/campaign/standard/administration/using/configuring-transactional-messaging.html">動」檔案中</a>。

例如，您希望當客戶在購物車中購買產品之前離開您的網站時，觸發「購物車放棄」事件。 若要這麼做，您的網頁開發人員必須使用REST交易訊息API。

1. 開發人員根據POST方法傳送請求，觸發事 [務事件的傳送](#sending-a-transactional-event)。
1. 對POST要求的回應包含主要金鑰，可讓開發人員透過GET要求傳送一或多個要求。 這樣，他就可以獲得事件 [狀態](#transactional-event-status)。

## 傳送交易事件 {#sending-a-transactional-event}

事務性事件是透過具有下列URL結構的POST要求傳送：

```
POST https://mc.adobe.io/<ORGANIZATION>/campaign/<transactionalAPI>/<eventID>
```

* **&lt;ORGANIZATION>**:您的個人組織ID。 Refer to [this section](../../api/using/must-read.md).

* **&lt;transactionalAPI>**:交易訊息API endPoints。

   事務性消息API端點的名稱取決於實例配置。 它對應於值&quot;mc&quot;後跟您的個人組織ID。 讓我們以Geometrixx公司為例，其組織ID為&quot;geometrixx&quot;。 在這種情況下，開機自檢要求如下：

   `POST https://mc.adobe.io/geometrixx/campaign/mcgeometrixx/<eventID>`

   （請注意，交易訊息API端點也會在API預覽期間顯示）

* **&lt;eventID>**:您要傳送的事件類型。 此ID是在建立事件定義時產生。 請參閱促銷活 [動檔案](https://helpx.adobe.com/campaign/standard/administration/using/configuring-transactional-messaging.html)。

### POST請求標題

請求必須包含「內容類型：application/json」標題。

您必須新增字元集，例如 **utf-8**。 請注意，此值取決於您使用的REST應用程式。

```
-X POST \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-H 'Content-Type: application/json;charset=utf-8' \
-H 'Content-Length:79' \
```

### POST請求正文

事件資料包含在JSON POST內文中。 事件結構取決於其定義。 資源定義畫面中的API預覽按鈕提供請求範例。 請參閱促銷活 [動檔案](https://helpx.adobe.com/campaign/standard/administration/using/configuring-transactional-messaging.html)。

可以將下列可選參數添加到事件內容中，以管理連結到事件的事務性消息的發送：

* **到期** （可選）:在此日期之後，事務性事件的傳送將被取消。
* **scheduled** （可選）:從此日期開始，將處理事務性事件併發送事務性消息。

>[!NOTE]
>
>&quot;expiration&quot;和&quot;scheduled&quot;參數的值遵循ISO 8601格式。 ISO 8601指定使用大寫字母&quot;T&quot;來分隔日期和時間。 不過，您可將它從輸入或輸出中移除，以提高可讀性。

### 對POST請求的回應

POST響應返回建立事務事件時的事務事件狀態。 要檢索其當前狀態（事件資料、事件狀態……），請在GET請求中使用POST響應返回的主鍵：

`GET https://mc.adobe.io/<ORGANIZATION>/campaign/<transactionalAPI>/<eventID>/`

<br/>

***請求範例&#x200B;***

POST要求傳送事件。

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/mcAdobe/EVTcartAbandonment \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-H 'Content-Type: application/json;charset=utf-8' \
-H 'Content-Length:79'

{
  "email":"test@example.com",
  "scheduled":"2017-12-01 08:00:00.768Z",
  "expiration":"2017-12-31 08:00:00.768Z",
  "ctx":
  {
    "cartAmount": "$ 125",
    "lastProduct": "Leather motorbike jacket",
    "firstName": "Jack"
  }
}
```

回應POST請求。

```
{
  "PKey":"<PKEY>",
  "ctx":
  {
    "cartAmount": "",
    "lastProduct": "",
    "firstName": ""
  }
  "email":"",
  "scheduled":"2017-12-01 08:00:00.768Z",
  "expiration":"2017-12-31 08:00:00.768Z",
  "href": "mcAdobe/EVTcartAbandonment/<PKEY>",
  "serverUrl":" https://myserver.com ",
  "status":"pending",
  "type":""
}
```

### 交易事件狀態 {#transactional-event-status}

在回應中，「狀態」欄位可讓您知道事件是否已處理：

* **待定**:事件擱置中——事件在剛觸發時進入此狀態。
* **處理**:事件正在等待傳送——它正被轉換為訊息並傳送訊息。
* **暫停**:正在暫停事件進程。 它不再處理，但會保留在Adobe Campaign資料庫的佇列中。 如需詳細資訊，請參閱促銷活動 [檔案](https://helpx.adobe.com/campaign/standard/channels/using/event-transactional-messages.html#unpublishing-a-transactional-message)。
* **已處理**:已處理事件並成功傳送訊息。
* **忽略**:傳送會忽略事件，通常是在隔離地址時。
* **deliveryFailed**:處理事件時發生傳送錯誤。
* **routingFailed**:路由階段失敗——例如，當找不到指定的事件類型時，可能會發生這種情況。
* **tooOld**:該事件在處理之前過期——可能因各種原因而發生，例如，當傳送失敗數次（這會導致事件不再是最新狀態），或當伺服器過載後無法再處理事件。
* **targetingFailed**:「促銷活動標準」無法擴充用於訊息定位的連結。
