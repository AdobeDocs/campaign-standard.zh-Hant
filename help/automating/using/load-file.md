---
title: 載入檔案
description: 「載入檔案」活動可讓您以單一結構化形式匯入資料，以便在Adobe Campaign中使用此資料。
page-status-flag: never-activated
uuid: 69af12cc-6f82-4977-9f53-aa7bc26f5d7e
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: 584ff893-9b1b-46c9-9628-714ab349ab88
context-tags: fileImport,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2a8cb9aa0d018fec9d5b256beba079c5ec3afaf0
workflow-type: tm+mt
source-wordcount: '1799'
ht-degree: 0%

---


# 載入檔案 {#load-file}

## 說明 {#description}

![](assets/data_loading.png)

此活 **[!UICONTROL Load file]** 動可讓您匯入單一結構化格式的資料，以便在Adobe Campaign中使用此資料。 資料會暫時匯入，而另一個活動必須將它完全整合在Adobe Campaign資料庫中。

## 使用內容 {#context-of-use}

設定活動時，會定義資料擷取的方式。 例如，要載入的檔案可以是聯繫人清單。

>[!CAUTION]
>
>只考慮&quot;flat&quot;結構檔案，例如。txt、.csv等檔案。

您可以：

* 使用檔案結構將其應用於其他檔案的資料（使用活動恢復） **[!UICONTROL Transfer file]** 或
* 使用檔案的結構和資料，將其匯入Adobe Campaign。

## 配置 {#configuration}

活動配置涉及兩個步驟。 首先，您需要透過上傳範例檔案來定義預期的檔案結構。 完成此操作後，您可以指定要導入其資料的檔案的源。

>[!NOTE]
>
>示例檔案的資料用於配置活動，但不導入。 建議使用包含少量資料的範例檔案。

1. 將活動拖放 **[!UICONTROL Load file]** 到工作流程中。
1. 選擇活動，然後使用顯示的快 ![](assets/edit_darkgrey-24px.png) 速操作中的按鈕將其開啟。
1. 上傳範例檔案，讓您在匯入最終檔案時定義預期結構。

   ![](assets/wkf_file_loading.png)

   上傳資料檔案後，活動中會出現兩個新標籤： **[!UICONTROL File structure]** 和 **[!UICONTROL Column definition]**。

1. 轉至標籤 **[!UICONTROL File structure]** 以檢視從範例檔案自動偵測的結構。

   如果錯誤地檢測到檔案結構，您有幾個選項可以更正任何可能的錯誤：

   * 通過選擇選項，可以選擇使用另一個檔案的 **[!UICONTROL Detect structure from a new file]** 結構。
   * 您可以修改預設檢測參數，使其與檔案相適應。 欄位 **[!UICONTROL File type]** 可讓您指定您要匯入的檔案是否由長度固定的欄組成。 在這種情況下，您還必須指定標籤中各欄的字元數目上 **[!UICONTROL Column definition]** 限。

      正確從檔案中恢復資料所需的所有檢測選項都將重新分組 **[!UICONTROL File format]**。 您可以修改它們，然後考慮到這些新設定，重新檢測活動中載入的最後一個檔案的結構。 若要這麼做，請使用按 **[!UICONTROL Apply configuration]** 鈕。 例如，您可以指定不同的欄分隔符。

      >[!NOTE]
      >
      >此操作會考慮到活動中載入的最後一個檔案。 如果偵測到的檔案很大，資料預覽只會顯示前30行。

      ![](assets/wkf_file_loading3.png)

      在該節 **[!UICONTROL File format]** 中，選 **[!UICONTROL Check columns from file against column definitions]** 項可讓您驗證要上載的檔案的列是否與列定義對應。

      如果欄數和／或名稱不符合欄定義，則執行工作流程時會顯示錯誤訊息。 如果未激活該選項，日誌檔案中將顯示警告。

      ![](assets/wkf_file_loading_check.png)

