---
title: 傳輸檔案
description: 「傳輸檔案」活動可讓您接收或傳送檔案、測試是否有檔案存在，或列出 Adobe Campaign 中的檔案。
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
source-git-commit: eed3474c133645a3b9fe8001c21360bba4a363e4
workflow-type: tm+mt
source-wordcount: '1070'
ht-degree: 98%

---


# 傳輸檔案{#transfer-file}

## 說明 {#description}

![](assets/file_transfer.png)

**[!UICONTROL Transfer file]** 活動可讓您接收或傳送檔案、測試 Adobe Campaign 中是否有檔案或列出檔案。

>[!CAUTION]
>
>從 20.3 版開始，隨 **[!UICONTROL Transfer File]** 活動下載的檔案將在 X 天後刪除，其中 X 由「工作流程」屬性中 **[!UICONTROL Execution]** 功能表下的 **[!UICONTROL History in days]** 欄位決定。

## 使用內容 {#context-of-use}

設定活動時，會定義資料擷取的方式。例如，要載入的檔案可以是聯絡人清單。

您可以使用 **[!UICONTROL Load file]** 活動來復原隨後將與活動一起建構的資料。

**相關主題：**

* [使用案例：根據自動檔案下載更新資料](../../automating/using/update-data-automatic-download.md)

## 設定 {#configuration}

1. 將活動 **[!UICONTROL Transfer file]** 拖曳至工作流程中。
1. 選取活動，然後使用所顯示快速操作中的 ![](assets/edit_darkgrey-24px.png) 按鈕將其開啟。
1. 使用 **[!UICONTROL Action]** 欄位中的下拉式清單，選取下列活動動作之一：

   ![](assets/wkf_file_transfer_01.png)

   * **檔案下載**：可讓您下載檔案。
   * **檔案上傳**：可讓您上傳檔案。從 Adobe Campaign 檔案上傳檔案會在 **[!UICONTROL Export audits]** 功能表中產生記錄項目。有關匯出稽核的詳細資訊，請參閱[稽核匯出](../../administration/using/auditing-export-logs.md)區段。
   * **測試以查看檔案是否存在**：可讓您檢查是否存在檔案。
   * **檔案清單**：可讓您列出伺服器上存在的檔案（在 **[!UICONTROL Protocol]** 索引標籤中定義）。此動作主要用於偵錯，以在從遠端伺服器下載檔案之前，先檢查活動是否已根據您的需求進行設定。

