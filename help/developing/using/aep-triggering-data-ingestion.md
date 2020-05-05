---
title: 透過 API 觸發資料引入
description: 瞭解如何透過API觸發資料擷取。
page-status-flag: never-activated
uuid: 867b1c4b-4c79-4c52-9d0a-ef71993e50a2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: configuring-channels
discoiquuid: 406c955a-b2d2-4099-9918-95f5fa966067
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 816d550d8bd0de085a47f97c1f6cc2fbb5e7acb9

---


# 透過 API 觸發資料引入 {#triggering-data-ingestion-apis}

>[!IMPORTANT]
>
>Adobe Experience Platform Data Connector目前正在測試中，可能會在不另行通知的情況下頻繁更新。 客戶必須在Azure上代管（目前僅限北美地區測試版）才能存取這些功能。 如果您想要存取，請聯絡Adobe客戶服務。

Adobe Campaign Standard可讓您透過API觸發資料映射的立即擷取，並擷取擷取擷取請求的狀態。

本頁介紹如何觸發和檢索資料映射的提取狀態。 如需Campaign Standard API的全域資訊，請參 [閱本節](../../api/using/get-started-apis.md)。

## 必要條件 {#prerequisites}

在使用API之前，資料對應必須先在Campaign Standard介面中設定並發佈。 有關這些內容的詳細資訊，請參閱下列章節：

* [映射定義](../../developing/using/aep-mapping-definition.md)
* [映射啟動](../../developing/using/aep-mapping-activation.md)

建立資料對應後，您必須停止它的執行，以便您可以隨時從API觸發它。 若要這麼做，請依照下列步驟進行：

1. 在「促銷活動標準」中，前往 **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Platform]** >功能 **[!UICONTROL Status of data export to platform]** 表。

1. 連按兩下資料對應以開啟它，然後按一下 **[!UICONTROL Stop]** 按鈕。

   ![](assets/aep_datamapping_stop.png)

1. 儲存變更

資料映射執行現在停止。 您可以使用Campaign Standard API手動觸發它。

## 開始立即擷取資料對應 {#starting-immediate-ingestion}

POST操作會觸發XDM映射到Adobe Experience Platform的立即接收：

`POST https://mc.adobe.io/<ORGANIZATION>/campaign/dataIngestion/xdmIngestion/<XDM Mapping ID>/ingest`

>[!NOTE]
>
>為了執行收錄的POST API呼叫，使用者必須具有 **SQL函式執行角色** ，此角色可由Campaign Standard管理員透過執行下列JS指令碼提供：
>
>`var sqlRoleObj = REST.head.roleBase.sql.get();
REST.head.securityGroup.Administrators.roles.post(sqlRoleObj);`

POST操作返回有關已建立請求狀態的資訊：

* 成功提交XDM映射的請求：

```
{
"requestId": <value>,
"info": "Ingestion request submitted successfully for the Mapping ID: <value>",
"status":"Success"
}
```

* XDM映射請求已在進行中：

```
{
"requestId": <value>,
"info": "Ingestion request already in progress for the Mapping ID: <value>",
"status":"In Progress"
}
```

* 請求失敗，因為XDM映射未發佈或已停止：

```
{
"info": "Unable to submit data ingestion request, XDM Mapping ID: <value> is not stopped",
"status": "Failed"
}
{
"info": "Unable to submit data ingestion request, XDM Mapping ID: <value> is not published",
"status": "Failed"
}
```

## 檢索提取請求的狀態 {#retrieving-status}

您可以使用GET操作和參數中所需的請求ID來擷取擷取請求的狀態：

```
GET https://mc.adobe.io/<ORGANIZATION>/campaign/dataIngestion/xdmIngestion/<XDM Mapping ID>/ingest
{"requestId"="<value>"}
```

>[!NOTE]
有關XDM映射請求狀態及其相關作業的詳細資訊，請參閱「Campaign Standard」介面的「資料匯出至平台的狀態」功能表 **!UICONTROL [(請參閱&#x200B;]**映射啟動[](../../developing/using/aep-mapping-activation.md))。

GET操作返回以下資訊：

* **batchId**: 只有在批次準備和上傳後發生失敗時，才會填入此欄位，
* **資訊**: XDM映射ID,
* **numRecords**: 已收錄的記錄數（僅限成功狀態）,
* **狀態**: 收錄請求狀態（成功／失敗／進行中）

對GET操作的可能響應包括：

* 收錄請求成功：

   ```
   {
   "batchId": "",
   "info": "Mapping Id: <value>. ",
   "numRecords": 15,
   "requestId": 3520,
   "status": "Success"
   }
   ```

* 收錄請求失敗，已收錄0個記錄：

   ```
   {
   "batchId": "",
   "info": "Mapping Id: <value>. ACP-880056 Failed to fetch the record from the database.",
   "numRecords": 0,
   "requestId": 3520,
   "status": "Failed"
   }
   ```

* 收錄請求失敗，有些記錄在批次下上傳：

   ```
   {
   "batchId": "<value>",
   "info": "Mapping Id: <value>. ACP-880096 Sync Job failed to upload. Please check the error in the Platform UI.",
   "numRecords": 0,
   "requestId": <value>,
   "status": "Failed"
   }
   ```

* 在收錄某些記錄後，收錄請求中止（這可能發生在當機情形中）:

   ```
   {
   "batchId": "",
   "info": "Mapping Id: <value>. Ingestion request aborted due to some issue with data ingestion service. Please submit a new request",
   "numRecords": 0,
   "requestId": <value>,
   "status": "Aborted"
   }
   ```

* 正在收錄請求（當請求在批次中上傳資料或批次準備請求時）:

   ```
   {
   "batchId": "",
   "info": "Mapping Id: <value>.",
   "numRecords": 0,
   "requestId": <value>,
   "status": "In Progress"
   }
   ```
