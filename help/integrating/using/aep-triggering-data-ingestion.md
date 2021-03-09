---
solution: Campaign Standard
product: campaign
title: 透過 API 觸發資料引入
description: 瞭解如何透過API觸發資料擷取。
audience: administration
content-type: reference
topic-tags: configuring-channels
translation-type: tm+mt
source-git-commit: 35d61efce8d752ea30b7eaad55e6c23d4debd853
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 4%

---


# 透過 API 觸發資料引入 {#triggering-data-ingestion-apis}

>[!IMPORTANT]
>
>Adobe Experience Platform資料連接器目前正在測試中，可能會在不另行通知的情況下頻繁更新。 客戶必須在Azure上代管（目前僅限北美地區測試版）才能存取這些功能。 如果您想要存取，請聯絡Adobe客戶服務。

Adobe Campaign Standard允許您通過API觸發資料映射的立即接收，並檢索接收請求的狀態。

本頁介紹如何觸發和檢索資料映射的提取狀態。 有關Campaign StandardAPI的全局資訊，請參閱[本節](../../api/using/get-started-apis.md)。

## 必要條件 {#prerequisites}

使用API之前，必須先在Campaign Standard介面中設定並發佈資料對應。 有關這些內容的詳細資訊，請參閱下列章節：

* [映射定義](../../integrating/using/aep-mapping-definition.md)
* [映射啟動](../../integrating/using/aep-mapping-activation.md)

建立資料對應後，您必須停止它的執行，以便您可以隨時從API觸發它。 要執行此操作，請依照下列步驟執行：

1. 在Campaign Standard中，轉至&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Platform]** > **[!UICONTROL Status of data export to platform]**&#x200B;菜單。

1. 連按兩下資料對應以開啟它，然後按一下&#x200B;**[!UICONTROL Stop]**&#x200B;按鈕。

   ![](assets/aep_datamapping_stop.png)

1. 儲存變更

資料映射執行現在停止。 您可以使用Campaign StandardAPI來手動觸發。

## 開始立即提取資料映射{#starting-immediate-ingestion}

通過POST操作，可以立即提取XDM映射到Adobe Experience Platform:

`POST https://mc.adobe.io/<ORGANIZATION>/campaign/dataIngestion/xdmIngestion/<XDM Mapping ID>/ingest`

>[!NOTE]
>
>要執行收錄POSTAPI調用，用戶必須具有&#x200B;**SQL函式執行**&#x200B;角色，該角色可由Campaign Standard管理員通過執行以下JS指令碼提供：
>
>
```
>var sqlRoleObj = REST.head.roleBase.sql.get();
>REST.head.securityGroup.Administrators.roles.post(sqlRoleObj);
>```

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

## 檢索提取請求的狀態{#retrieving-status}

可以使用參數中的GET操作和所需請求ID來檢索提取請求的狀態：

```
GET https://mc.adobe.io/<ORGANIZATION>/campaign/dataIngestion/xdmIngestion/<XDM Mapping ID>/ingest
{"requestId"="<value>"}
```

>[!NOTE]
>
>有關XDM映射請求狀態及其相關作業的詳細資訊，請參見&#x200B;**[!UICONTROL Status of data export to platform]**&#x200B;菜單中的Campaign Standard介面（請參閱[映射激活](../../integrating/using/aep-mapping-activation.md)）。

GET操作返回以下資訊：

* **batchId**:只有在批次準備和上傳後發生失敗時，才會填入此欄位，
* **資訊**:XDM映射ID,
* **numRecords**:已收錄的記錄數（僅限成功狀態）,
* **狀態**:收錄請求狀態（成功／失敗／進行中）

對GET操作的可能響應包括：

* 成功收錄請求：

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
