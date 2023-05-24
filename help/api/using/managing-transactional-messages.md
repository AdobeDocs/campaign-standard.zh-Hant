---
title: 管理異動訊息
description: 瞭解如何使用API管理事務性消息。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 00d39438-a232-49f1-ae5e-1e98c73397e3
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '672'
ht-degree: 3%

---

# 管理異動訊息 {#managing-transactional-messages}

建立並發佈事務性事件後，您需要將此事件的觸發整合到您的網站中。

>[!NOTE]
>
>事件配置在中詳細介紹 [此部分](../../channels/using/configuring-transactional-event.md)。

例如，您希望在購買購物車中的產品之前，當您的某個客戶離開您的網站時，會觸發「購物車放棄」事件。 要執行此操作，作為Web開發人員，必須使用REST事務性消息API。

1. 根據POST方法發送請求，該方法將觸發 [發送事務性事件](#sending-a-transactional-event)。
1. 對POST請求的響應包含主鍵，該主鍵允許您通過GET請求發送一個或多個請求。 這樣，您就能 [事件狀態](#transactional-event-status)。

## 發送事務事件 {#sending-a-transactional-event}

事務性事件通過具有以下URL結構的POST請求發送：

```
POST https://mc.adobe.io/<ORGANIZATION>/campaign/<transactionalAPI>/<eventID>
```

* **&lt;organization>**:您的個人組織ID。 請參閱[本節](../../api/using/must-read.md)。

* **&lt;transactionalapi>**:事務性消息API endPoint。

   事務性消息API終結點的名稱取決於實例配置。 它對應於值「mc」後跟您的個人組織ID。 讓我們以Geometrixx公司為例，其組織ID為&quot;geometrixx&quot;。 在這種情況下，POST請求如下：

   `POST https://mc.adobe.io/geometrixx/campaign/mcgeometrixx/<eventID>`

   請注意，事務性消息API終結點在API預覽過程中也可見。

* **&lt;eventid>**:要發送的事件類型。 建立事件配置時生成此ID(請參閱 [此部分](../../channels/using/configuring-transactional-event.md#creating-an-event))。

### POST請求標題

請求必須包含「內容類型：application/json&quot;頭。

例如，必須添加字元集 **utf-8**。 請注意，此值取決於您正在使用的REST應用程式。

```
-X POST \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-H 'Content-Type: application/json;charset=utf-8' \
-H 'Content-Length:79' \
```

### POST請求正文

事件資料包含在JSONPOST體中。 事件結構取決於其定義。 資源定義螢幕中的API預覽按鈕提供了請求示例。 請參閱[本節](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event)。

可以將以下可選參數添加到事件內容中，以管理連結到事件的事務性消息的發送：

* **到期** （可選）:在此日期之後，將取消事務事件的發送。
* **計畫** （可選）:從此日期開始，將處理事務性事件併發送事務性消息。

>[!NOTE]
>
>「到期」和「計畫」參數的值遵循ISO 8601格式。 ISO 8601指定使用大寫字母&quot;T&quot;分隔日期和時間。 但是，可以從輸入或輸出中刪除它，以便更好地讀取。

### 對POST請求的響應

POST響應返回建立事務事件時的事務事件狀態。 要檢索其當前狀態（事件資料、事件狀態……），請在POST請求中使用GET響應返回的主鍵：

`GET https://mc.adobe.io/<ORGANIZATION>/campaign/<transactionalAPI>/<eventID>/`

<br/>

***示例請求***

POST請求發送事件。

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

響應POST請求。

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

### 事務性事件狀態 {#transactional-event-status}

在響應中，「狀態」欄位允許您知道事件是否已處理：

* **掛起**:該事件處於掛起狀態 — 該事件在剛觸發時會進入此狀態。
* **處理**:該事件正在等待傳遞 — 它正被轉換為消息並且正在發送該消息。
* **暫停**:正在暫停事件進程。 它不再被處理，而是被保存在Adobe Campaign資料庫的隊列中。 如需詳細資訊，請參閱[本章節](../../channels/using/publishing-transactional-message.md#suspending-a-transactional-message-publication)。
* **處理**:已處理該事件並成功發送消息。
* **忽略**:交貨忽略了該事件，通常在地址處於隔離狀態時。
* **交付失敗**:處理事件時發生傳遞錯誤。
* **路由失敗**:路由階段失敗 — 例如，當找不到指定的事件類型時，可能會發生這種情況。
* **太舊**:該事件在處理之前已過期 — 這可能因各種原因而發生，例如，當發送失敗幾次（這導致事件不再是最新的）或當伺服器過載後無法再處理事件。
* **目標失敗**:Campaign Standard未能對用於消息目標的連結進行富集。
