---
title: 匯入資料
seo-title: 匯入資料
description: 匯入資料
seo-description: 瞭解如何使用工作流程匯入資料。
page-status-flag: 從未啓動
uuid: d909d26a-cf50-46aff-ae09-f0 d7258 ca27
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: reference
topic-tags: 工作流程一般運作
discoiquuid: 75b86165-dcbd-4bb7-b703-ed769 f489 b16
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 36727e82d3aa73add6116fa2916752ff0e407d9d

---


# Importing data{#importing-data}

## Collecting data {#collecting-data}

您可以從檔案收集資料，以便處理和/或在Adobe Campaign資料庫中匯入資料。

* **[!UICONTROL Load file]** 活動可讓您將資料匯入單一結構化表單，以便在Adobe Campaign中使用此資料。資料會暫時匯入，而另一個活動則需要在Adobe Campaign資料庫中完全整合。
* **[!UICONTROL Transfer file]** 活動可讓您接收或傳送檔案、測試是否存在檔案，或在Adobe Campaign中列出檔案。

   You can use this activity before a **[!UICONTROL Load file]** in case you need to retrieve the file from an external source.

## Import best practices {#import-best-practices}

小心並遵循下面幾個簡單的規則有助於確保資料庫資料一致性，以及避免資料庫更新或資料匯出時常見錯誤。

### Using import templates {#using-import-templates}

Most import workflows should contain the following activities: **[!UICONTROL Load file]**, **[!UICONTROL Reconciliation]**, **[!UICONTROL Segmentation]**, **[!UICONTROL Deduplication]**, **[!UICONTROL Update data]**.

使用匯入範本可讓您輕鬆準備類似的匯入，並確保資料庫中的資料一致性。

In many projects, imports are built without **[!UICONTROL Deduplication]** activity because the files used in the project do not have duplicates. 複製不同檔案有時會出現重復。然後去重復化很困難。因此，去重復化步驟在所有匯入工作流程中都是很好的預防措施。

請勿基於接收資料一致且正確的假設，或由IT部門或Adobe Campaign監督或將負責處理。在專案期間，請記住資料清除。在匯入資料時消除重復、協調和維護一致性。

