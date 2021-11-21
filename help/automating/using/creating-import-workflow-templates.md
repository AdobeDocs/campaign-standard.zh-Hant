---
title: 建立工作流程範本以匯入資料
description: 了解如何建立工作流程範本以匯入資料。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
role: Data Architect
level: Experienced
exl-id: 5974a52c-8721-4575-b452-2982d6497235
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '1172'
ht-degree: 1%

---

# 建立工作流程範本以匯入資料 {#import-workflow-template}

如果您需要定期匯入具有相同結構的檔案，使用匯入範本是最佳作法。

此範例說明如何預先設定可重複用於匯入來自Adobe Campaign資料庫中CRM之設定檔的工作流程。

1. 從建立新的工作流模板 **[!UICONTROL Resources > Templates > Workflow templates]**.
1. 新增下列活動：

   * **[!UICONTROL Load file]**:定義包含要匯入之資料的檔案的預期結構。

      >[!NOTE]
      >
      >您只能從單一檔案匯入資料。 如果工作流有多個 **[!UICONTROL Load file]** 活動時，每次都會使用相同的檔案。

   * **[!UICONTROL Reconciliation]**:將匯入的資料與資料庫資料進行調解。
   * **[!UICONTROL Segmentation]**:建立篩選器以根據記錄是否可協調而以不同方式處理記錄。
   * **[!UICONTROL Deduplication]**:在將傳入檔案插入資料庫之前，先從該檔案中刪除重複資料。
   * **[!UICONTROL Update data]**:使用匯入的設定檔更新資料庫。

   ![](assets/import_template_example0.png)

1. 設定 **[!UICONTROL Load file]** 活動：

   * 上傳範例檔案以定義預期的結構。 範例檔案應僅包含幾行，但匯入所需的所有欄。 檢查並編輯檔案格式，確保正確設定每欄的類型：文字、日期、整數等。 例如：

      ```
      lastname;firstname;birthdate;email;crmID
      Smith;Hayden;23/05/1989;hayden.smith@mailtest.com;123456
      ```

   * 在 **[!UICONTROL File to load]** 部分，選擇 **[!UICONTROL Upload a new file from the local machine]** 並將欄位留空。 每次從此模板建立新工作流時，只要與定義的結構對應，您都可以在此處指定所需的檔案。

      您可以使用任何選項，但必須據以修改範本。 例如，若您選取 **[!UICONTROL Use the file specified in the inbound transition]**，您可以新增 **[!UICONTROL Transfer file]** 活動，以擷取要從FTP/SFTP伺服器匯入的檔案。

      如果您希望使用者能夠下載包含匯入期間發生錯誤的檔案，請核取 **[!UICONTROL Keep the rejects in a file]** 選項和指定 **[!UICONTROL File name]**.

      ![](assets/import_template_example1.png)

