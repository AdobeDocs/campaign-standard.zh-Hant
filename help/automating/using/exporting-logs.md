---
title: 匯出日誌
description: 記錄資料，不論是與傳送或訂閱相關，都可透過簡單的工作流程匯出。
page-status-flag: 從未激活
uuid: 954e919c-0a33-47c3-9a3c-63c7a2a4edc4
contentOwner: 紹維亞
products: SG_CAMPAIGN/STANDARD
audience: 自動化
content-type: 參考
topic-tags: 導入和導出資料
discoiquuid: ca8a95d8-523f-4085-a2fc-e1d8262cfbae
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 匯出日誌{#exporting-logs}

記錄資料，不論是與傳送或訂閱相關，都可透過簡單的工作流程匯出。 它可讓您在自己的報表或BI工具中分析促銷活動的結果。

使用只 **[!UICONTROL Incremental query]** 在每次執行工作流時檢索新日誌和用簡單活動來定義輸出列的 **[!UICONTROL Extract file]** 檔案，可以獲得格式和所需的所有資料的檔案。 然後使用活 **[!UICONTROL Transfer file]** 動來擷取最終檔案。 每個工作流執行都由計畫 **[!UICONTROL Scheduler]**。

出口日誌操作可由標準用戶執行。 私人資源，例如：profiles上的broadlogs、追蹤記錄、排除記錄訂閱記錄和訂閱記 **錄記錄** ，只能由功能管理員管理。

1. 建立新的工作流程，如本節 [所述](../../automating/using/building-a-workflow.md#creating-a-workflow)。
1. 新增活 **[!UICONTROL Scheduler]** 動並根據您的需求加以設定。 以下是每月執行的範例。

   ![](assets/export_logs_scheduler.png)

1. 新增活 **[!UICONTROL Incremental query]** 動並加以設定，以便選擇您需要的記錄檔。 例如，要選擇所有新的或更新的廣播（配置檔案交付日誌）:

   * 在標籤 **[!UICONTROL Properties]** 中，將目標資源變更為 **傳送記錄** (broadLogRcp)。

      ![](assets/export_logs_query_properties.png)

   * 在標籤 **[!UICONTROL Target]** 中，設定條件以擷取與2016年或之後傳送之傳送相對應的所有傳送記錄。 如需詳細資訊，請參閱「編 [輯查詢](../../automating/using/editing-queries.md#creating-queries) 」一節。

      ![](assets/export_logs_query_target.png)

   * 在標籤中 **[!UICONTROL Processed data]** ，選擇並 **[!UICONTROL Use a date field]** 選擇最後修 **改的欄位** 。 在工作流的下一個執行中，將只檢索在上次執行後將修改或建立的日誌。

      ![](assets/export_logs_query_processeddata.png)

      在第一次執行工作流程後，您可以在此標籤中看到下次執行時使用的最後一個執行日期。 每次執行工作流程時，都會自動更新它。 您仍然可以手動輸入新值來覆寫此值，以符合您的需求。

1. 新增將 **[!UICONTROL Extract file]** 匯出檔案中查詢資料的活動：

   * 在標 **[!UICONTROL Extraction]** 簽中，指定檔案名稱。 此名稱將自動填入匯出日期，以確保所有解壓縮的檔案都是唯一的。

      選擇要在檔案中導出的列。 您可以選取來自相關資源（例如傳送或描述檔資訊）的資料。 要組織最終檔案，可以應用排序。 例如，在記錄日期，如下例所示。

      ![](assets/export_logs_extractfile_extraction.png)

      >[!NOTE]
      >
      >無法導出日誌資源的唯一標識符（主鍵）。

   * 在標籤 **[!UICONTROL File structure]** 中，定義輸出檔案的格式以符合您的需求。

      勾選選 **[!UICONTROL Export labels instead of internal values of enumerations]** 選項，以備您匯出列舉值時使用。 此選項可讓您擷取較短的標籤，這些標籤很容易理解，而非ID。

1. 新增活 **[!UICONTROL Transfer file]** 動並設定它，將新建立的檔案從Adobe Campaign伺服器傳輸至您可存取的其他位置，例如SFTP伺服器。

   * 在標籤 **[!UICONTROL General]** 中，選 **[!UICONTROL File upload]** 擇目的是將檔案從Adobe Campaign傳送至其他伺服器。
   * 在標籤 **[!UICONTROL Protocol]** 中，指定傳輸參數並選擇要 [使用的外部](../../administration/using/external-accounts.md#creating-an-external-account) 帳戶。

1. 新增活 **[!UICONTROL End]** 動，以確保活動正常結束並儲存您的工作流程。

   ![](assets/export_logs_example_workflow.png)

您現在可以在外部伺服器上執行工作流程並擷取輸出檔案。

**相關主題：**

[工作流程](../../automating/using/discovering-workflows.md)
