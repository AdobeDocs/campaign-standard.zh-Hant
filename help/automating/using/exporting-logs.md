---
solution: Campaign Standard
product: campaign
title: 匯出日誌
description: 記錄資料，不論是與傳送或訂閱相關，都可透過簡單的工作流程匯出。
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '597'
ht-degree: 14%

---


# 匯出日誌{#exporting-logs}

記錄資料，不論是與傳送或訂閱相關，都可透過簡單的工作流程匯出。 它可讓您在自己的報表或BI工具中分析促銷活動的結果。

>[!CAUTION]
>
>只有具有&#x200B;**[!UICONTROL Administration]**&#x200B;角色和&#x200B;**所有**&#x200B;單元訪問權的[管理員](../../administration/using/users-management.md#functional-administrators)才能訪問發送日誌、消息日誌、跟蹤日誌、排除或訂閱日誌。 非管理員使用者可以定位這些記錄檔，但是從連結的表格（描述檔、傳送）開始。

通過使用&#x200B;**[!UICONTROL Incremental query]**（每次執行工作流時僅檢索新日誌）和簡單的&#x200B;**[!UICONTROL Extract file]**&#x200B;活動來定義輸出列，您可以獲得具有格式和所需所有資料的檔案。 然後使用&#x200B;**[!UICONTROL Transfer file]**&#x200B;活動來擷取最終檔案。 每個工作流執行都由&#x200B;**[!UICONTROL Scheduler]**&#x200B;計畫。

出口日誌操作可由標準用戶執行。 私人資源，例如：**Profiles**&#x200B;上的broadlog、跟蹤日誌、排除日誌訂閱日誌和訂閱歷史日誌只能由功能管理員管理。

1. 如[本節](../../automating/using/building-a-workflow.md#creating-a-workflow)中所述，建立新工作流。
1. 新增&#x200B;**[!UICONTROL Scheduler]**&#x200B;活動，並根據您的需求加以設定。 以下是每月執行的範例。

   ![](assets/export_logs_scheduler.png)

1. 新增&#x200B;**[!UICONTROL Incremental query]**&#x200B;活動並加以設定，以選擇您需要的記錄檔。 例如，要選擇所有新的或更新的廣播（配置檔案交付日誌）:

   * 在&#x200B;**[!UICONTROL Properties]**&#x200B;標籤中，將目標資源更改為&#x200B;**Delivery logs**(broadLogRcp)。

      ![](assets/export_logs_query_properties.png)

   * 在&#x200B;**[!UICONTROL Target]**&#x200B;標籤中，設定條件以擷取與2016年或之後傳送之傳送相對應的所有傳送記錄。 有關詳細資訊，請參閱[編輯查詢](../../automating/using/editing-queries.md#creating-queries)部分。

      ![](assets/export_logs_query_target.png)

   * 在&#x200B;**[!UICONTROL Processed data]**&#x200B;標籤中，選擇&#x200B;**[!UICONTROL Use a date field]**&#x200B;並選擇&#x200B;**lastModified**&#x200B;欄位。 在工作流的下一個執行中，將只檢索在上次執行後將修改或建立的日誌。

      ![](assets/export_logs_query_processeddata.png)

      在第一次執行工作流程後，您可以在此索引標籤中看到下次執行時使用的最後一個執行日期。每次執行工作流程時，都會自動更新它。您仍然可以手動輸入新值來覆寫此值，以符合您的需求。

1. 新增&#x200B;**[!UICONTROL Extract file]**&#x200B;活動，將查詢的資料匯出至檔案：

   * 在&#x200B;**[!UICONTROL Extraction]**&#x200B;標籤中，指定檔案的名稱。

      如果選擇&#x200B;**[!UICONTROL Add date and time to the file name]**&#x200B;選項，此名稱將自動與導出日期一起完成，以確保所有提取的檔案都是唯一的。 選擇要在檔案中導出的列。 您可以選取來自相關資源（例如傳送或描述檔資訊）的資料。

      >[!NOTE]
      >
      >要導出每個日誌的唯一標識符，請選擇&#x200B;**[!UICONTROL Delivery log ID]**&#x200B;元素。

      要組織最終檔案，可以應用排序。 例如，在記錄日期，如下例所示。

      ![](assets/export_logs_extractfile_extraction.png)

   * 在&#x200B;**[!UICONTROL File structure]**&#x200B;標籤中，定義輸出檔案的格式以符合您的需求。

      核取 **[!UICONTROL Export labels instead of internal values of enumerations]** 選項，以備您匯出分項清單時使用。此選項可讓您擷取較短的標籤，與 ID 不同，這些標籤很容易理解。

1. 新增&#x200B;**[!UICONTROL Transfer file]**&#x200B;活動，並設定它將新建立的檔案從Adobe Campaign伺服器傳輸至您可存取的其他位置，例如SFTP伺服器。

   * 在&#x200B;**[!UICONTROL General]**&#x200B;標籤中，選擇&#x200B;**[!UICONTROL File upload]**，因為目的是將檔案從Adobe Campaign傳送至其他伺服器。
   * 在&#x200B;**[!UICONTROL Protocol]**&#x200B;標籤中，指定傳輸參數並選擇要使用的[外部帳戶](../../administration/using/external-accounts.md#creating-an-external-account)。

1. 新增&#x200B;**[!UICONTROL End]**&#x200B;活動，以確保活動正確結束並儲存您的工作流程。

   ![](assets/export_logs_example_workflow.png)

您現在可以在外部伺服器上執行工作流程並擷取輸出檔案。

**相關主題：**

[工作流程](../../automating/using/get-started-workflows.md)
