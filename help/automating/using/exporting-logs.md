---
title: 匯出記錄
description: 記錄資料（無論是與傳送或訂閱相關）可透過簡單的工作流程匯出。
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
feature: Workflows
role: Data Architect
level: Experienced
exl-id: d74e2a2c-3ce1-44d6-a058-67b0600360ca
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '597'
ht-degree: 14%

---

# 匯出記錄{#exporting-logs}

記錄資料（無論是與傳送或訂閱相關）可透過簡單的工作流程匯出。 它可讓您在自己的報表或BI工具中分析促銷活動的結果。

>[!CAUTION]
>
>僅功能 [管理員](../../administration/using/users-management.md#functional-administrators)，使用 **[!UICONTROL Administration]** 角色和存取權 **全部** 裝置可存取傳送記錄檔、訊息記錄檔、追蹤記錄檔、排除或訂閱記錄檔。 非管理員使用者可以鎖定這些記錄，但從連結的表格（設定檔、傳送）開始。

使用 **[!UICONTROL Incremental query]** 只會在每次執行工作流程時擷取新記錄，且簡單 **[!UICONTROL Extract file]** 活動來定義輸出欄，您可以取得包含格式和您所需所有資料的檔案。 然後使用 **[!UICONTROL Transfer file]** 擷取最終檔案的活動。 每個工作流程執行由 **[!UICONTROL Scheduler]**.

標準使用者可執行匯出記錄操作。 私人資源，例如：broadlogs，追蹤記錄，排除記錄訂閱記錄和訂閱記錄記錄 **設定檔** 只能由功能管理員管理。

1. 建立新工作流程，詳情請參閱 [本節](../../automating/using/building-a-workflow.md#creating-a-workflow).
1. 新增 **[!UICONTROL Scheduler]** 活動，並根據您的需求加以設定。 以下是每月執行的範例。

   ![](assets/export_logs_scheduler.png)

1. 新增 **[!UICONTROL Incremental query]** 活動並加以設定，以便選取您需要的記錄檔。 例如，若要選取所有新的或更新的廣播（設定檔傳送記錄檔）:

   * 在 **[!UICONTROL Properties]** 頁簽，將目標資源更改為 **傳送記錄檔** (broadLogRcp)。

      ![](assets/export_logs_query_properties.png)

   * 在 **[!UICONTROL Target]** 索引標籤，設定條件以擷取與2016年或之後傳送之傳送相對應的所有傳送記錄。 如需詳細資訊，請參閱 [編輯查詢](../../automating/using/editing-queries.md#creating-queries) 區段。

      ![](assets/export_logs_query_target.png)

   * 在 **[!UICONTROL Processed data]** 索引標籤，選取 **[!UICONTROL Use a date field]** 並選擇 **lastModified** 欄位。 在工作流程的下一個執行時，將只擷取上次執行後已修改或建立的記錄檔。

      ![](assets/export_logs_query_processeddata.png)

      在第一次執行工作流程後，您可以在此索引標籤中看到下次執行時使用的最後一個執行日期。每次執行工作流程時，都會自動更新它。您仍然可以手動輸入新值來覆寫此值，以符合您的需求。

1. 新增 **[!UICONTROL Extract file]** 將匯出檔案中查詢資料的活動：

   * 在 **[!UICONTROL Extraction]** 頁簽，指定檔案的名稱。

      如果您選取 **[!UICONTROL Add date and time to the file name]** 選項，此名稱將自動與匯出日期一併完成，以確保所有擷取的檔案都是唯一的。 選取要在檔案中匯出的欄。 您可以選取此處來自相關資源的資料，例如傳送或設定檔資訊。

      >[!NOTE]
      >
      >若要匯出每個記錄檔的唯一識別碼，請選取 **[!UICONTROL Delivery log ID]** 元素。

      若要組織最終檔案，您可以套用排序。 例如記錄日期，如下列範例所示。

      ![](assets/export_logs_extractfile_extraction.png)

   * 在 **[!UICONTROL File structure]** 頁簽，定義輸出檔案的格式以符合您的需求。

      核取 **[!UICONTROL Export labels instead of internal values of enumerations]** 選項，以備您匯出分項清單時使用。此選項可讓您擷取較短的標籤，與 ID 不同，這些標籤很容易理解。

1. 新增 **[!UICONTROL Transfer file]** 活動並設定它，以將新建立的檔案從Adobe Campaign伺服器傳輸至您可以存取的其他位置，例如SFTP伺服器。

   * 在 **[!UICONTROL General]** 索引標籤，選取 **[!UICONTROL File upload]** 目的是將檔案從Adobe Campaign傳送至其他伺服器。
   * 在 **[!UICONTROL Protocol]** 頁簽，指定傳輸參數並選擇 [外部帳戶](../../administration/using/external-accounts.md#creating-an-external-account) 來使用。

1. 新增 **[!UICONTROL End]** 活動，確保活動正確結束並儲存您的工作流程。

   ![](assets/export_logs_example_workflow.png)

您現在可以執行工作流程，並在外部伺服器上擷取輸出檔案。

**相關主題：**

[工作流程](../../automating/using/get-started-workflows.md)
