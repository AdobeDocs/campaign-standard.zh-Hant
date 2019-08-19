---
title: 傳輸檔案
seo-title: 傳輸檔案
description: 傳輸檔案
seo-description: 轉讓檔案活動可讓您接收或傳送檔案、測試是否存在檔案，或在Adobe Campaign中列出檔案。
page-status-flag: 從未啓動
uuid: a2f18118-b681-4310-aee0-1e82179 d2032
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: reference
topic-tags: 資料管理活動
discoiquuid: 752f2aed-f897-485e-b329-f3 cc1756 ee8 e
context-tags: FileTransfer，主要
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 4fe36a1747aca69e8857cf415593086781947a47

---


# 傳輸檔案{#transfer-file}

## 說明 {#description}

![](assets/file_transfer.png)

**[!UICONTROL Transfer file]** 活動可讓您接收或傳送檔案、測試是否存在檔案，或在Adobe Campaign中列出檔案。

## 使用內容 {#context-of-use}

在設定活動時，定義擷取資料的方式。要載入的檔案可能是連絡人清單。

您可以使用此活動來復原隨後將與 **[!UICONTROL Load file]** 活動結構化的資料。

## 組態配置 {#configuration}

1. 將 **[!UICONTROL Transfer file]** 活動拖放到工作流程中。
1. 選取活動，然後使用顯示的快速動作 ![](assets/edit_darkgrey-24px.png) 按鈕將其開啓。
1. 使用 **[!UICONTROL Action]** 欄位中的下拉式清單，選取下列其中一個活動動作：

   ![](assets/wkf_file_transfer_01.png)

   * **檔案下載**：可供您下載檔案。
   * **檔案上傳**：可讓您上傳檔案。從Adobe Campaign檔案上傳檔案時，會在 **[!UICONTROL Export audits]** 功能表中產生記錄項目。如需匯出稽核的詳細資訊，請參閱 [「稽核匯出](../../administration/using/auditing-export-logs.md) 」區段。
   * **測試以查看檔案是否存在**：可讓您檢查是否有檔案。
   * **檔案清單**：可讓您列出Adobe Campaign中顯示的檔案。
   根據選取的動作，可使用一或多個通訊協定：

   * **HTTP**：此通訊協定可讓您從外部帳戶或從URL開始下載檔案。

      * 按一下 **[!UICONTROL Use connection parameters defined in an external account]** 選項，然後選取您要的帳戶，並指定要下載的檔案路徑。

         ![](assets/wkf_file_transfer_03.png)

      * 按一下 **[!UICONTROL Quick configuration]** 選項，然後在顯示的欄位中輸入URL。

         ![](assets/wkf_file_transfer_04.png)
   * **S3**：此通訊協定可讓您從URL或Amazon Simple Storage Service(S3)開始從URL或外部帳戶下載檔案。

      * 選取外部帳戶，並指定要下載的檔案路徑。

         ![](assets/wkf_file_transfer_08.png)
   * **SFTP**：此通訊協定可讓您從URL或外部帳戶開始下載檔案。

      * 按一下 **[!UICONTROL Use connection parameters defined in an external account]** 選項，然後選取您要的帳戶，並指定要下載的檔案路徑。

         ![](assets/wkf_file_transfer_07.png)

         >[!CAUTION]
         >
         >支援萬用字元。

      * 按一下 **[!UICONTROL Quick configuration]** 選項，然後在顯示的欄位中輸入URL。
      * 如果您想要對匯入的檔案進行排序，請從 **[!UICONTROL Sort alphanumerically]****[!UICONTROL Additional options]** 區段中選取選項。然後會以循序順序處理檔案。

         ![](assets/wkf_file_transfer_sort.png)
   * **Adobe Campaign伺服器上的檔案**：此通訊協定對應至包含檔案的儲存庫。

      Metacharacters或萬用字元(例如*或？)可用來篩選檔案。

      填寫此欄位並確認您的活動使用此通訊協定。

      >[!NOTE]
      >
      >路徑必須與Adobe Campaign伺服器的儲存空間目錄相相對。檔案位於 **sftp&lt; yourri cename&gt;/** 目錄中。您也無法瀏覽儲存空間上方的目錄。例如： **user&lt; youroft cename&gt;/my_ receivers. csv** 正確。**../hello/my_recipients.csv** 不正確。**//myserver/hello/myrecipients.csv** 不正確。
   選取您的通訊協定並完成相關欄位。

   **[!UICONTROL Use a dynamic file path]** 每個通訊協定可用的選項可讓您使用標準運算式和事件變數，將檔案的名稱個人化。如需詳細資訊，請參閱「使用事件變數 [自訂活動」](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables) 。

