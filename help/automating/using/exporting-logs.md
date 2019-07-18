---
title: 匯出記錄檔
seo-title: 匯出記錄檔
description: 匯出記錄檔
seo-description: 記錄資料(不論是與傳送或訂閱相關)都可以透過簡單的工作流程匯出。
page-status-flag: 從未啓動
uuid: 954e919c-0a33-47c3-9a3c-63c7a2a4edic4
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: reference
topic-tags: 匯入-匯出資料
discoiquuid: ca8a95d8-523f-4085-a2 fc-e1 d8262 cfbae
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 36727e82d3aa73add6116fa2916752ff0e407d9d

---


# Exporting logs{#exporting-logs}

記錄資料(不論是與傳送或訂閱相關)都可以透過簡單的工作流程匯出。它可讓您在自己的報表或BI工具中分析促銷活動的結果。

By using an **[!UICONTROL Incremental query]** that only retrieves new logs every time the workflow is executed and a simple **[!UICONTROL Extract file]** activity to define the output columns, you can get a file with the format and all the data you need. Then use a **[!UICONTROL Transfer file]** activity to retrieve the final file. Each workflow execution is planned by a **[!UICONTROL Scheduler]**.

匯出記錄作業可由標準使用者執行。Private resources such as: broadlogs, tracking logs, exclusion logs subscription logs and subscription history logs on **Profiles** can only be managed by functional administrator.

1. Create a new workflow as detailed in [this section](../../automating/using/building-a-workflow.md#creating-a-workflow).
1. Add a **[!UICONTROL Scheduler]** activity and set it according to your needs. 以下是每月執行的範例。

   ![](assets/export_logs_scheduler.png)

1. Add an **[!UICONTROL Incremental query]** activity and configure it so that it selects the logs you need. 例如，若要選取所有新的或更新的群組(描述檔傳送記錄檔)：

   * **[!UICONTROL Properties]** 在標籤中，將目標資源變更為 **「傳送記錄檔」** (BroadlogRCP)。

      ![](assets/export_logs_query_properties.png)

   * **[!UICONTROL Target]** 在標籤中，設定條件來擷取所有對應於2016年或之後傳送之傳送的傳送記錄檔。For more information, refer to the [Editing queries](../../automating/using/editing-queries.md#creating-queries) section.

      ![](assets/export_logs_query_target.png)

   * In the **[!UICONTROL Processed data]** tab, select **[!UICONTROL Use a date field]** and choose the **lastModified** field. 在工作流程的下一個執行階段中，只會擷取將在最後一次執行後修改或建立的記錄檔。

      ![](assets/export_logs_query_processeddata.png)

      第一次執行工作流程後，您可以在此標籤中看到上次執行的執行日期。每次執行工作流程時都會自動更新它。您仍有可能透過手動輸入新值來覆蓋此值，使其符合您的需求。

1. Add an **[!UICONTROL Extract file]** activity that will export the queried data in a file:

   * In the **[!UICONTROL Extraction]** tab, specify the name of the file. 此名稱會自動填入匯出日期，以確保所有擷取的檔案都是唯一的。

      選取您要在檔案中匯出的欄。您可以在此處選取來自相關資源的資料，例如傳送或描述檔資訊。若要組織最終檔案，您可以套用排序。例如記錄日期上的範例，如下方範例所示。

      ![](assets/export_logs_extractfile_extraction.png)

      >[!NOTE]
      >
      >無法匯出記錄資源的唯一識別碼(主鍵)。

   * **[!UICONTROL File structure]** 在標籤中，定義輸出檔案格式以符合您的需求。

      Check the **[!UICONTROL Export labels instead of internal values of enumerations]** option in case you export enumeration values. 此選項可擷取較短的標籤，而不需使用ID而易於瞭解。

1. Add a **[!UICONTROL Transfer file]** activity and configure it to transfer the newly created file from the Adobe Campaign server to another location where you can access it, such as a SFTP server.

   * In the **[!UICONTROL General]** tab, select **[!UICONTROL File upload]** as the purpose is to send the file from Adobe Campaign to another server.
   * **[!UICONTROL Protocol]** 在標籤中，指定轉移參數並選取要使用的 [外部帳戶](../../administration/using/external-accounts.md#creating-an-external-account) 。

1. Add an **[!UICONTROL End]** activity to make sure it properly ends and save your workflow.

   ![](assets/export_logs_example_workflow.png)

您現在可以在外部伺服器上執行工作流程並擷取輸出檔案。

**相關主題：**

[工作流程](../../automating/using/discovering-workflows.md)