1. 選取要使用的通訊協定：
   * [HTTP](#HTTP-configuration-wf)
   * [SFTP](#SFTP-configuration-wf)
   * [Amazon S3](#S3-configuration-wf)
   * [Microsoft Azure Blob　儲存](#azure-blob-configuration-wf)
   * [Adobe Campaign　伺服器上的檔案](#files-server-configuration-wf)

1. **[!UICONTROL Additional options]** 區段根據所選協定而提供，可讓您向通訊協定新增參數。您可以：

   * **[!UICONTROL Delete the source files after transfer]**
   * **[!UICONTROL Disable passive mode]**
   * **[!UICONTROL List all files]**：在　**[!UICONTROL General]**　索引標籤中選取　**[!UICONTROL File listing]**　動作時，此選項可供使用。它可讓您為 **vars.filenames** event　變數中伺服器上所有檔案建立索引，其中檔案名稱以 **&#39;n&#39;** 字元分隔 。

1. **[!UICONTROL If no files are found]** 索引標籤的 **[!UICONTROL Advanced options]** 區段可讓您在活動啟動時偵測到任何錯誤或不存在的檔案時設定特定操作。

   您也可以定義重試次數。不同的重試次數會出現在工作流程執行記錄中。

   ![](assets/wkf_file_transfer_09.png)

1. 確認活動的設定並儲存工作流程。

### 使用　HTTP　進行設定 {#HTTP-configuration-wf}

HTTP　通訊協定可讓您從外部帳戶或　URL　開始下載檔案。

使用此控制工具，您可以選取　**[!UICONTROL Use connection parameters defined in an external account]**　選項。在此情況下，請選取您需要的帳戶，並指定要下載的檔案路徑。
![](assets/wkf_file_transfer_03.png)

您也可以選取 **[!UICONTROL Quick configuration]** 選項。您只需在　URL　欄位中輸入URL。
![](assets/wkf_file_transfer_04.png)

### 使用　SFTP　進行設定 {#SFTP-configuration-wf}

SFTP　通訊協定可讓您開始從　URL　或外部帳戶下載檔案。

使用此通訊協定，您可以選取 **[!UICONTROL Use connection parameters defined in an external account]** 選項，然後選取您要的帳戶並指定要下載的檔案路徑。
![](assets/wkf_file_transfer_07.png)

>[!CAUTION]
>
>支援萬用字元。

您也可以選取 **[!UICONTROL Quick configuration]** 選項。您只需在 URL 欄位中輸入 URL。

### 使用　Amazon S3　進行設定 {#S3-configuration-wf}

Amazon S3　通訊協定可讓您透過　Amazon Simple Storage Service(S3)　從　URL　或外部帳戶開始下載檔案。

1. 選取　Amazon S3　外部帳戶。如需詳細資訊，請參閱此[頁面](../../administration/using/external-accounts.md#amazon-s3-external-account)。

2. 選取是否 **[!UICONTROL Define a file path]** 或 **[!UICONTROL Use a dynamic file path]**。

3. 指定要下載的檔案路徑。

   ![](assets/wkf_file_transfer_08.png)

4. 如果要在傳輸完成時刪除源檔案，請核取 **[!UICONTROL Delete the source files after transfer]**。

### 使用　Microsoft Azure Blob　儲存設定 {#azure-blob-configuration-wf}

Microsoft Azure Blob　通訊協定可讓您存取位於　Microsoft Azure Blob　儲存帳戶上的　blob。

1. 選取　**[!UICONTROL Microsoft Azure Blob]**　外部帳戶。如需詳細資訊，請參閱此[頁面](../../administration/using/external-accounts.md#microsoft-azure-external-account)。

1. 選取是否 **[!UICONTROL Define a file path]** 或 **[!UICONTROL Use a dynamic file path]**。

   ![](assets/wkf_file_transfer_10.png)

1. 指定要下載的檔案路徑，可比對多個　blob。在這種情況下，找到每個 blob 之後，**[!UICONTROL File transfer]**　活動就會啟動出站轉變。然後會依字母順序處理。

   >[!CAUTION]
   >
   >不支援萬用字元來比對多個檔案名稱。您需要輸入首碼。所有與該首碼相符的　blob　名稱都符合條件。

   您可以在檔案路徑的範例清單下找到：

   * **&quot;campaign/&quot;**：相符項目：位於容器根目錄的　Campaign　資料夾中的所有 blob。
   * **&quot;campaign/new-&quot;**：相符項目：所有檔案名稱以　&quot;new-&quot;　開頭且位於　Campaign　檔案夾下方的　blob。
   * **&quot;&quot;**：新增空白路徑可讓您比對容器中所有可用的　blob。

### Adobe Campaign　伺服器上檔案的設定 {#files-server-configuration-wf}

**[!UICONTROL File(s) present on the Adobe Campaign server]**　通訊協定對應於包含要復原的檔案的存放庫。
超字元或萬用字元（例如　* 或 ?）可用於篩選檔案。

選取是否 **[!UICONTROL Define a file path]** 或 **[!UICONTROL Use a dynamic file path]**
**[!UICONTROL Use a dynamic file path]**　選項可讓您使用標準運算式和事件變數來個人化要傳輸的檔案名稱。For more on this, refer to this section: [](../../automating/using/customizing-workflow-external-parameters.md).

請注意，路徑必須相對於　Adobe Campaign　伺服器的儲存空間目錄。檔案位於 **sftp&lt;yourinstancename>/** 目錄。您也無法瀏覽儲存空間上方的目錄。例如：

    >**user&amp;lt;yourinstancename>/my_recipients.csv** 是正確的。
    >
    >**../hello/my_recipients.csv** 是不正確的。
    >
    >**//myserver/hello/myrecipients.csv** 是不正確的。

## 歷史化設定 {#historization-settings}

每次執行　**[!UICONTROL Transfer file]**　活動時，都會將已上傳或已下載的檔案儲存在專用的資料夾中。系統會為工作流的每個　**[!UICONTROL Transfer file]**　活動建立一個資料夾。因此，必須能夠限制此資料夾的大小，以便保留伺服器上的實體空間。

若要這麼做，您可在 **[!UICONTROL Transfer File]** 活動的 **[!UICONTROL Advanced options]** 中定義 **[!UICONTROL Historization settings]**。

**[!UICONTROL Historization settings]** 可定義活動資料夾的檔案數目上限或總大小。依預設，授權 100 個檔案和 50 MB。

每次執行活動時，都會檢查資料夾，如下所示：

* 只考慮在活動執行前 24 小時以上建立的檔案。
* 如果考慮的檔案數大於 **[!UICONTROL Maximum number of files]** 參數的值，則刪除最舊的文件，直到達到允許的 **[!UICONTROL Maximum number of files]** 值為止。
* 如果考慮的檔案總大小大於 **[!UICONTROL Maximum size (in MB)]** 參數值，則會刪除最舊的檔案，直到達到允許的 **[!UICONTROL Maximum size (in MB)]** 值為止。

>[!NOTE]
>
>如果活動未再次執行，則不會檢查或清除其資料夾。考慮到這一點，在傳輸大型檔案時請務必小心。
