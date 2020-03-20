---
title: 傳輸檔案
description: 「傳輸檔案」活動可讓您接收或傳送檔案、測試是否有檔案存在，或列出Adobe Campaign中的檔案。
page-status-flag: never-activated
uuid: a2f18118-b681-4310-aee0-9e82179d2032
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: 752f2aed-f897-485e-b329-f3cc1756ee8e
context-tags: fileTransfer,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 9048e11fe063707e1c6b5a86de095f72d22800c1

---


# 傳輸檔案{#transfer-file}

## 說明 {#description}

![](assets/file_transfer.png)

此活 **[!UICONTROL Transfer file]** 動可讓您接收或傳送檔案、測試Adobe Campaign中是否有檔案或列出檔案。

## 使用內容 {#context-of-use}

設定活動時，會定義資料擷取的方式。 例如，要載入的檔案可以是聯繫人清單。

您可以使用此活動來恢復隨後將與活動一起構建的 **[!UICONTROL Load file]** 資料。

## 配置 {#configuration}

1. 將活動 **[!UICONTROL Transfer file]** 拖放至工作流程中。
1. 選擇活動，然後使用顯示的快 ![](assets/edit_darkgrey-24px.png) 速操作中的按鈕將其開啟。
1. 使用欄位中的下拉式清 **[!UICONTROL Action]** 單，選取下列活動動作之一：

   ![](assets/wkf_file_transfer_01.png)

   * **檔案下載**:可讓您下載檔案。
   * **檔案上傳**:可讓您上傳檔案。 從Adobe Campaign檔案上傳檔案會在功能表中產生記錄 **[!UICONTROL Export audits]** 項。 有關導出審計的詳細資訊，請參閱「審 [計導出](../../administration/using/auditing-export-logs.md) 」部分。
   * **測試以查看檔案是否存在**:允許您檢查是否存在檔案。
   * **檔案清單**:可讓您列出Adobe Campaign中的檔案。
