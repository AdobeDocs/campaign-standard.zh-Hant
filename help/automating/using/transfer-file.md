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
source-git-commit: 0fcedd464ae2074e7eda793bbf20cc53ce04f324

---


# Transfer file{#transfer-file}

## Description {#description}

![](assets/file_transfer.png)

**[!UICONTROL Transfer file]** 活動可讓您接收或傳送檔案、測試是否存在檔案，或在Adobe Campaign中列出檔案。

## Context of use {#context-of-use}

在設定活動時，定義擷取資料的方式。要載入的檔案可能是連絡人清單。

You can use this activity to recover data that will then be structured with the **[!UICONTROL Load file]** activity.

## Configuration {#configuration}

1. Drop a **[!UICONTROL Transfer file]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. Use the drop-down list in the **[!UICONTROL Action]** field to select one of the following activity actions:

   ![](assets/wkf_file_transfer_01.png)

   * **檔案下載**：可供您下載檔案。
   * **檔案上傳**：可讓您上傳檔案。Uploading a file from Adobe Campaign file generates a log entry in the **[!UICONTROL Export audits]** menu. For more information on export audits, refer to the [Auditing exports](../../administration/using/auditing-export-logs.md) section.
   * **測試以查看檔案是否存在**：可讓您檢查是否有檔案。
   * **檔案清單**：可讓您列出Adobe Campaign中顯示的檔案。
   根據選取的動作，可使用一或多個通訊協定：

   * **HTTP**：此通訊協定可讓您從外部帳戶或從URL開始下載檔案。

      * Click the **[!UICONTROL Use connection parameters defined in an external account]** option, then select the account you would like and specify the path of the file to download.

         ![](assets/wkf_file_transfer_03.png)

      * Click the **[!UICONTROL Quick configuration]** option, then enter the URL in the field that appears.

         ![](assets/wkf_file_transfer_04.png)
   * **S3**：此通訊協定可讓您從URL或Amazon Simple Storage Service(S3)開始從URL或外部帳戶下載檔案。

      * 選取外部帳戶，並指定要下載的檔案路徑。

         ![](assets/wkf_file_transfer_08.png)
   * **SFTP**：此通訊協定可讓您從URL或外部帳戶開始下載檔案。

      * Click the **[!UICONTROL Use connection parameters defined in an external account]** option, then select the account you would like and specify the path of the file to download.

         ![](assets/wkf_file_transfer_07.png)

         >[!CAUTION]
         >
         >支援萬用字元。

      * Click the **[!UICONTROL Quick configuration]** option, then enter the URL in the field that appears.
      * If you want to sort the imported files, select the **[!UICONTROL Sort alphanumerically]** option from the **[!UICONTROL Additional options]** section. 然後會以循序順序處理檔案。

         ![](assets/wkf_file_transfer_sort.png)
   * **Adobe Campaign伺服器上的檔案**：此通訊協定對應至包含檔案的儲存庫。

      Metacharacters或萬用字元(例如*或？)可用來篩選檔案。

      填寫此欄位並確認您的活動使用此通訊協定。

      >[!NOTE]
      >
      >路徑必須與Adobe Campaign伺服器的儲存空間目錄相相對。檔案位於** sftp&lt; yourri cename&gt;/**目錄中。您也無法瀏覽儲存空間上方的目錄。For example: **user&lt;yourinstancename&gt;/my_recipients.csv** is correct. **../hello/my_recipients.csv** 不正確。**//myserver/hello/myrecipients.csv** 不正確。
   選取您的通訊協定並完成相關欄位。

   **[!UICONTROL Use a dynamic file path]** 每個通訊協定可用的選項可讓您使用標準運算式和事件變數，將檔案的名稱個人化。For more on this, refer to the [Customizing activities with events variables](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables) section.

1. **[!UICONTROL Additional options]** 區段(視選取的通訊協定而定)可讓您新增參數至通訊協定。您可以：

   * **[!UICONTROL Delete the source files after transfer]**
   * **[!UICONTROL Disable passive mode]**
   * **[!UICONTROL List all files]**：選取 **[!UICONTROL File listing]** 動作時可使用此選項。It allows you to index all the files present on the server in the **vars.filenames** event variable in which the file names are separated by the **'n'** characters.

1. The **[!UICONTROL If no files are found]** section of the **[!UICONTROL Advanced options]** tab allows you to configure specific actions if any errors or inexistent files are detected when the activity is started.

   您也可以定義重試。不同重試會出現在工作流程執行記錄檔中。

   ![](assets/wkf_file_transfer_09.png)

1. 確認活動的設定並儲存工作流程。

## Historization settings {#historization-settings}

Every time a **[!UICONTROL Transfer file]** activity is executed, it stores the uploaded or downloaded files in a dedicated folder. One folder is created for each **[!UICONTROL Transfer file]** activity of a workflow. 因此，必須能夠限制此資料夾的大小，以保留伺服器上的實體空間。

To do that, you can define **[!UICONTROL Historization settings]** in the **[!UICONTROL Advanced options]** of the **[!UICONTROL Transfer File]** activity.

**[!UICONTROL Historization settings]** 允許定義活動資料夾的檔案數目上限或總大小。根據預設，已授權100個檔案和50MB。

每次執行活動時，都會檢查資料夾如下：

* 只有已建立超過24小時的檔案才會納入考量。
* If the number of files taken into account is greater than the value of the **[!UICONTROL Maximum number of files]** parameter, the oldest files are deleted until the **[!UICONTROL Maximum number of files]** allowed is reached.
* If the total size of files taken into account is greater than the value of the **[!UICONTROL Maximum size (in MB)]** parameter, the oldest files are deleted until the **[!UICONTROL Maximum size (in MB)]** allowed is reached.

>[!NOTE]
如果未再次執行活動，則不會檢查資料夾或清除資料夾。記住這一點，請小心傳輸大型檔案。

## Example {#example}

The following example shows the configuration of a **File transfer** activity which will then be followed by a **Load file** activity then an **Update data** activity. 此工作流程的目標是新增或更新Adobe Campaign資料庫設定檔與工作流程所復原的資料。

1. Drag and drop a **Transfer file** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. In the **[!UICONTROL Protocol]** tab, select **SFTP**.
1. Select the **Use connection parameters defined in an external account** option.
1. 輸入外部帳戶的名稱。
1. Enter the **File path on the remote server**.

   ![](assets/wkf_file_transfer_07.png)

1. 確認您的活動並儲存您的工作流程。

