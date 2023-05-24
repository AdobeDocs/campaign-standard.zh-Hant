---
title: 透過 API 觸發資料引入
description: 瞭解如何通過API觸發資料接收。
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
>Adobe Experience Platform資料連接器目前處於測試版，可能需要頻繁更新，恕不另行通知。 客戶需要在Azure上托管（目前僅在北美試用版）才能訪問這些功能。 如果您想訪問，請聯繫Adobe客戶服務。

Adobe Campaign Standard允許您通過API觸發資料映射的即時接收，並檢索接收請求的狀態。

此頁介紹如何觸發和檢索資料映射的接收狀態。 有關Campaign StandardAPI的全局資訊，請參閱 [此部分](../../api/using/get-started-apis.md)。

## 必要條件 {#prerequisites}

在使用API之前，必須先在Campaign Standard介面中配置和發佈資料映射。 如需詳細資訊，請參閱下列區段。

* [對應定義](../../integrating/using/aep-mapping-definition.md)
* [對應啟動](../../integrating/using/aep-mapping-activation.md)

建立資料映射後，必須停止其運行，以便您可以隨時從API觸發它。 要執行此操作，請依照下列步驟執行：

1. 在Campaign Standard中，轉到 **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Platform]** > **[!UICONTROL Status of data export to platform]** 的子菜單。

1. 按兩下資料映射以將其開啟，然後按一下 **[!UICONTROL Stop]** 按鈕

   ![](assets/aep_datamapping_stop.png)

1. 保存更改

資料映射執行現在已停止。 可以使用Campaign StandardAPI手動觸發它。

## 開始立即接收資料映射 {#starting-immediate-ingestion}

立即接收映射到Adobe Experience Platform的XDM時，會觸發POST操作：

`POST https://mc.adobe.io/<ORGANIZATION>/campaign/dataIngestion/xdmIngestion/<XDM Mapping ID>/ingest`

>[!NOTE]
>
>要執行接收POSTAPI調用，用戶必須具有 **SQL函式執行** 角色，該角色可由Campaign Standard管理員通過執行以下JS指令碼提供：
>
>
```
>var sqlRoleObj = REST.head.roleBase.sql.get();
>REST.head.securityGroup.Administrators.roles.post(sqlRoleObj);
>```

POST操作返回有關已建立請求狀態的資訊：

* 已成功提交XDM映射的請求：

```
{
"requestId": <value>,
"info": "Ingestion request submitted successfully for the Mapping ID: <value>",
"status":"Success"
}
```

* XDM映射的請求已在進行中：

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

## 正在檢索攝取請求的狀態 {#retrieving-status}

可以通過GET操作和參數中的所需請求ID來檢索接收請求的狀態：

```
GET https://mc.adobe.io/<ORGANIZATION>/campaign/dataIngestion/xdmIngestion/<XDM Mapping ID>/ingest
{"requestId"="<value>"}
```

>[!NOTE]
>
>有關XDM映射請求狀態及其相關作業的詳細資訊，請參閱的Campaign Standard介面 **[!UICONTROL Status of data export to platform]** 菜單（請參見） [映射激活](../../integrating/using/aep-mapping-activation.md))。

GET操作返回以下資訊：

* **批ID**:僅當批處理準備和上載後失敗時才填充此欄位，
* **資訊**:XDM映射ID,
* **數記錄**:已接收的記錄數（僅限於成功狀態）,
* **狀態**:接收請求狀態（成功/失敗/正在進行）

可能對GET操作的響應是：

* 接收請求成功：

   ```
   {
   "batchId": "",
   "info": "Mapping Id: <value>. ",
   "numRecords": 15,
   "requestId": 3520,
   "status": "Success"
   }
   ```

* 接收請求失敗，接收0個記錄：

   ```
   {
   "batchId": "",
   "info": "Mapping Id: <value>. ACP-880056 Failed to fetch the record from the database.",
   "numRecords": 0,
   "requestId": 3520,
   "status": "Failed"
   }
   ```

* 接收請求失敗，某些記錄在批下上載：

   ```
   {
   "batchId": "<value>",
   "info": "Mapping Id: <value>. ACP-880096 Sync Job failed to upload. Please check the error in the Platform UI.",
   "numRecords": 0,
   "requestId": <value>,
   "status": "Failed"
   }
   ```

* 在接收某些記錄後，接收請求中止（在崩潰情形中可能會發生這種情況）:

   ```
   {
   "batchId": "",
   "info": "Mapping Id: <value>. Ingestion request aborted due to some issue with data ingestion service. Please submit a new request",
   "numRecords": 0,
   "requestId": <value>,
   "status": "Aborted"
   }
   ```

* 正在接收請求（當請求在批中上載資料或正在為請求準備批時）:

   ```
   {
   "batchId": "",
   "info": "Mapping Id: <value>.",
   "numRecords": 0,
   "requestId": <value>,
   "status": "In Progress"
   }
   ```
