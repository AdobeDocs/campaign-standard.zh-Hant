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

1. 從&#x200B;**[!UICONTROL Resources > Templates > Workflow templates]**&#x200B;建立新的工作流模板。
1. 新增下列活動：

   * **[!UICONTROL Load file]**:定義包含要匯入之資料的檔案的預期結構。

      >[!NOTE]
      >
      >您只能從單一檔案匯入資料。 如果工作流有多個&#x200B;**[!UICONTROL Load file]**&#x200B;活動，則每次都會使用相同的檔案。

   * **[!UICONTROL Reconciliation]**:將匯入的資料與資料庫資料進行調解。
   * **[!UICONTROL Segmentation]**:建立篩選器以根據記錄是否可協調而以不同方式處理記錄。
   * **[!UICONTROL Deduplication]**:在將傳入檔案插入資料庫之前，先從該檔案中刪除重複資料。
   * **[!UICONTROL Update data]**:使用匯入的設定檔更新資料庫。

   ![](assets/import_template_example0.png)

1. 配置&#x200B;**[!UICONTROL Load file]**&#x200B;活動：

   * 上傳範例檔案以定義預期的結構。 範例檔案應僅包含幾行，但匯入所需的所有欄。 檢查並編輯檔案格式，確保正確設定每欄的類型：文字、日期、整數等。 例如：

      ```
      lastname;firstname;birthdate;email;crmID
      Smith;Hayden;23/05/1989;hayden.smith@mailtest.com;123456
      ```

   * 在&#x200B;**[!UICONTROL File to load]**&#x200B;區段中，選取&#x200B;**[!UICONTROL Upload a new file from the local machine]**&#x200B;並將欄位留空。 每次從此模板建立新工作流時，只要與定義的結構對應，您都可以在此處指定所需的檔案。

      您可以使用任何選項，但必須據以修改範本。 例如，如果您選取&#x200B;**[!UICONTROL Use the file specified in the inbound transition]**，則可先新增&#x200B;**[!UICONTROL Transfer file]**&#x200B;活動，再擷取要從FTP/SFTP伺服器匯入的檔案。

      如果希望用戶能夠下載包含導入期間發生錯誤的檔案，請檢查&#x200B;**[!UICONTROL Keep the rejects in a file]**&#x200B;選項並指定&#x200B;**[!UICONTROL File name]**。

      ![](assets/import_template_example1.png)

1. 配置&#x200B;**[!UICONTROL Reconciliation]**&#x200B;活動。 此活動在此背景下的目的是識別傳入的資料。

   * 在&#x200B;**[!UICONTROL Relations]**&#x200B;標籤中，選取&#x200B;**[!UICONTROL Create element]**&#x200B;並定義匯入資料與收件者目標維度之間的連結（請參閱[目標維度與資源](../../automating/using/query.md#targeting-dimensions-and-resources)）。 在此範例中，使用&#x200B;**CRM ID**&#x200B;自訂欄位來建立連結條件。 使用您需要的欄位或欄位組合，只要它允許識別唯一記錄即可。
   * 在&#x200B;**[!UICONTROL Identification]**&#x200B;標籤中，取消勾選&#x200B;**[!UICONTROL Identify the document from the working data]**&#x200B;選項。

   ![](assets/import_template_example2.png)

1. 設定&#x200B;**[!UICONTROL Segmentation]**&#x200B;活動，以在一個轉變中擷取已調解的收件者，以及在第二個轉變中無法調解但擁有足夠資料的收件者。

   之後，可以使用與已調解收件者的轉變來更新資料庫。 然後，如果檔案中有最少一組資訊可用，則具有未知收件者的轉變可用於在資料庫中建立新的收件者項目。

   無法調解且沒有足夠資料的收件者會在補充的出站轉變中選取，並可匯出至個別檔案或僅遭忽略。

   * 在活動的&#x200B;**[!UICONTROL General]**&#x200B;標籤中，將&#x200B;**[!UICONTROL Resource type]**&#x200B;設為&#x200B;**[!UICONTROL Temporary resource]**&#x200B;並選取&#x200B;**[!UICONTROL Reconciliation]**&#x200B;作為目標集。
   * 在&#x200B;**[!UICONTROL Advanced options]**&#x200B;標籤中，檢查&#x200B;**[!UICONTROL Generate complement]**&#x200B;選項，以查看資料庫中是否無法插入任何記錄。 如有需要，您可以對補充資料套用進一步處理：檔案匯出、清單更新等。
   * 在&#x200B;**[!UICONTROL Segments]**&#x200B;標籤的第一個區段中，對入站母體新增篩選條件，以僅選取設定檔的CRM ID不等於0的記錄。 這樣，將從該子集中選擇與資料庫的配置檔案協調的檔案中的資料。

      ![](assets/import_template_example3.png)

   * 新增第二個區段，以選取有足夠資料可插入資料庫的未調解記錄。 例如：電子郵件地址、名字和姓氏。 未調解的記錄其設定檔的CRM ID值等於0。

      ![](assets/import_template_example3_2.png)

   * 未在前兩個子集中選擇的所有記錄都在&#x200B;**[!UICONTROL Complement]**&#x200B;中選擇。

