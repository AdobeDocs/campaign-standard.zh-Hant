---
title: 擷取檔案
description: 「擷取檔案」活動可讓您以外部檔案的形式從Adobe Campaign匯出資料。
page-status-flag: 從未激活
uuid: 631f0fbd-9e8d-4f77-a338-fcb7f4fc1774
contentOwner: 紹維亞
products: SG_CAMPAIGN/STANDARD
audience: 自動化
content-type: 參考
topic-tags: 資料管理活動
discoiquuid: a06509f9-4731-4187-b43d-3bfa361284d3
context-tags: fileExport,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 擷取檔案{#extract-file}

## 說明 {#description}

![](assets/export.png)

此活 **[!UICONTROL Extract file]** 動可讓您以外部檔案的形式，從Adobe Campaign匯出資料。

## 使用內容 {#context-of-use}

設定活動時，會定義資料擷取的方式。

>[!CAUTION]
>
>活動 **[!UICONTROL Extract file]** 必須放在活動之 **[!UICONTROL Query]** 後才能使用。

## 配置 {#configuration}

1. 將活動拖放 **[!UICONTROL Extract file]** 至工作流程。

   ![](assets/wkf_data_export1.png)

1. 選擇活動，然後使用顯示的快 ![](assets/edit_darkgrey-24px.png) 速操作中的按鈕將其開啟。
1. 輸入輸出檔案 **的標籤**。 檔案的標籤將自動完成，其建立日期和時間為唯一。 例如：recipients_20150815_081532.txt，此檔案是於2015年8月15日08:15:32產生的。

   >[!NOTE]
   >
   >可以使用此欄位 **[!UICONTROL formatDate]** 中的函式指定檔案名。

1. 如果您喜歡，可以在欄位中選取，以壓縮 **[!UICONTROL Compression]** 輸出 **[!UICONTROL Add a pre-processing step]** 檔案。 輸出檔案將壓縮為GZIP檔案(.gz)。
1. 按一下或 ![](assets/add_darkgrey-24px.png) 按 **[!UICONTROL Add an element]** 鈕添加輸出列。

   ![](assets/wkf_data_export2.png)

   將會開啟新視窗。

   ![](assets/wkf_data_export3.png)

1. 輸入表達式。 要執行此操作，可以選擇現有表達式，或使用表達式編輯器建立新 **表達式**。
1. 確認您的運算式。

   表達式將添加到輸出列。

1. 建立您所需的欄數。 您可以按一下欄的運算式和標籤來編輯欄。

   如果要導出配置檔案並希望在外部工具中使用它們，請確保導出唯一標識符。 依預設，並非所有描述檔都有唯一的識別碼，視其新增至資料庫的方式而定。 如需詳細資訊，請參閱「產 [生描述檔的唯一ID](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources) 」一節。

1. 按一下 **[!UICONTROL File structure]** 頁籤，為要導出的檔案配置輸出、日期和編號格式。

   勾選選 **[!UICONTROL Export labels instead of internal values of enumerations]** 選項，以備您匯出列舉值時使用。 此選項可讓您擷取較短的標籤，這些標籤很容易理解，而非ID。

1. 在標籤中 **[!UICONTROL Properties]** ，選取選 **[!UICONTROL Do not generate a file if the inbound transition is empty]** 項以避免在傳入的轉場為空時，在SFTP伺服器上建立和上傳空白檔案。
1. 確認活動的設定並儲存工作流程。

## Example {#example}

以下示例說明如何在活動後 **[!UICONTROL Extract file]** 配置活 **[!UICONTROL Query]** 動。

此工作流程的目的是匯出外部檔案格式的描述檔清單，以便在Adobe Campaign外使用資料。

1. 將活動拖放 **[!UICONTROL Extract file]** 到工作流程中，並將其置於活動 **[!UICONTROL Query]** 後面。

   在此範例中，查詢是對18到30歲的所有描述檔執行。

1. 開啟「擷取檔案」活動以進行編輯。
1. 命名輸出檔案。
1. 新增輸出欄。

   在此範例中，會新增描述檔的電子郵件、年齡、出生日期、名字和姓氏作為輸出欄。

   ![](assets/wkf_data_export6.png)

1. 按一下標 **[!UICONTROL File structure]** 簽以定義：

   * CSV輸出格式

      ![](assets/wkf_data_export7.png)

   * 日期格式

      ![](assets/wkf_data_export9.png)

1. 確認您的活動。
1. 在活動後拖放活 **[!UICONTROL Transfer file]** 動，以 **[!UICONTROL Extract file]** 恢復外部帳戶上的提取檔案。
1. 開啟活動並選擇 **[!UICONTROL File upload]** 動作。

   ![](assets/wkf_data_export11.png)

1. 選擇外部帳戶，然後輸入伺服器上資料夾的路徑。

   ![](assets/wkf_data_export12.png)

1. 確認您的活動並儲存您的工作流程。
1. 啟動工作流程。

   當工作流程已正確執行時，擷取的檔案便可在外部帳戶上使用。

