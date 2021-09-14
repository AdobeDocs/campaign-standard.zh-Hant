---
title: 擷取檔案
description: 「擷取檔案」活動可讓您以外部檔案的形式從 Adobe Campaign 匯出資料。
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: fileExport,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: ccf73563-f0f8-4397-ba96-7c5727562acd
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '402'
ht-degree: 86%

---

# 擷取檔案{#extract-file}

## 說明 {#description}

![](assets/export.png)

**[!UICONTROL Extract file]** 活動可讓您以外部檔案的形式，從 Adobe Campaign 匯出資料。

## 使用內容 {#context-of-use}

設定活動時，會定義擷取資料的方式。

>[!CAUTION]
>
>活動 **[!UICONTROL Extract file]** 必須放在 **[!UICONTROL Query]** 活動之後才能使用。

**相關主題：**

* [使用案例：在外部檔案中匯出設定檔](../../automating/using/exporting-profiles-in-file.md)

## 設定 {#configuration}

1. 將 **[!UICONTROL Extract file]** 活動拖放至工作流程中。

   ![](assets/wkf_data_export1.png)

1. 選取活動，然後使用所顯示快速操作中的 ![](assets/edit_darkgrey-24px.png) 按鈕將其開啟。
1. 輸入&#x200B;**輸出檔案**&#x200B;的標籤。將自動在檔案的標籤內填入建立的日期與時間，所以該標籤會是唯一的。例如：recipients_20150815_081532.txt，此檔案是於2015年8月15日08:15:32產生的。

   >[!NOTE]
   >
   >可以使用此欄位的 **[!UICONTROL formatDate]** 函式指定檔案名稱。

1. 您也可以在 **[!UICONTROL Add a post-processing stage]** 欄位中選取 **[!UICONTROL Compression]** 以壓縮輸出檔案。輸出檔案將壓縮為 GZIP 檔案 (.gz)。

   **[!UICONTROL Add a post-processing stage]**&#x200B;欄位還允許您在解壓檔案之前對其進行加密。 有關如何處理加密檔案的詳細資訊，請參閱[此部分](../../automating/using/managing-encrypted-data.md)

1. 按一下&#x200B;**[!UICONTROL Create element]**&#x200B;按鈕以新增輸出欄。

   ![](assets/wkf_data_export2.png)

   新視窗隨之開啟。

   ![](assets/wkf_data_export3.png)

1. 輸入運算式。要執行此操作，可以選取現有運算式，或使用&#x200B;**運算式編輯器**&#x200B;建立新的運算式。
1. 確認您的運算式。

   已將運算式新增至到輸出欄。

1. 建立您所需的欄數。您可以按一下欄的運算式及標籤來進行編輯。

   如果要匯出設定檔並希望在外部工具中使用它們，請確定您匯出唯一識別碼。依預設，並非所有設定檔都有唯一識別碼，這會視其新增至資料庫的方式而定。如需詳細資訊，請參閱[產生設定檔的唯一 ID](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources)區段。

1. 按一下 **[!UICONTROL File structure]** 索引標籤，為要匯出的檔案設定輸出、日期和編號格式。

   核取 **[!UICONTROL Export labels instead of internal values of enumerations]** 選項，以備您匯出分項清單時使用。此選項可讓您擷取較短的標籤，與 ID 不同，這些標籤很容易理解。

1. 在 **[!UICONTROL Properties]** 索引標籤中，選取 **[!UICONTROL Do not generate a file if the inbound transition is empty]** 選項，以避免在入站轉變為空時，在 SFTP 伺服器上建立和上傳空白檔案。
1. 確認活動的設定並儲存工作流程。
