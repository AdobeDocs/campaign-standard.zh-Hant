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
>只有具有&#x200B;**[!UICONTROL Administration]**&#x200B;角色且可存取&#x200B;**所有**&#x200B;單位的功能[管理員](../../administration/using/users-management.md#functional-administrators)才能存取傳送記錄檔、訊息記錄檔、追蹤記錄檔、排除或訂閱記錄檔。 非管理員使用者可以鎖定這些記錄，但從連結的表格（設定檔、傳送）開始。

使用&#x200B;**[!UICONTROL Incremental query]**&#x200B;來定義輸出欄時，只會在每次執行工作流程時擷取新記錄，並使用簡單的&#x200B;**[!UICONTROL Extract file]**&#x200B;活動，即可取得包含格式和您所需所有資料的檔案。 然後使用&#x200B;**[!UICONTROL Transfer file]**&#x200B;活動來擷取最終檔案。 每個工作流執行由&#x200B;**[!UICONTROL Scheduler]**&#x200B;計畫。

標準使用者可執行匯出記錄操作。 私人資源，例如：**設定檔**&#x200B;上的broadlog、追蹤記錄、排除記錄訂閱記錄和訂閱歷史記錄記錄只能由功能管理員管理。

1. 建立新工作流，如[本部分](../../automating/using/building-a-workflow.md#creating-a-workflow)中所述。
1. 新增&#x200B;**[!UICONTROL Scheduler]**&#x200B;活動，並根據您的需求加以設定。 以下是每月執行的範例。

   ![](assets/export_logs_scheduler.png)

1. 新增&#x200B;**[!UICONTROL Incremental query]**&#x200B;活動並加以設定，以便選取您需要的記錄檔。 例如，若要選取所有新的或更新的廣播（設定檔傳送記錄檔）:

   * 在&#x200B;**[!UICONTROL Properties]**&#x200B;標籤中，將目標資源變更為&#x200B;**傳送記錄**(broadLogRcp)。

      ![](assets/export_logs_query_properties.png)

   * 在&#x200B;**[!UICONTROL Target]**&#x200B;標籤中，設定條件以擷取與2016年或之後傳送之傳送相對應的所有傳送記錄。 如需詳細資訊，請參閱[編輯查詢](../../automating/using/editing-queries.md#creating-queries)區段。

      ![](assets/export_logs_query_target.png)

   * 在&#x200B;**[!UICONTROL Processed data]**&#x200B;標籤中，選擇&#x200B;**[!UICONTROL Use a date field]**&#x200B;並選擇&#x200B;**lastModified**&#x200B;欄位。 在工作流程的下一個執行時，將只擷取上次執行後已修改或建立的記錄檔。

      ![](assets/export_logs_query_processeddata.png)

      在第一次執行工作流程後，您可以在此索引標籤中看到下次執行時使用的最後一個執行日期。每次執行工作流程時，都會自動更新它。您仍然可以手動輸入新值來覆寫此值，以符合您的需求。

1. 新增&#x200B;**[!UICONTROL Extract file]**&#x200B;活動，以匯出檔案中查詢的資料：

   * 在&#x200B;**[!UICONTROL Extraction]**&#x200B;索引標籤中，指定檔案的名稱。

      如果您選取&#x200B;**[!UICONTROL Add date and time to the file name]**&#x200B;選項，此名稱將自動與匯出日期一併完成，以確保所有擷取的檔案都是唯一的。 選取要在檔案中匯出的欄。 您可以選取此處來自相關資源的資料，例如傳送或設定檔資訊。

      >[!NOTE]
      >
      >要導出每個日誌的唯一標識符，請選擇&#x200B;**[!UICONTROL Delivery log ID]**&#x200B;元素。

      若要組織最終檔案，您可以套用排序。 例如記錄日期，如下列範例所示。

      ![](assets/export_logs_extractfile_extraction.png)

   * 在&#x200B;**[!UICONTROL File structure]**&#x200B;標籤中，定義輸出檔案的格式以符合您的需求。

      核取 **[!UICONTROL Export labels instead of internal values of enumerations]** 選項，以備您匯出分項清單時使用。此選項可讓您擷取較短的標籤，與 ID 不同，這些標籤很容易理解。

1. 新增&#x200B;**[!UICONTROL Transfer file]**&#x200B;活動並將其設定為將新建立的檔案從Adobe Campaign伺服器傳輸至您可以存取的其他位置，例如SFTP伺服器。

   * 在&#x200B;**[!UICONTROL General]**&#x200B;索引標籤中，選取&#x200B;**[!UICONTROL File upload]** ，因為目的是將檔案從Adobe Campaign傳送至其他伺服器。
   * 在&#x200B;**[!UICONTROL Protocol]**&#x200B;標籤中，指定傳輸參數並選取要使用的[外部帳戶](../../administration/using/external-accounts.md#creating-an-external-account)。

1. 新增&#x200B;**[!UICONTROL End]**&#x200B;活動，以確保活動正確結束並儲存您的工作流程。

   ![](assets/export_logs_example_workflow.png)

您現在可以執行工作流程，並在外部伺服器上擷取輸出檔案。

**相關主題：**

[工作流程](../../automating/using/get-started-workflows.md)
