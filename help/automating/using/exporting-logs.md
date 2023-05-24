---
title: 匯出記錄
description: 無論日誌資料是與交貨還是與預訂相關，都可以通過簡單的工作流導出。
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

無論日誌資料是與交貨還是與預訂相關，都可以通過簡單的工作流導出。 它使您能夠在您自己的報告或BI工具中分析您的市場活動結果。

>[!CAUTION]
>
>僅功能 [管理員](../../administration/using/users-management.md#functional-administrators), **[!UICONTROL Administration]** 角色和訪問權限 **全部** 設備可以訪問發送日誌、消息日誌、跟蹤日誌、排除日誌或訂閱日誌。 非管理員用戶可以針對這些日誌，但可以從連結的表（配置檔案、傳遞）開始。

使用 **[!UICONTROL Incremental query]** 只在每次執行工作流時檢索新日誌，並且 **[!UICONTROL Extract file]** 活動：定義輸出列，您可以獲取格式和所需的所有資料的檔案。 然後使用 **[!UICONTROL Transfer file]** 活動以檢索最終檔案。 每個工作流執行由 **[!UICONTROL Scheduler]**。

導出日誌操作可由標準用戶執行。 專用資源，如：廣播日誌、跟蹤日誌、排除日誌訂閱日誌和訂閱歷史日誌 **配置檔案** 只能由功能管理員管理。

1. 建立新工作流，如中所述 [此部分](../../automating/using/building-a-workflow.md#creating-a-workflow)。
1. 添加 **[!UICONTROL Scheduler]** 並根據需要設定。 下面是每月執行一次的示例。

   ![](assets/export_logs_scheduler.png)

1. 添加 **[!UICONTROL Incremental query]** 並配置它，以便它選擇所需的日誌。 例如，要選擇所有新廣播或更新的廣播（配置檔案交付日誌）:

   * 在 **[!UICONTROL Properties]** 頁籤，將目標資源更改為 **交付日誌** (broadLogRcp)。

      ![](assets/export_logs_query_properties.png)

   * 在 **[!UICONTROL Target]** 頁籤，設定條件以檢索與2016年或之後發送的交貨相對應的所有交貨日誌。 有關詳細資訊，請參閱 [編輯查詢](../../automating/using/editing-queries.md#creating-queries) 的子菜單。

      ![](assets/export_logs_query_target.png)

   * 在 **[!UICONTROL Processed data]** 頁籤 **[!UICONTROL Use a date field]** 選擇 **上次修改時間** 的子菜單。 在工作流的下一個執行中，將只檢索上次執行後將修改或建立的日誌。

      ![](assets/export_logs_query_processeddata.png)

      在第一次執行工作流程後，您可以在此索引標籤中看到下次執行時使用的最後一個執行日期。每次執行工作流程時，都會自動更新它。您仍然可以手動輸入新值來覆寫此值，以符合您的需求。

1. 添加 **[!UICONTROL Extract file]** 將導出檔案中查詢的資料的活動：

   * 在 **[!UICONTROL Extraction]** 頁籤。

      如果選擇 **[!UICONTROL Add date and time to the file name]** 選項，此名稱將自動與導出日期一起完成，以確保所有提取的檔案都是唯一的。 選擇要在檔案中導出的列。 您可以在此處選擇來自相關資源的資料，如交付或配置檔案資訊。

      >[!NOTE]
      >
      >要導出每個日誌的唯一標識符，請選擇 **[!UICONTROL Delivery log ID]** 的子菜單。

      要組織最終檔案，可應用排序。 例如，在日誌日期，如下例所示。

      ![](assets/export_logs_extractfile_extraction.png)

   * 在 **[!UICONTROL File structure]** 頁籤，定義輸出檔案的格式以滿足您的需要。

      核取 **[!UICONTROL Export labels instead of internal values of enumerations]** 選項，以備您匯出分項清單時使用。此選項可讓您擷取較短的標籤，與 ID 不同，這些標籤很容易理解。

1. 添加 **[!UICONTROL Transfer file]** 活動，並將其配置為將新建立的檔案從Adobe Campaign伺服器傳輸到您可以訪問它的其他位置，如SFTP伺服器。

   * 在 **[!UICONTROL General]** 頁籤 **[!UICONTROL File upload]** 因為目的是將檔案從Adobe Campaign發送到另一台伺服器。
   * 在 **[!UICONTROL Protocol]** 頁籤，指定傳輸參數並選擇 [外部帳戶](../../administration/using/external-accounts.md#creating-an-external-account) 的下界。

1. 添加 **[!UICONTROL End]** 活動，確保它正確結束並保存工作流。

   ![](assets/export_logs_example_workflow.png)

現在，您可以執行工作流並在外部伺服器上檢索輸出檔案。

**相關主題：**

[工作流程](../../automating/using/get-started-workflows.md)