1. 設定位於先前設定之&#x200B;**[!UICONTROL Segmentation]**&#x200B;活動之第一個出站轉變之後的&#x200B;**[!UICONTROL Update data]**&#x200B;活動。

   * 選擇&#x200B;**[!UICONTROL Update]**&#x200B;作為&#x200B;**[!UICONTROL Operation type]**，因為入站轉變僅包含資料庫中已存在的收件者。
   * 在&#x200B;**[!UICONTROL Identification]**&#x200B;索引標籤中，選取&#x200B;**[!UICONTROL Using reconciliation criteria]**&#x200B;並定義&#x200B;**[!UICONTROL Dimension to update]** — 此例中的設定檔 — 與&#x200B;**[!UICONTROL Reconciliation]**&#x200B;活動中建立的連結之間的索引鍵。 在此範例中，使用&#x200B;**CRM ID**&#x200B;自訂欄位。

      ![](assets/import_template_example6.png)

   * 在&#x200B;**[!UICONTROL Fields to update]**&#x200B;索引標籤中，指出「設定檔」維度中的欄位，以使用檔案中對應欄的值更新。 如果檔案列的名稱與收件人維欄位的名稱相同或幾乎相同，則可以使用魔術棒按鈕自動匹配不同欄位。

      ![](assets/import_template_example6_2.png)

      >[!NOTE]
      >
      >如果您打算將直接郵件傳送至這些設定檔，請務必包含郵遞區號，因為此資訊對直接郵件提供者至關重要。 也請確定已勾選設定檔資訊中的&#x200B;**[!UICONTROL Address specified]**&#x200B;方塊。 若要從工作流程更新此選項，只需將元素新增至要更新的欄位，並將&#x200B;**1**&#x200B;指定為&#x200B;**[!UICONTROL Source]**，然後將`postalAddress/@addrDefined`欄位選為&#x200B;**[!UICONTROL Destination]**&#x200B;即可。 有關直接郵件和使用&#x200B;**[!UICONTROL Address specified]**&#x200B;選項的詳細資訊，請參閱[本文檔](../../channels/using/about-direct-mail.md#recommendations)。

1. 設定位於包含未調解設定檔之轉變之後的&#x200B;**[!UICONTROL Deduplication]**&#x200B;活動：

   * 在&#x200B;**[!UICONTROL Properties]**&#x200B;標籤中，將&#x200B;**[!UICONTROL Resource type]**&#x200B;設定為從工作流的&#x200B;**[!UICONTROL Reconciliation]**&#x200B;活動生成的臨時資源。

      ![](assets/import_template_example4.png)

   * 在此範例中，電子郵件欄位可用來尋找唯一的設定檔。 您可以使用任何您確定已填入的欄位，以及唯一組合的一部分。
   * 選擇&#x200B;**[!UICONTROL Deduplication method]**。 在這種情況下，應用程式會自動決定在出現重複時要保留哪些記錄。

   ![](assets/import_template_example7.png)

1. 設定位於先前設定之&#x200B;**[!UICONTROL Deduplication]**&#x200B;活動之後的&#x200B;**[!UICONTROL Update data]**&#x200B;活動。

   * 選擇&#x200B;**[!UICONTROL Insert only]**&#x200B;作為&#x200B;**[!UICONTROL Operation type]**，因為入站轉變僅包含資料庫中不存在的配置檔案。
   * 在&#x200B;**[!UICONTROL Identification]**&#x200B;索引標籤中，選取&#x200B;**[!UICONTROL Using reconciliation criteria]**&#x200B;並定義&#x200B;**[!UICONTROL Dimension to update]** — 此例中的設定檔 — 與&#x200B;**[!UICONTROL Reconciliation]**&#x200B;活動中建立的連結之間的索引鍵。 在此範例中，使用&#x200B;**CRM ID**&#x200B;自訂欄位。

      ![](assets/import_template_example6.png)

   * 在&#x200B;**[!UICONTROL Fields to update]**&#x200B;索引標籤中，指出「設定檔」維度中的欄位，以使用檔案中對應欄的值更新。 如果檔案列的名稱與收件人維欄位的名稱相同或幾乎相同，則可以使用魔術棒按鈕自動匹配不同欄位。

      ![](assets/import_template_example6_2.png)

      >[!NOTE]
      >
      >如果您打算將直接郵件傳送至這些設定檔，請務必包含郵遞區號，因為此資訊對直接郵件提供者至關重要。 也請確定已勾選設定檔資訊中的&#x200B;**[!UICONTROL Address specified]**&#x200B;方塊。 若要從工作流程更新此選項，只需將元素新增至要更新的欄位，並將&#x200B;**1**&#x200B;指定為&#x200B;**[!UICONTROL Source]**，然後選取&#x200B;**[postalAddress/@addrDefined]**&#x200B;欄位為&#x200B;**[!UICONTROL Destination]**&#x200B;即可。 有關直接郵件和使用&#x200B;**[!UICONTROL Address specified]**&#x200B;選項的詳細資訊，請參閱[本文檔](../../channels/using/about-direct-mail.md#recommendations)。

1. 在&#x200B;**[!UICONTROL Segmentation]**&#x200B;活動的第三次轉變後，如果要跟蹤未插入資料庫中的資料，請添加&#x200B;**[!UICONTROL Extract file]**&#x200B;活動和&#x200B;**[!UICONTROL Transfer file]**&#x200B;活動。 設定這些活動以匯出您需要的欄，並在FTP或SFTP伺服器上傳輸檔案，您可在其中擷取檔案。
1. 新增&#x200B;**[!UICONTROL End]**&#x200B;活動並儲存工作流程範本。

範本現在可供使用，並可供所有新工作流程使用。 然後，需要全部來指定包含要在&#x200B;**[!UICONTROL Load file]**&#x200B;活動中匯入之資料的檔案。

![](assets/import_template_example9.png)