1. 選擇要使用的協定：
   * [HTTP](#HTTP-configuration-wf)
   * [SFTP](#SFTP-configuration-wf)
   * [Amazon S3](#S3-configuration-wf)
   * [Microsoft Azure Blob儲存](#azure-blob-configuration-wf)
   * [Adobe Campaign伺服器上的檔案](#files-server-configuration-wf)

1. 該 **[!UICONTROL Additional options]** 部分根據所選協定而提供，允許您向協定添加參數。 您可以：

   * **[!UICONTROL Delete the source files after transfer]**
   * **[!UICONTROL Disable passive mode]**
   * **[!UICONTROL List all files]**:此選項在選擇操作時可 **[!UICONTROL File listing]** 用。 它可讓您為 **vars.filenames** event變數中伺服器上所有檔案建立索引，其中檔案名稱以&#39; **n&#39;字元分隔** 。

1. 該選 **[!UICONTROL If no files are found]** 項卡的 **[!UICONTROL Advanced options]** 部分允許您在活動啟動時檢測到任何錯誤或不存在的檔案時配置特定操作。

   您也可以定義重試次數。 不同的重試次數會出現在工作流程執行記錄中。

   ![](assets/wkf_file_transfer_09.png)

1. 確認活動的設定並儲存工作流程。

### 使用HTTP進行配置 {#HTTP-configuration-wf}

HTTP通訊協定可讓您從外部帳戶或URL開始下載檔案。

使用此控制工具，您可以選擇選 **[!UICONTROL Use connection parameters defined in an external account]** 項。 在此情況下，請選取您要的帳戶，並指定要下載的檔案路徑。
![](assets/wkf_file_transfer_03.png)

您也可以選擇 **[!UICONTROL Quick configuration]** 選項。 您只需在URL欄位中輸入URL。
![](assets/wkf_file_transfer_04.png)

### 使用SFTP進行設定 {#SFTP-configuration-wf}

SFTP通訊協定可讓您開始從URL或外部帳戶下載檔案。

使用此協定，您可以選擇 **[!UICONTROL Use connection parameters defined in an external account]** 選項，然後選取您要的帳戶並指定要下載的檔案路徑。
![](assets/wkf_file_transfer_07.png)

>[!CAUTION]
>
>支援萬用字元。

您也可以選擇 **[!UICONTROL Quick configuration]** 選項。 您只需在URL欄位中輸入URL。

### 使用Amazon S3進行配置 {#S3-configuration-wf}

Amazon S3通訊協定可讓您透過Amazon Simple Storage Service(S3)從URL或外部帳戶開始下載檔案。

1. 選擇Amazon S3外部帳戶。 For more on this, refer to this [page](../../administration/using/external-accounts.md#amazon-s3-external-account).

2. 選擇是否 **[!UICONTROL Define a file path]** 要 **[!UICONTROL Use a dynamic file path]**。

3. 指定要下載的檔案路徑。

   ![](assets/wkf_file_transfer_08.png)

4. 如果要在傳輸完成時刪除源檔案，請選中 **[!UICONTROL Delete the source files after transfer]**。

### 使用Microsoft Azure Blob儲存配置 {#azure-blob-configuration-wf}

Microsoft Azure Blob通訊協定可讓您存取位於Microsoft Azure Blob儲存帳戶上的blob。

1. 選擇外 **[!UICONTROL Microsoft Azure Blob]** 部帳戶。 For more on this, refer to this [page](../../administration/using/external-accounts.md#microsoft-azure-external-account).

1. 選擇是否 **[!UICONTROL Define a file path]** 要 **[!UICONTROL Use a dynamic file path]**。

   ![](assets/wkf_file_transfer_10.png)

1. 指定要下載的檔案路徑，可比對多個blob。 在這種情況下，活 **[!UICONTROL File transfer]** 動將激活每個找到的blob一次傳出過渡。 然後會依字母順序處理。

   >[!CAUTION]
   >
   >不支援萬用字元來比對多個檔案名稱。 您需要輸入首碼。 所有與該前置詞匹配的blob名稱都符合條件。

   您可以在檔案路徑的範例清單下找到：

   * **&quot;campaign/&quot;**:相符項目：位於容器根目錄的「促銷活動」資料夾中的所有blob。
   * **「促銷活動／新增-」**:相符項目：所有檔案名稱以&quot;new-&quot;開頭且位於「促銷活動」檔案夾下方的blob。
   * **「」**:新增空路徑可讓您比對容器中所有可用的位塊。

### Adobe Campaign伺服器上檔案的設定 {#files-server-configuration-wf}

協 **[!UICONTROL File(s) present on the Adobe Campaign server]** 議對應於包含要恢復的檔案的儲存庫。
元字元或萬用字元（例如*或？）可用來篩選檔案。

選擇是否要， **[!UICONTROL Define a file path]** 或 **[!UICONTROL Use a dynamic file path]**&#x200B;選 **[!UICONTROL Use a dynamic file path]** 項可讓您使用標準運算式和事件變數來個人化要傳輸的檔案名稱。 如需詳細資訊，請參閱「使用事件變 [數自訂活動](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables) 」一節。

請注意，路徑必須相對於Adobe Campaign伺服器的儲存空間目錄。 檔案位於 **sftp&lt;yourinstancename>/目錄** 。 您也無法瀏覽儲存空間上方的目錄。 例如：

    >**user&amp;lt;yourinstancename>/my_recipients.csv**正確。
    >
    >**../hello/my_recipients.csv**不正確。
    >
    >**//myserver/hello/myrecipients.csv**不正確。

## 歷史化設定 {#historization-settings}

每次執行活 **[!UICONTROL Transfer file]** 動時，都會將已上傳或已下載的檔案儲存在專用的資料夾中。 系統會為工作流的每個活 **[!UICONTROL Transfer file]** 動建立一個資料夾。 因此，必須能夠限制此資料夾的大小，以便保留伺服器上的物理空間。

若要這麼做，您可在 **[!UICONTROL Historization settings]** 活動中 **[!UICONTROL Advanced options]** 定義 **[!UICONTROL Transfer File]** 。

**[!UICONTROL Historization settings]** 允許定義活動資料夾的最大檔案數或總大小。 依預設，授權100個檔案和50 MB。

每次執行活動時，都會檢查資料夾，如下所示：

* 只考慮在活動執行前24小時以上建立的檔案。
* 如果考慮的檔案數大於參數的值，則刪除最舊的文 **[!UICONTROL Maximum number of files]** 件，直到達到允許 **[!UICONTROL Maximum number of files]** 的值為止。
* 如果考慮的檔案總大小大於參數值，則會刪除最舊的檔案，直到達到允許 **[!UICONTROL Maximum size (in MB)]****[!UICONTROL Maximum size (in MB)]** 的值為止。

>[!NOTE]
>
>如果活動未再次執行，則不會檢查或清除其資料夾。 有了這一點，在傳輸大型檔案時請務必小心。

## Example {#example}

以下示例顯示檔案傳輸活 **動的配置** ，該活動隨後將依次是 **Load file** activity和 **Update data** activity。 此工作流程的目標是新增或更新Adobe Campaign資料庫設定檔，並使用工作流程所復原的資料。

1. 將「傳輸」檔案 **活動拖放** 至您的工作流程中。
1. 選擇活動，然後使用顯示的快 ![](assets/edit_darkgrey-24px.png) 速操作中的按鈕將其開啟。
1. 在標籤 **[!UICONTROL Protocol]** 中，選擇 **SFTP**。
1. 選擇「使 **用在外部帳戶中定義的連接參數** 」選項。
1. 輸入外部帳戶的名稱。
1. 輸入遠程 **伺服器上的檔案路徑**。

   ![](assets/wkf_file_transfer_07.png)

1. 確認您的活動並儲存您的工作流程。