1. **[!UICONTROL Additional options]** 區段(視選取的通訊協定而定)可讓您新增參數至通訊協定。您可以：

   * **[!UICONTROL Delete the source files after transfer]**
   * **[!UICONTROL Disable passive mode]**
   * **[!UICONTROL List all files]**：選取 **[!UICONTROL File listing]** 動作時可使用此選項。它可讓您索引 **vars. filenames** 事件變數中伺服器上顯示的所有檔案，其中檔案名稱由 **'n'** 字元分隔。

1. 此標籤 **[!UICONTROL If no files are found]** 的區段 **[!UICONTROL Advanced options]** 可讓您設定當活動啓動時偵測到任何錯誤或不存在的檔案時的特定動作。

   您也可以定義重試。不同重試會出現在工作流程執行記錄檔中。

   ![](assets/wkf_file_transfer_09.png)

1. 確認活動的設定並儲存工作流程。

## 歷史設定 {#historization-settings}

每次執行 **[!UICONTROL Transfer file]** 活動時，都會將上傳或下載的檔案儲存在專屬資料夾中。為工作流程的每 **[!UICONTROL Transfer file]** 個活動建立一個資料夾。因此，必須能夠限制此資料夾的大小，以保留伺服器上的實體空間。

若要這麼做，您可以在 **[!UICONTROL Historization settings]** 活動中 **[!UICONTROL Advanced options]****[!UICONTROL Transfer File]** 定義。

**[!UICONTROL Historization settings]** 允許定義活動資料夾的檔案數目上限或總大小。根據預設，已授權100個檔案和50MB。

每次執行活動時，都會檢查資料夾如下：

* 只有已建立超過24小時的檔案才會納入考量。
* 如果考量的檔案數目大於 **[!UICONTROL Maximum number of files]** 參數值，會刪除最舊的檔案，直到達到 **[!UICONTROL Maximum number of files]** 允許的檔案為止。
* 如果納入的檔案大小大於 **[!UICONTROL Maximum size (in MB)]** 參數值，則會刪除最舊的檔案，直到達到 **[!UICONTROL Maximum size (in MB)]** 允許的大小為止。

>[!NOTE]
如果未再次執行活動，則不會檢查資料夾或清除資料夾。記住這一點，請小心傳輸大型檔案。

## 範例 {#example}

下列範例顯示 **檔案傳輸** 活動的設定，隨後 **接著接著載入檔案** 活動， **然後更新資料** 活動。此工作流程的目標是新增或更新Adobe Campaign資料庫設定檔與工作流程所復原的資料。

1. 將 **移轉檔案** 活動拖放至工作流程中。
1. 選取活動，然後使用顯示的快速動作 ![](assets/edit_darkgrey-24px.png) 按鈕將其開啓。
1. 在 **[!UICONTROL Protocol]** 標籤中，選取 **SFTP**。
1. 選取 **在外部帳戶** 選項中定義的「使用連線參數」。
1. 輸入外部帳戶的名稱。
1. 在遠端伺服器上輸入 **檔案路徑**。

   ![](assets/wkf_file_transfer_07.png)

1. 確認您的活動並儲存您的工作流程。

