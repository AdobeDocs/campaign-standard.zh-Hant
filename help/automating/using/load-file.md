---
title: 載入檔案
seo-title: 載入檔案
description: 載入檔案
seo-description: 載入檔案活動可讓您將資料匯入單一結構化表單，以便在Adobe Campaign中使用此資料。
page-status-flag: 從未啓動
uuid: 69af12cc-6f82-4977-1f53-aa7 bc26 f5 d7 e
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: reference
topic-tags: 資料管理活動
discoiquuid: 584ff893-9b1b-46c9-9628-714ab349ab88
context-tags: FileImport，主要
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Load file{#load-file}

## Description {#description}

![](assets/data_loading.png)

**[!UICONTROL Load file]** 活動可讓您將資料匯入單一結構化表單，以便在Adobe Campaign中使用此資料。資料會暫時匯入，而另一個活動則需要在Adobe Campaign資料庫中完全整合。

## Context of use {#context-of-use}

在設定活動時，定義擷取資料的方式。要載入的檔案可能是連絡人清單。

>[!CAUTION]
>
>僅會考量「扁平化」結構檔案，例如.txt、. csv等檔案。

您可以：

* Use the file structure to apply it to another file's data (recovered using the **[!UICONTROL Transfer file]** activity) or,
* 使用結構中的結構和資料，將其匯入Adobe Campaign。

## Configuration {#configuration}

活動設定需要兩個步驟。首先，您必須上傳範例檔案，才能定義預期的檔案結構。完成後，您可以指定將匯入資料的檔案來源。

>[!NOTE]
>
>範例檔案的資料用於設定活動，但未匯入。建議您使用包含少量資料的範例檔案。

1. Drag and drop a **[!UICONTROL Load file]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. 上傳範例檔案，讓您在匯入最終檔案時定義預期的結構。

   ![](assets/wkf_file_loading.png)

   Once the data file is uploaded, two new tabs appear in the activity: **[!UICONTROL File structure]** and **[!UICONTROL Column definition]**.

1. Go to the **[!UICONTROL File structure]** tab to view the structure that is automatically detected from the sample file.

   如果檔案結構錯誤偵測，您有幾個選項可更正可能的錯誤：

   * You can choose to use the structure of another file by selecting the **[!UICONTROL Detect structure from a new file]** option.
   * 您可以修改預設的偵測參數，將其調整為您的檔案。**[!UICONTROL File type]** 此欄位可讓您指定要匯入的檔案是由具有固定長度的欄所組成。In that case, you must also specify the maximum number of characters for each column in the **[!UICONTROL Column definition]** tab.

      All of the detection options necessary to correctly recover the data from the file are regrouped in **[!UICONTROL File format]**. 您可以修改這些新設定，然後再重新偵測活動中載入的最後一個檔案結構。To do this, use the **[!UICONTROL Apply configuration]** button. 例如，您可以指定不同的欄分隔符號。

      >[!NOTE]
      >
      >此操作會考量活動中載入的最後一個檔案。如果偵測到的檔案很大，資料預覽只會顯示前30行。

      ![](assets/wkf_file_loading3.png)

      In the **[!UICONTROL File format]** section, the **[!UICONTROL Check columns from file against column definitions]** option lets you verify that the columns of the file you are uploading correspond to the column definition.

      如果欄的數字和/或名稱不符合欄定義，則會在執行工作流程時顯示錯誤訊息。如果未啓用選項，則會在記錄檔中顯示警告。

      ![](assets/wkf_file_loading_check.png)

1. Go to the **[!UICONTROL Column definition]** tab to check the data format for each column and adjust the parameters if necessary.

   **[!UICONTROL Column definition]** 此標籤可讓您精確指定每個欄的資料結構，以便匯入不包含任何錯誤的資料(例如，使用null管理)，並使它符合Adobe Campaign資料庫中已存在的類型，以便日後操作。

   例如，您可以變更欄的標籤，選取其類型(字串、整數、日期等)。甚至指定錯誤處理。

   For more information, refer to the [Column format](../../automating/using/load-file.md#column-format) section.

   ![](assets/wkf_file_loading4.png)

1. **[!UICONTROL Execution]** 在標籤中，指定要處理載入資料的檔案：

   * 來自工作流程中傳入的轉變。
   * 是您在上一個步驟上傳的。
   * 是從本機電腦上傳的新檔案。The **[!UICONTROL Upload a new file from local machine]** option appears if uploading a first file was already defined in the workflow. 這可讓您上傳另一個檔案，如果目前的檔案不符合您的需求即可加以處理。

      ![](assets/wkf_file_loading1.png)

1. If the file that you want to load the data from is compressed into a GZIP file (.gz), select the **[!UICONTROL Decompression]** option in the **[!UICONTROL Add a pre-processing step]** field. 這可讓您在載入資料之前先解壓縮檔案。只有當檔案來自活動的傳入轉換時，才可使用此選項。
1. **[!UICONTROL Keep the rejects in a file]** 此選項可讓您下載包含在匯入期間發生錯誤的檔案，並將其套用至後處理階段。

   >[!NOTE]
   >
   >**[!UICONTROL Add date and time to the file name]** 此選項可讓您新增時間戳記，以建立包含拒絕之檔案的名稱。

   ![](assets/wkf_file_loading_keeprejects.png)

1. 確認活動的設定並儲存工作流程。

## Column format {#column-format}

載入範例檔案時，會自動偵測每個資料類型的預設參數。您可以修改這些預設參數，以指定要套用至資料的特定程序，尤其是當出現錯誤或空白值時。

To do this, select **[!UICONTROL Edit properties]** from the quick actions of the column whose format you would like to define. 隨即開啓欄格式詳細資料視窗。

![](assets/wkf_file_loading4.png)

然後，您可以修改每欄的格式設定。

欄格式可讓您定義每欄的值處理：

* **[!UICONTROL Ignore column]**：不會在資料載入期間處理此欄。
* **[!UICONTROL Data type]**：指定每欄預期的資料類型。
* **[!UICONTROL Format and separators]****屬性**：指定文字的屬性、時間、日期和數值格式，以及欄內容所指定的分隔符號。

   * **[!UICONTROL Maximum number of characters]**：指定字串類型欄的字元數目上限。

      載入包含固定長度的資料欄時，必須填寫此欄位。

   * **[!UICONTROL Letter case management]**：定義是否需要針對 **文字** 資料套用字元案例程序。
   * **[!UICONTROL White space management]**：指定 **文字** 資料字串中是否需要忽略某些空格。
   * **[!UICONTROL Time format]**&#x200B;指定 **日期[!UICONTROL Date format]、**&#x200B;時間&#x200B;**和**&#x200B;日期和時間&#x200B;**資料的格式。******
   * **[!UICONTROL Format]**：可讓您定義 **整數** 和 **浮動數字** 資料的數值格式。
   * **[!UICONTROL Separator]**：定義由欄上下文(千個分隔符號或小數點分隔符號)指定的分隔符號，用於 **日期**、 **時間**、 **日期和時間**、 **整數**&#x200B;和 **浮動數字** 資料。

* **[!UICONTROL Remapping of values]**：此欄位僅適用於欄詳細資料設定。它可讓您在匯入時轉換某些值。例如，您可以將「三個」轉換為「3」。
* **[!UICONTROL Error processing]**：定義發生錯誤時的行為。

   * **[!UICONTROL Ignore the value]**：值會被忽略。在工作流程執行記錄檔中會產生警告。
   * **[!UICONTROL Reject the line]**：整個系列未處理。
   * **[!UICONTROL Use a default value]**：取代造成預設值出現在 **[!UICONTROL Default value]** 欄位中的值。
   * **[!UICONTROL Use a default value in case the value is not remapped]**：取代造成 **[!UICONTROL Default value]** 在欄位中定義的預設值發生錯誤的值，除非為錯誤值定義對應(請參閱上述 **[!UICONTROL Remapping of values]** 選項)。
   * **[!UICONTROL Reject the line when there is no remapping value]**：除非為錯誤值定義對應(請參閱上述 **[!UICONTROL Remapping of values]** 選項)，否則不會處理整個行。
   >[!NOTE]
   >
   >**[!UICONTROL Error processing]** 關於匯入檔案中值的錯誤。例如，會遇到一種偶然資料類型(「整數」欄中的字母全部以字母表示)、一個字串包含超過授權數目的字元、一個具有附屬分隔符號的日期等等。不過，此選項不會擔心空白值管理產生的錯誤。

* **[!UICONTROL Default value]**：根據選取的錯誤處理來指定預設值。
* **[!UICONTROL Empty value management]**：指定如何在資料載入期間管理空值。

   * **[!UICONTROL Generate an error for numerical fields]**：僅會產生數值欄位的錯誤，否則會插入NULL值。
   * **[!UICONTROL Insert NULL in the corresponding field]**：授權空白值。因此插入值NULL。
   * **[!UICONTROL Generate an error]**：產生錯誤。

## Example {#example}

載入檔案活動主要是結構化傳輸檔案活動中的資料，以便將其整合至現有資料中。

下列範例顯示透過傳輸檔案活動自動下載載入檔案活動的結果，接著是更新資料活動。此工作流程旨在利用新的描述檔豐富Adobe Campaign資料庫，或使用從匯入檔案復原的資料更新現有設定檔。

1. Drag and drop a **[!UICONTROL Transfer file]** activity into your workflow and configure it in a way so that it recovers the file you would like.
1. Drag and drop a **[!UICONTROL Load file]** activity into your workflow and place it after the **[!UICONTROL Transfer file]** activity.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. In the **[!UICONTROL File to load]** section of the **[!UICONTROL Execution]** tab, check the **[!UICONTROL Use the file specified in the inbound transition]** option.

   ![](assets/wkf_file_loading8.png)

1. 依先前指定的方式設定您的活動。
1. Drag and drop an **[!UICONTROL Update data]** activity into your workflow and place it after the **[!UICONTROL Load file]** activity, then configure it. Refer to [Update data](../../automating/using/update-data.md).

工作流程開始後，會擷取上傳檔案的資料，然後用來充實Adobe Campaign資料庫。
