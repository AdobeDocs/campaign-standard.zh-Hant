---
title: 管理異動訊息
description: 了解如何使用API管理交易式訊息。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 00d39438-a232-49f1-ae5e-1e98c73397e3
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '678'
ht-degree: 3%

---

# 管理異動訊息 {#managing-transactional-messages}

## 關於異動訊息傳送

建立並發佈交易式事件後，您必須將此事件的觸發整合至您的網站。

>[!NOTE]
>
>在[此部分](../../channels/using/configuring-transactional-event.md)中顯示配置事件。

例如，您希望當客戶在購物車中購買產品之前離開您的網站時，觸發「購物車放棄」事件。 若要這麼做，您的網頁開發人員必須使用REST交易式訊息API。

1. 開發人員根據POST方法傳送請求，觸發交易事件](#sending-a-transactional-event)的[傳送。
1. 對POST要求的回應包含主要金鑰，可讓開發人員透過GET要求傳送一或多個要求。 這樣他就能取得[事件狀態](#transactional-event-status)。

## 傳送交易式事件 {#sending-a-transactional-event}

交易式事件會透過具有下列URL結構的POST請求傳送：

```
POST https://mc.adobe.io/<ORGANIZATION>/campaign/<transactionalAPI>/<eventID>
```

* **&lt;organization>**:您的個人組織ID。請參閱[本節](../../api/using/must-read.md)。

* **&lt;transactionalapi>**:交易式訊息API endPoints。

   交易式訊息API端點的名稱取決於您的執行個體設定。 它對應至「mc」值，後面接著您的個人組織ID。 以Geometrixx公司為例，其組織ID為&quot;geometrixx&quot;。 在這種情況下，POST請求如下：

   `POST https://mc.adobe.io/geometrixx/campaign/mcgeometrixx/<eventID>`

   （請注意，交易式訊息API端點也會在API預覽期間顯示）

* **&lt;eventid>**:您要傳送的事件類型。此ID會在建立事件設定時產生（請參閱[此區段](../../channels/using/configuring-transactional-event.md#creating-an-event)）。

### POST請求標題

請求必須包含「內容類型：application/json」標題。

您必須新增字元集，例如&#x200B;**utf-8**。 請注意，此值取決於您使用的REST應用程式。

```
-X POST \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-H 'Content-Type: application/json;charset=utf-8' \
-H 'Content-Length:79' \
```

### POST要求內文

事件資料包含在JSONPOST內文中。 事件結構取決於其定義。 資源定義畫面中的API預覽按鈕提供請求範例。 請參閱[本節](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event)。

可將下列選用參數新增至事件內容，以管理連結至事件的交易式訊息的傳送：

* **過期** （選用）:在此日期之後，交易式事件的傳送將會取消。
* **已排程** （選用）:從此日期起，將處理交易式事件，並傳送交易式訊息。

>[!NOTE]
>
>「過期」和「已排程」參數的值遵循ISO 8601格式。 ISO 8601指定使用大寫字母&quot;T&quot;來分隔日期和時間。 但可從輸入或輸出中移除，以提高可讀性。

### 回應POST要求

POST回應會在建立交易式事件時傳回其狀態。 若要擷取其目前狀態（事件資料、事件狀態……），請在GET請求中使用POST回應傳回的主索引鍵：

`GET https://mc.adobe.io/<ORGANIZATION>/campaign/<transactionalAPI>/<eventID>/`

<br/>

***範例要求***

POST傳送事件的要求。

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

回應POST要求。

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

### 交易式事件狀態 {#transactional-event-status}

在回應中，「狀態」欄位可讓您知道事件是否已處理：

* **待定**:事件擱置中 — 事件剛觸發時就會進入此狀態。
* **處理**:事件處於待定傳送狀態 — 該事件正在轉換為訊息並傳送訊息。
* **暫停**:事件進程正在暫停。不再處理，而是會保留在Adobe Campaign資料庫的佇列中。 如需詳細資訊，請參閱[本章節](../../channels/using/publishing-transactional-message.md#suspending-a-transactional-message-publication)。
* **已處理**:已處理事件且已成功傳送訊息。
* **忽略**:傳送會忽略事件，通常是在地址處於隔離狀態時。
* **deliveryFailed**:處理事件時發生傳送錯誤。
* **routingFailed**:路由階段失敗 — 例如，當找不到指定的事件類型時，可能會發生此情況。
* **tooOld**:事件在能夠處理前已過期 — 這可能會因多種原因而發生，例如，當傳送失敗多次（這會導致事件不再為最新狀態），或當伺服器變得超載後無法再處理事件。
* **targetingFailed**:Campaign Standard無法擴充正用於訊息定位的連結。