1. 設定 **[!UICONTROL Reconciliation]** 活動。 此活動在此背景下的目的是識別傳入的資料。

   * 在 **[!UICONTROL Relations]** 索引標籤，選取 **[!UICONTROL Create element]** 和定義匯入資料與收件者目標維度之間的連結(請參閱 [目標維度和資源](../../automating/using/query.md#targeting-dimensions-and-resources))。 在此範例中， **CRM ID** 「自訂」欄位可用來建立連接條件。 使用您需要的欄位或欄位組合，只要它允許識別唯一記錄即可。
   * 在 **[!UICONTROL Identification]** 標籤，保留 **[!UICONTROL Identify the document from the working data]** 選項。

   ![](assets/import_template_example2.png)

1. 設定 **[!UICONTROL Segmentation]** 在一個轉變中擷取已調解的收件者，以及在第二個轉變中具有足夠資料無法調解的收件者。

   之後，可以使用與已調解收件者的轉變來更新資料庫。 然後，如果檔案中有最少一組資訊可用，則具有未知收件者的轉變可用於在資料庫中建立新的收件者項目。

   無法調解且沒有足夠資料的收件者會在補充的出站轉變中選取，並可匯出至個別檔案或僅遭忽略。

   * 在 **[!UICONTROL General]** 索引標籤，設定 **[!UICONTROL Resource type]** to **[!UICONTROL Temporary resource]** 選取 **[!UICONTROL Reconciliation]** 作為目標集。
   * 在 **[!UICONTROL Advanced options]** 頁簽，檢查 **[!UICONTROL Generate complement]** 選項，查看資料庫中是否無法插入任何記錄。 如有需要，您可以對補充資料套用進一步處理：檔案匯出、清單更新等。
   * 在 **[!UICONTROL Segments]** 索引標籤，在入站母體上新增篩選條件，以僅選取設定檔的CRM ID不等於0的記錄。 這樣，將從該子集中選擇與資料庫的配置檔案協調的檔案中的資料。

      ![](assets/import_template_example3.png)

   * 新增第二個區段，以選取有足夠資料可插入資料庫的未調解記錄。 例如：電子郵件地址、名字和姓氏。 未調解的記錄其設定檔的CRM ID值等於0。

      ![](assets/import_template_example3_2.png)

   * 未在前兩個子集中選擇的所有記錄都將在 **[!UICONTROL Complement]**.

1. 設定 **[!UICONTROL Update data]** 位於 **[!UICONTROL Segmentation]** 先前設定的活動。

   * 選擇 **[!UICONTROL Update]** as **[!UICONTROL Operation type]** 因為入站轉變只包含資料庫中已存在的收件者。
   * 在 **[!UICONTROL Identification]** 索引標籤，選取 **[!UICONTROL Using reconciliation criteria]** 並定義 **[!UICONTROL Dimension to update]**  — 此情況下的設定檔 — 以及 **[!UICONTROL Reconciliation]** 活動。 在此範例中， **CRM ID** 已使用自訂欄位。

      ![](assets/import_template_example6.png)

   * 在 **[!UICONTROL Fields to update]** 頁簽，指定「配置檔案」維中的欄位，以使用檔案中相應列的值進行更新。 如果檔案列的名稱與收件人維欄位的名稱相同或幾乎相同，則可以使用魔術棒按鈕自動匹配不同欄位。

      ![](assets/import_template_example6_2.png)

      >[!NOTE]
      >
      >如果您打算將直接郵件傳送至這些設定檔，請務必包含郵遞區號，因為此資訊對直接郵件提供者至關重要。 同時請確定 **[!UICONTROL Address specified]** 方塊。 若要從工作流程更新此選項，只需將元素新增至要更新的欄位，然後指定 **1** as **[!UICONTROL Source]** ，然後選取 `postalAddress/@addrDefined` 欄位 **[!UICONTROL Destination]**. 有關直接郵件和使用的詳細資訊 **[!UICONTROL Address specified]** 選項，請參閱 [此文檔](../../channels/using/about-direct-mail.md#recommendations).

1. 設定 **[!UICONTROL Deduplication]** 位於包含未協調設定檔之轉變之後的活動：

   * 在 **[!UICONTROL Properties]** 頁簽，設定 **[!UICONTROL Resource type]** 至 **[!UICONTROL Reconciliation]** 工作流程的活動。

      ![](assets/import_template_example4.png)

   * 在此範例中，電子郵件欄位可用來尋找唯一的設定檔。 您可以使用任何您確定已填入的欄位，以及唯一組合的一部分。
   * 選擇 **[!UICONTROL Deduplication method]**. 在這種情況下，應用程式會自動決定在出現重複時要保留哪些記錄。

   ![](assets/import_template_example7.png)

1. 設定 **[!UICONTROL Update data]** 位於 **[!UICONTROL Deduplication]** 先前設定的活動。

   * 選擇 **[!UICONTROL Insert only]** as **[!UICONTROL Operation type]** 因為入站轉變只包含資料庫中不存在的設定檔。
   * 在 **[!UICONTROL Identification]** 索引標籤，選取 **[!UICONTROL Using reconciliation criteria]** 並定義 **[!UICONTROL Dimension to update]**  — 此情況下的設定檔 — 以及 **[!UICONTROL Reconciliation]** 活動。 在此範例中， **CRM ID** 已使用自訂欄位。

      ![](assets/import_template_example6.png)

   * 在 **[!UICONTROL Fields to update]** 頁簽，指定「配置檔案」維中的欄位，以使用檔案中相應列的值進行更新。 如果檔案列的名稱與收件人維欄位的名稱相同或幾乎相同，則可以使用魔術棒按鈕自動匹配不同欄位。

      ![](assets/import_template_example6_2.png)

      >[!NOTE]
      >
      >如果您打算將直接郵件傳送至這些設定檔，請務必包含郵遞區號，因為此資訊對直接郵件提供者至關重要。 同時請確定 **[!UICONTROL Address specified]** 方塊。 若要從工作流程更新此選項，只需將元素新增至要更新的欄位，然後指定 **1** as **[!UICONTROL Source]** ，然後選取 **[郵遞區號/@addrDefined]** 欄位 **[!UICONTROL Destination]**. 有關直接郵件和使用的詳細資訊 **[!UICONTROL Address specified]** 選項，請參閱 [此文檔](../../channels/using/about-direct-mail.md#recommendations).

1. 在 **[!UICONTROL Segmentation]** 活動，新增 **[!UICONTROL Extract file]** 活動與 **[!UICONTROL Transfer file]** 活動。 設定這些活動以匯出您需要的欄，並在FTP或SFTP伺服器上傳輸檔案，您可在其中擷取檔案。
1. 新增 **[!UICONTROL End]** 活動並儲存工作流程範本。

範本現在可供使用，並可供所有新工作流程使用。 然後，就需要全部，以指定包含要匯入的資料的檔案 **[!UICONTROL Load file]** 活動。

![](assets/import_template_example9.png)
