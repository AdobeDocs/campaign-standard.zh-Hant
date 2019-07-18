---
title: 摘取檔案
seo-title: 摘取檔案
description: 摘取檔案
seo-description: 「擷取檔案」活動可讓您以外部檔案的形式從Adobe Campaign匯出資料。
page-status-flag: 從未啓動
uuid: 631f0fbd-9e8d-4f77-a338-fcp7 f4 fc1774
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: reference
topic-tags: 資料管理活動
discoiquuid: a06509f9-4731-4187-b43 d-3bfa361284 d3
context-tags: FileExport，主要
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e384a0cef325bc01eb5ea050b0f3d926aea9a88f

---


# Extract file{#extract-file}

## Description {#description}

![](assets/export.png)

**[!UICONTROL Extract file]** 活動可讓您以外部檔案的形式從Adobe Campaign匯出資料。

## Context of use {#context-of-use}

在設定活動時，定義擷取資料的方式。

>[!CAUTION]
>
>**[!UICONTROL Extract file]** 活動必須放在 **[!UICONTROL Query]** 活動之後，才能使用。

## Configuration {#configuration}

1. Drag and drop an **[!UICONTROL Extract file]** activity into your workflow.

   ![](assets/wkf_data_export1.png)

1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. Enter the label of the **Output file**. 檔案的標籤會自動填入建立的日期和時間，使其成為唯一的。例如：recipients_20150815_081532.txt。

   >[!NOTE]
   >
   >It is possible to use the **[!UICONTROL formatDate]** function in this field to specify the file name.

1. If you like, you can zip the output file by selecting **[!UICONTROL Compression]** in the **[!UICONTROL Add a pre-processing step]** field. 輸出檔案將壓縮為GZIP檔案(.gz)。
1. Click the ![](assets/add_darkgrey-24px.png) or **[!UICONTROL Add an element]** button to add an output column.

   ![](assets/wkf_data_export2.png)

   開啓新視窗。

   ![](assets/wkf_data_export3.png)

1. 輸入運算式。To do this, you can select an existing expression or create a new one using the **expression editor**.
1. 確認您的運算式。

   運算式會新增至輸出欄。

1. 建立任意數量的欄。您可以按一下其運算式和標籤來編輯欄。

   如果您要匯出描述檔並想要在外部工具中使用，請務必匯出唯一識別碼。根據預設，並非所有描述檔都有唯一識別碼，視其新增至資料庫的方式而定。For more information, refer to the [Generating a unique ID for profiles](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources) section.

1. Click the **[!UICONTROL File structure]** tab to configure the output, date, and number formats for the file that will be exported.

   Check the **[!UICONTROL Export labels instead of internal values of enumerations]** option in case you export enumeration values. 此選項可擷取較短的標籤，而不需使用ID而易於瞭解。

1. In the **[!UICONTROL Properties]** tab, select the **[!UICONTROL Do not generate a file if the inbound transition is empty]** option to avoid creating and uploading empty files on SFTP servers if the inbound transition is empty.
1. 確認活動的設定並儲存工作流程。

## Example {#example}

The following example illustrates how to configure an **[!UICONTROL Extract file]** activity after a **[!UICONTROL Query]** activity.

此工作流程的目的是以外部檔案的形式匯出描述檔清單，以便在Adobe Campaign之外使用資料。

1. Drag and drop an **[!UICONTROL Extract file]** activity into your workflow and place it after the **[!UICONTROL Query]** activity.

   在此範例中，查詢是在18到30歲的所有描述檔上進行。

1. 開啓「摘取檔案」活動以進行編輯。
1. 為輸出檔案命名。
1. 新增輸出欄。

   在此範例中，會新增電子郵件、年齡、生日、名字的名字和姓氏作為輸出欄。

   ![](assets/wkf_data_export6.png)

1. Click the **[!UICONTROL File structure]** tab to define:

   * CSV輸出格式

      ![](assets/wkf_data_export7.png)

   * 日期格式

      ![](assets/wkf_data_export9.png)

1. 確認您的活動。
1. Drag and drop a **[!UICONTROL Transfer file]** activity after the **[!UICONTROL Extract file]** activity to recover the extract file on an external account.
1. Open the activity and choose the **[!UICONTROL File upload]** action.

   ![](assets/wkf_data_export11.png)

1. 選取外部帳戶，然後輸入伺服器上資料夾的路徑。

   ![](assets/wkf_data_export12.png)

1. 確認您的活動並儲存您的工作流程。
1. 開始工作流程。

   當工作流程正確執行時，會在外部帳戶上提供解壓縮檔案。

