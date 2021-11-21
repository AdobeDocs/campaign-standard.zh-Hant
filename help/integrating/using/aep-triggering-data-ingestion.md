---
title: 透過 API 觸發資料引入
description: 了解如何透過API觸發資料擷取。
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: d67a796a-0730-4502-802c-d0b3583dd1dc
source-git-commit: 13d419c5fc51845ee14f8a3b288f4c467e0a60d9
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 6%

---

# 透過 API 觸發資料引入 {#triggering-data-ingestion-apis}

>[!IMPORTANT]
>
>Adobe Experience Platform Data Connector目前為測試版，可能會經常更新，恕不另行通知。 客戶必須在Azure上托管（目前測試版僅供北美使用），才能存取這些功能。 如果您想要存取權限，請聯絡Adobe客戶服務。

Adobe Campaign Standard可讓您透過API觸發立即擷取資料對應，並擷取擷取請求的狀態。

本頁面說明如何觸發和擷取資料對應的擷取狀態。 如需Campaign StandardAPI的全域資訊，請參閱 [本節](../../api/using/get-started-apis.md).

## 先決條件 {#prerequisites}

使用API之前，必須先在Campaign Standard介面中設定並發佈資料對應。 如需詳細資訊，請參閱下列區段。

* [對應定義](../../integrating/using/aep-mapping-definition.md)
* [對應啟動](../../integrating/using/aep-mapping-activation.md)

建立資料對應後，您必須停止該資料對應的執行，以便隨時從API觸發。 要執行此操作，請依照下列步驟執行：

1. 在Campaign Standard中，前往 **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Platform]** > **[!UICONTROL Status of data export to platform]** 功能表。

1. 連按兩下資料對應以開啟，然後按一下 **[!UICONTROL Stop]** 按鈕。

   ![](assets/aep_datamapping_stop.png)

1. 儲存您的變更

資料對應執行現已停止。 您可以使用Campaign StandardAPI來手動觸發。

## 開始立即擷取資料對應 {#starting-immediate-ingestion}

系統會透過POST操作觸發立即擷取XDM對應至Adobe Experience Platform:

`POST https://mc.adobe.io/<ORGANIZATION>/campaign/dataIngestion/xdmIngestion/<XDM Mapping ID>/ingest`

>[!NOTE]
>
>若要執行內嵌POSTAPI呼叫，使用者必須具備 **SQL函式執行** 角色，可由Campaign Standard管理員透過執行下列JS指令碼來提供：
>
>
```
>var sqlRoleObj = REST.head.roleBase.sql.get();
>REST.head.securityGroup.Administrators.roles.post(sqlRoleObj);
>```

POST操作返回有關已建立請求狀態的資訊：

* 已成功提交XDM對應的請求：

```
{
"requestId": <value>,
"info": "Ingestion request submitted successfully for the Mapping ID: <value>",
"status":"Success"
}
```

* XDM對應的請求已在進行中：

```
{
"requestId": <value>,
"info": "Ingestion request already in progress for the Mapping ID: <value>",
"status":"In Progress"
}
```

* 請求失敗，因為XDM對應未發佈或已停止：

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

## 擷取擷取請求的狀態 {#retrieving-status}

擷取請求的狀態可透過GET操作和參數中所需的請求ID來擷取：

```
GET https://mc.adobe.io/<ORGANIZATION>/campaign/dataIngestion/xdmIngestion/<XDM Mapping ID>/ingest
{"requestId"="<value>"}
```

>[!NOTE]
>
>有關XDM對應請求狀態及其相關作業的詳細資訊，請參閱Campaign Standard介面中的 **[!UICONTROL Status of data export to platform]** 功能表(請參閱 [映射激活](../../integrating/using/aep-mapping-activation.md))。

GET操作返回以下資訊：

* **batchId**:只有在批次準備和上傳後發生失敗時，才會填入此欄位，
* **資訊**:XDM對應ID,
* **numRecords**:已擷取的記錄數（僅限成功狀態）,
* **狀態**:擷取請求狀態（成功/失敗/進行中）

對GET操作的可能響應為：

* 成功擷取請求：

   ```
   {
   "batchId": "",
   "info": "Mapping Id: <value>. ",
   "numRecords": 15,
   "requestId": 3520,
   "status": "Success"
   }
   ```

* 內嵌請求失敗，內嵌0個記錄：

   ```
   {
   "batchId": "",
   "info": "Mapping Id: <value>. ACP-880056 Failed to fetch the record from the database.",
   "numRecords": 0,
   "requestId": 3520,
   "status": "Failed"
   }
   ```

* 內嵌請求失敗，部分記錄在批次下上載：

   ```
   {
   "batchId": "<value>",
   "info": "Mapping Id: <value>. ACP-880096 Sync Job failed to upload. Please check the error in the Platform UI.",
   "numRecords": 0,
   "requestId": <value>,
   "status": "Failed"
   }
   ```

* 擷取某些記錄後擷取請求已中止（可能會在當機情況下發生）:

   ```
   {
   "batchId": "",
   "info": "Mapping Id: <value>. Ingestion request aborted due to some issue with data ingestion service. Please submit a new request",
   "numRecords": 0,
   "requestId": <value>,
   "status": "Aborted"
   }
   ```

* 正在內嵌請求（當請求以批次上傳資料，或正在為請求準備批次時）:

   ```
   {
   "batchId": "",
   "info": "Mapping Id: <value>.",
   "numRecords": 0,
   "requestId": <value>,
   "status": "In Progress"
   }
   ```