1. 前往標籤 **[!UICONTROL Column definition]** 以檢查每欄的資料格式，並視需要調整參數。

   此標 **[!UICONTROL Column definition]** 簽可讓您精確指定每欄的資料結構，以匯入不含任何錯誤的資料（例如，使用null管理），並讓它符合Adobe Campaign資料庫中已存在的類型，以供日後作業使用。

   例如，您可以變更欄的標籤，並選取其類型（字串、整數、日期等） 甚至指定錯誤處理。

   有關詳細資訊，請參閱「列 [格式」部分](#column-format) 。

   ![](assets/wkf_file_loading4.png)

1. 在標籤 **[!UICONTROL Execution]** 中，指定是否要處理檔案以載入資料：

   * 來自工作流程的傳入轉場。
   * 是您在上一步驟中上傳的。
   * 是要從本機機器上傳的新檔案。 如果 **[!UICONTROL Upload a new file from local machine]** 上傳工作流程中已定義第一個檔案，就會顯示此選項。 這可讓您上傳其他檔案，以便在目前檔案不符合您的需求時加以處理。

      ![](assets/wkf_file_loading1.png)

1. 如果要從中載入資料的檔案壓縮到GZIP檔案(.gz)中，請在欄位中 **[!UICONTROL Decompression]** 選擇選 **[!UICONTROL Add a pre-processing step]** 項。 這可讓您在載入資料之前先解壓縮檔案。 只有當檔案來自活動的傳入轉換時，才可使用此選項。

   該 **[!UICONTROL Add a pre-processing step]** 欄位還允許您在將檔案導入資料庫之前對其進行解密。 有關如何使用加密檔案的詳細資訊，請參 [閱本節](../../automating/using/managing-encrypted-data.md)

1. 選 **[!UICONTROL Keep the rejects in a file]** 項可讓您下載包含匯入期間發生錯誤的檔案，並套用至後處理階段。 啟用此選項時，對外轉場會重新命名為「拒絕」。

   >[!NOTE]
   >
   >此選 **[!UICONTROL Add date and time to the file name]** 項可讓您將時間戳記新增包含拒絕之檔案的名稱。

   ![](assets/wkf_file_loading_keeprejects.png)

1. 確認活動的設定並儲存工作流程。

如果活動在執行工作流程後發生任何錯誤，請參閱日誌以獲取有關檔案中錯誤值的詳細資訊。 For more on workflows logs, refer to [this section](../../automating/using/monitoring-workflow-execution.md).

## 欄格式 {#column-format}

載入範例檔案時，會自動偵測欄格式，並使用每個資料類型的預設參數。 您可以修改這些預設參數，以指定要套用至資料的特定程式，尤其是當有錯誤或空值時。

要執行此操作，請 **[!UICONTROL Edit properties]** 從要定義其格式的列的快速操作中選擇。 將會開啟列格式詳細資訊窗口。

![](assets/wkf_file_loading4.png)

然後，您可以修改每列的格式。

列格式允許您定義每列的值處理：

* **[!UICONTROL Ignore column]**: 不會在資料載入期間處理此欄。
* **[!UICONTROL Data type]**: 指定每列所需的資料類型。
* **[!UICONTROL Format and separators]**，屬 **性**: 指定文字的屬性、時間、日期和數值格式，以及欄內容所指定的分隔符號。

   * **[!UICONTROL Maximum number of characters]**: 指定字串類型列的字元數上限。

      載入由長度固定的欄組成的檔案時，必須填入此欄位。

   * **[!UICONTROL Letter case management]**: 定義是否需要對文本資料應用字元大 **寫** 。
   * **[!UICONTROL White space management]**: 指定Text資料的字串中是否需要忽略某些 **空格** 。
   * **[!UICONTROL Time format]**, **[!UICONTROL Date format]**: 指定日期、時 **間和日**&#x200B;期 **** 和時間資料的格式 **** 。
   * **[!UICONTROL Format]**: 允許您定義整數和浮點數數數 **據****的數值格式** 。
   * **[!UICONTROL Separator]**: 定義由列上下文指定的分隔符（數值的千位或小數分隔符，日期和時間的千位分隔符） **Date**、 **Time**、 **Date和time**、 ******** Integer numberFloating data的分隔符。

* **[!UICONTROL Remapping of values]**: 此欄位僅在列詳細資訊配置中可用。 它可讓您在匯入特定值時加以轉換。 例如，您可將&quot;three&quot;轉換為&quot;3&quot;。
* **[!UICONTROL Error processing]**: 定義在遇到錯誤時的行為。

   * **[!UICONTROL Ignore the value]**: 值被忽略。 在工作流執行日誌中生成警告。
   * **[!UICONTROL Reject the line]**: 不處理整個行。
   * **[!UICONTROL Use a default value]**: 以在欄位中定義的預設值取代造成錯誤的 **[!UICONTROL Default value]** 值。
   * **[!UICONTROL Use a default value in case the value is not remapped]**: 以在欄位中定義的預設值取代導致錯誤的值，除非 **[!UICONTROL Default value]** 已針對錯誤值定義對應(請參閱上 **[!UICONTROL Remapping of values]** 述選項)。
   * **[!UICONTROL Reject the line when there is no remapping value]**: 除非為錯誤值定義了映射(請參閱上面的選 **[!UICONTROL Remapping of values]** 項)，否則不處理整行。
   >[!NOTE]
   >
   >**[!UICONTROL Error processing]** 有關匯入檔案中值的錯誤。 例如，遇到錯誤的資料類型（「4」全部是「整數」列的字母）、包含超過授權最大數字的字串、分隔符錯誤的日期等。 但是，此選項與空值管理產生的錯誤無關。

* **[!UICONTROL Default value]**: 根據選擇的錯誤處理指定預設值。
* **[!UICONTROL Empty value management]**: 指定在資料載入期間如何管理空值。

   * **[!UICONTROL Generate an error for numerical fields]**: 僅為數字欄位生成錯誤，否則插入NULL值。
   * **[!UICONTROL Insert NULL in the corresponding field]**: 授權空值。 因此插入值NULL。
   * **[!UICONTROL Generate an error]**: 如果值為空，則生成錯誤。

## 範例1: 更新資料庫 {#example-1-update-the-database}

載入檔案活動主要從傳輸檔案活動中構造資料，以便將其整合到現有資料中。

以下示例顯示通過傳輸檔案活動自動下載的載入檔案活動的結果，其後是更新資料活動。 此工作流程旨在以新的描述檔豐富Adobe Campaign資料庫，或使用從匯入檔案中復原的資料更新現有的描述檔。

![](assets/load_file_workflow_ex1.png)

1. 將活動拖放 **[!UICONTROL Transfer file]** 至您的工作流程中，並以某種方式加以設定，以便它可以恢復您想要的檔案。
1. 將活動拖放 **[!UICONTROL Load file]** 到工作流程中，並將其放在活動之 **[!UICONTROL Transfer file]** 後。
1. 選擇活動，然後使用顯示的快 ![](assets/edit_darkgrey-24px.png) 速操作中的按鈕將其開啟。
1. 在標籤 **[!UICONTROL File to load]** 的區段中 **[!UICONTROL Execution]** ，勾選選 **[!UICONTROL Use the file specified in the inbound transition]** 選項。

   ![](assets/wkf_file_loading8.png)

1. 依照先前的指定設定您的活動。
1. 將活動拖放 **[!UICONTROL Update data]** 到工作流程中，並將其置於活動之 **[!UICONTROL Load file]** 後，再加以設定。 請參閱 [更新資料](../../automating/using/update-data.md)。

工作流程開始後，會擷取上傳檔案的資料，然後用來豐富Adobe Campaign資料庫。

## 範例2: 傳送包含豐富欄位的電子郵件 {#example-2-email-with-enriched-fields}

<!--A new example showing how to send an email containing additional data retrieved from a load file activity has been added. [Read more](example-2-email-with-enriched-fields)-->

此外，載入檔案活動也可讓您在相同的工作流程中，從外部檔案傳送內含其他資料的電子郵件。

以下範例說明如何透過載入檔案活動，使用從外部檔案擷取的其他資料來傳送電子郵件。 在此範例中，外部檔案包含描述檔清單及其關聯的帳號。 您想要匯入此資料，以傳送電子郵件給每個設定檔及其帳號。

![](assets/load_file_workflow_ex2.png)

1. 將活動拖放 **[!UICONTROL Query]** 到工作流程中，並開啟它以定義主要目標。

   <!--The Query activity is presented in the [Query](../../automating/using/query.md) section.-->

1. 拖放活動 **[!UICONTROL Load file]** 以指派部分資料至描述檔。 在此示例中，載入包含與資料庫的某些配置檔案相對應的帳戶號的檔案。

   ![](assets/load_file_activity.png)

1. 將活動拖放至 **[!UICONTROL Enrichment]** 您的工作流程中，並將載入檔案和查詢活動連結至工作流程。

1. 在擴充 **[!UICONTROL Advanced relations]** 活動的頁籤中，選擇 **[!UICONTROL 0 or 1 cardinality simple link]** 並定義要用於調節的欄位。 在這裡，我們使用姓氏來協調資料與資料庫配置檔案。

   ![](assets/load_file_enrichment_relation.png)

1. 在標籤 **[!UICONTROL Additional data]** 中，選取您要在電子郵件中使用的元素。 在此處選擇帳戶號（從通過載入檔案活動檢索的檔案中的列）。

   ![](assets/load_file_enrichment_select_element.png)

   <!--![](assets/load_file_enrichment_additional_data.png)-->

   有關詳細資訊，請參 [閱Enrichment](../../automating/using/enrichment.md) 節。

1. 將活動拖放 **[!UICONTROL Segmentation]** 至工作流程中，並開啟它以調整主要目標。

   ![](assets/load_file_segmentation.png)

   如需詳細資訊，請參閱「區 [段](../../automating/using/segmentation.md) 」區段。

1. 將活動拖放 **[!UICONTROL Email delivery]** 到工作流程中並加以開啟。

   <!--The Email delivery activity is presented in the [Email delivery](../../automating/using/email-delivery.md) section.-->

1. 新增個人化欄位，並從節點選取擴充活動（此處為帳戶編號）中定義的其他 **[!UICONTROL Additional data (targetData)]** 資料。 如此可動態擷取電子郵件內容中每個描述檔的帳號。

   ![](assets/load_file_perso_field.png)

1. 儲存電子郵件並啟動工作流程。

電子郵件會傳送至目標。 每個描述檔都會收到含有其對應帳號的電子郵件。

![](assets/load_file_email.png)