[範例中提供用於匯入資料的一般工作流程範本範例：匯入工作流程範本](../../automating/using/importing-data.md#example--import-workflow-template) 區段。

>[!NOTE]
>
>You can also use [import templates](../../automating/using/importing-data-with-import-templates.md). 它們是由管理員定義的工作流程範本，在啓動後，只提供可能指定包含要匯入之資料的檔案。

### Using flat file formats {#using-flat-file-formats}

最有效的匯入格式是平面檔案。可在資料庫層級以大量模式匯入平面檔案。

例如：

* 分隔符號：tab或分號
* 含有標題的第一行
* 無字串分隔字元
* 日期格式：YYYY/MM/DD HH：mm：SS

要匯入的檔案範例：

```
lastname;firstname;birthdate;email;crmID
Smith;Hayden;23/05/1989;hayden.smith@example.com;124365
Mars;Daniel;17/11/1987;dannymars@example.com;123545
Smith;Clara;08/02/1989;hayden.smith@example.com;124567
Durance;Allison;15/12/1978;allison.durance@example.com;120987
```

### Using compression {#using-compression}

使用壓縮檔案進行匯入和匯出。預設支援GZIP。You can add pre-processing when importing files or post-processing when extracting data, respectively in the **[!UICONTROL Load file]** and **[!UICONTROL Extract file]** workflow activities.

### Importing in Delta mode {#importing-in-delta-mode}

定期匯入必須以delta模式完成。這表示只會將修改或新資料傳送至Adobe Campaign，而非每次表格。

完整匯入只能用於初始載入。

### Maintaining consistency {#maintaining-consistency}

若要維持Adobe Campaign資料庫中的資料一致性，請遵循下列原則：

* 如果匯入的資料符合Adobe Campaign中的參考表格，則應在工作流程中與該表格協調。不符合不符合的記錄。
* Ensure that the imported data is always **"normalized"** (email, phone number, direct mail address) and that this normalization is reliable and will not change over the years. 如果情況並非如此，有些重復項目可能會出現在資料庫中，而Adobe Campaign不會提供工具來執行「模糊」比對，因此難以管理和移除。
* 交易資料應具有協調索引鍵並與現有資料協調，以避免建立重復項目。
* **依序匯入相關檔案**。如果匯入由多個需要相互依存的檔案組成，工作流程應確定檔案是以正確順序匯入。當檔案失敗時，其他檔案將無法匯入。
* **在匯入資料時消除重復**、協調和維護一致性。

## Example: Import workflow template {#example--import-workflow-template}

如果您需要定期匯入相同結構的檔案，則使用匯入範本是最佳做法。

此範例顯示如何預先設定工作流程，以便重新使用可從Adobe Campaign資料庫中CRM匯入的描述檔。

1. Create a new workflow template from **[!UICONTROL Resources > Templates > Workflow templates]**.
1. 新增下列活動：

   * **[!UICONTROL Load file]**：定義包含要匯入資料之檔案的預期結構。

      >[!NOTE]
      >
      >您只能從單一檔案匯入資料。If the workflow has multiple **[!UICONTROL Load file]** activities, the same file will be used each time.

   * **[!UICONTROL Reconciliation]**：將匯入的資料與資料庫資料協調。
   * **[!UICONTROL Segmentation]**：根據是否能協調記錄，建立篩選器以不同的方式建立記錄。
   * **[!UICONTROL Deduplication]**：將傳入檔案中的資料複製，然後再插入資料庫中。
   * **[!UICONTROL Update data]**：使用匯入的設定檔更新資料庫。
   ![](assets/import_template_example0.png)

1. Configure the **[!UICONTROL Load file]** activity:

   * 上傳範例檔案以定義預期的結構。範例檔案只應包含幾行，但所有必要欄位都應包含在內。檢查並編輯檔案格式，確定每欄的類型設定正確：文字、日期、整數等。例如：

      ```
      lastname;firstname;birthdate;email;crmID
      Smith;Hayden;23/05/1989;hayden.smith@mailtest.com;123456
      ```

   * In the **[!UICONTROL File to load]** section, select **[!UICONTROL Upload a new file from the local machine]** and leave the field blank. 每次從此範本建立新工作流程時，您可以在此處指定所要的檔案，其中長時間符合定義的結構。

      您可以使用任一選項，但您必須據以修改範本。For example, if you select **[!UICONTROL Use the file specified in the inbound transition]**, you can add a **[!UICONTROL Transfer file]** activity before to retrieve the file to import from a FTP/SFTP server.

      If you want users to be able to download a file containing errors that occurred during an import, check the **[!UICONTROL Keep the rejects in a file]** option and specify the **[!UICONTROL File name]**.

      ![](assets/import_template_example1.png)

1. Configure the **[!UICONTROL Reconciliation]** activity. 此項活動的目的在於識別傳入的資料。

   * In the **[!UICONTROL Relations]** tab, select **[!UICONTROL Create element]** and define a link between the imported data and the recipients targeting dimension (see [Targeting dimensions and resources](../../automating/using/query.md#targeting-dimensions-and-resources)). In this example, the **CRM ID** custom field is used to create the join condition. 您可以使用欄位或所需欄位組合來識別獨特記錄。
   * **[!UICONTROL Identification]** 在標籤中，將 **[!UICONTROL Identify the document from the working data]** 選項解除勾選。
   ![](assets/import_template_example2.png)

1. Configure the **[!UICONTROL Segmentation]** activity to retrieve reconciled recipients in one transition and recipients that could not be reconciled but who have enough data in a second transition.

   然後可使用協調收件者的轉換來更新資料庫。然後，若檔案中有最少的資訊集，則可使用未知收件者的轉換來建立資料庫中新的收件者項目。

   無法協調且無法在輔助轉場中選取足夠資料的收件者，可以匯出成單獨的檔案，或只會被忽略。

   * In the **[!UICONTROL General]** tab of the activity, set the **[!UICONTROL Resource type]** to **[!UICONTROL Temporary resource]** and select **[!UICONTROL Reconciliation]** as the targeted set.
   * In the **[!UICONTROL Advanced options]** tab, check the **[!UICONTROL Generate complement]** option to be able to see if any record cannot be inserted in the database. 如果您需要，則可以將進一步處理套用至互補資料：檔案匯出、清單更新等等
   * In the first segment of the **[!UICONTROL Segments]** tab, add a filtering condition on the inbound population to select only records for which the profile's CRM ID is not equal to 0. 如此，就會在該子集中選取檔案中與資料庫設定檔協調的資料。

      ![](assets/import_template_example3.png)

   * 新增第二個區段，選取已在資料庫中插入足夠資料的未協調記錄。例如：電子郵件地址、名字和姓氏。未協調的記錄的CRM ID值等於0。

      ![](assets/import_template_example3_2.png)

   * All records that are not selected in the first two subsets are selected in the **[!UICONTROL Complement]**.

1. Configure the **[!UICONTROL Update data]** activity located after the first outbound transition of the **[!UICONTROL Segmentation]** activity configured previously.

   * Select **[!UICONTROL Update]** as **[!UICONTROL Operation type]** since the inbound transition only contains recipients already present in the database.
   * **[!UICONTROL Identification]** 在標籤中，選取 **[!UICONTROL Using reconciliation criteria]** 並定義此案例 **[!UICONTROL Dimension to update]** 中-以及 **[!UICONTROL Reconciliation]** 在活動中建立的連結之間的索引鍵。In this example, the **CRM ID** custom field is used.

      ![](assets/import_template_example6.png)

   * **[!UICONTROL Fields to update]** 在標籤中，指定「描述檔」維度中的欄位，以搭配檔案中對應欄的值更新。如果檔案欄的名稱與收件者維度欄位的名稱相同或幾乎相同，您可以使用魔術棒按鈕自動比對不同欄位。

      ![](assets/import_template_example6_2.png)

      >[!NOTE]
      >
      >如果您打算將直接郵寄傳送至這些個人檔案，請務必加入郵寄地址，因為此資訊對直接郵件提供者而言是不可或缺的資訊。Also make sure that the **[!UICONTROL Address specified]** box in your profiles' information is checked. To update this option from a workflow, simply add an element to the fields to update, and specify **1** as **[!UICONTROL Source]** and select the **[postalAddress/@addrDefined]** field as **[!UICONTROL Destination]**. For more on direct mail and the use of the **[!UICONTROL Address specified]** option, see [this document](../../channels/using/about-direct-mail.md#recommendations).

1. Configure the **[!UICONTROL Deduplication]** activity located after the transition containing unreconciled profiles:

   * **[!UICONTROL Properties]** 在標籤中，將 **[!UICONTROL Resource type]** 從工作流程 **[!UICONTROL Reconciliation]** 活動產生的暫存資源設定為。

      ![](assets/import_template_example4.png)

   * 在這個範例中，會使用電子郵件欄位尋找獨特的個人檔案。您可以使用您確定的任何欄位，以及唯一組合的一部分。
   * Choose a **[!UICONTROL Deduplication method]**. 在此情況下，應用程式會自動決定會保留哪些記錄以備重復使用。
   ![](assets/import_template_example7.png)

1. Configure the **[!UICONTROL Update data]** activity located after the **[!UICONTROL Deduplication]** activity configured previously.

   * Select **[!UICONTROL Insert only]** as **[!UICONTROL Operation type]** since the inbound transition only contains profiles not present in the database.
   * **[!UICONTROL Identification]** 在標籤中，選取 **[!UICONTROL Using reconciliation criteria]** 並定義此案例 **[!UICONTROL Dimension to update]** 中-以及 **[!UICONTROL Reconciliation]** 在活動中建立的連結之間的索引鍵。In this example, the **CRM ID** custom field is used.

      ![](assets/import_template_example6.png)

   * **[!UICONTROL Fields to update]** 在標籤中，指定「描述檔」維度中的欄位，以搭配檔案中對應欄的值更新。如果檔案欄的名稱與收件者維度欄位的名稱相同或幾乎相同，您可以使用魔術棒按鈕自動比對不同欄位。

      ![](assets/import_template_example6_2.png)

      >[!NOTE]
      >
      >如果您打算將直接郵寄傳送至這些個人檔案，請務必加入郵寄地址，因為此資訊對直接郵件提供者而言是不可或缺的資訊。Also make sure that the **[!UICONTROL Address specified]** box in your profiles' information is checked. To update this option from a workflow, simply add an element to the fields to update, and specify **1** as **[!UICONTROL Source]** and select the **[postalAddress/@addrDefined]** field as **[!UICONTROL Destination]**. For more on direct mail and the use of the **[!UICONTROL Address specified]** option, see [this document](../../channels/using/about-direct-mail.md#recommendations).

1. **[!UICONTROL Segmentation]** 在活動第三次轉換後，如果您想追蹤未插入資料庫中的資料，請新增 **[!UICONTROL Extract file]** 活動和 **[!UICONTROL Transfer file]** 活動。設定這些活動以匯出您需要的欄，並在FTP或SFTP伺服器上傳輸檔案，以便擷取它。
1. Add an **[!UICONTROL End]** activity and save the workflow template.

範本現在可用於每個新工作流程中。All is needed is then to specify the file containing the data to import in the **[!UICONTROL Load file]** activity.

![](assets/import_template_example9.png)

