---
solution: Campaign Standard
product: campaign
title: 建立工作流程範本以匯入資料
description: 瞭解如何建立工作流程範本以匯入資料。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '1172'
ht-degree: 1%

---


# 建立工作流程範本以匯入資料 {#import-workflow-template}

如果您需要定期匯入具有相同結構的檔案，請使用匯入範本是最佳做法。

此範例說明如何預先設定可重複用於匯入來自Adobe Campaign資料庫中CRM的設定檔的工作流程。

1. 從&#x200B;**[!UICONTROL Resources > Templates > Workflow templates]**&#x200B;建立新的工作流程範本。
1. 新增下列活動：

   * **[!UICONTROL Load file]**:定義包含要導入資料的檔案的預期結構。

      >[!NOTE]
      >
      >您只能從單一檔案匯入資料。 如果工作流程有多個&#x200B;**[!UICONTROL Load file]**&#x200B;活動，則每次都會使用相同的檔案。

   * **[!UICONTROL Reconciliation]**:協調導入的資料與資料庫資料。
   * **[!UICONTROL Segmentation]**:根據記錄是否可以調節，建立篩選器以不同方式處理記錄。
   * **[!UICONTROL Deduplication]**:在將傳入檔案插入資料庫之前，先從該檔案中消除重複資料。
   * **[!UICONTROL Update data]**:使用導入的配置檔案更新資料庫。

   ![](assets/import_template_example0.png)

1. 配置&#x200B;**[!UICONTROL Load file]**&#x200B;活動：

   * 上傳範例檔案以定義預期的結構。 範例檔案應僅包含幾行，但是導入時需要的所有列。 檢查並編輯檔案格式，以確保每列的類型設定正確：文字、日期、整數等。 例如：

      ```
      lastname;firstname;birthdate;email;crmID
      Smith;Hayden;23/05/1989;hayden.smith@mailtest.com;123456
      ```

   * 在&#x200B;**[!UICONTROL File to load]**&#x200B;區段中，選擇&#x200B;**[!UICONTROL Upload a new file from the local machine]**&#x200B;並將欄位留空。 每次從此模板建立新工作流時，您都可以在此處指定所需的檔案，只要該檔案與定義的結構相對應。

      您可以使用任何選項，但必須相應修改模板。 例如，如果您選擇&#x200B;**[!UICONTROL Use the file specified in the inbound transition]**，則可以先添加&#x200B;**[!UICONTROL Transfer file]**&#x200B;活動，然後再檢索要從FTP/SFTP伺服器導入的檔案。

      如果您希望使用者能夠下載包含匯入期間發生錯誤的檔案，請勾選&#x200B;**[!UICONTROL Keep the rejects in a file]**&#x200B;選項並指定&#x200B;**[!UICONTROL File name]**。

      ![](assets/import_template_example1.png)

1. 設定&#x200B;**[!UICONTROL Reconciliation]**&#x200B;活動。 此活動的目的是識別傳入的資料。

   * 在&#x200B;**[!UICONTROL Relations]**&#x200B;標籤中，選擇&#x200B;**[!UICONTROL Create element]**&#x200B;並定義匯入資料與收件者定位維度之間的連結（請參閱[定位維度與資源](../../automating/using/query.md#targeting-dimensions-and-resources)）。 在此範例中，**CRM ID**&#x200B;自訂欄位用於建立連結條件。 只要您需要欄位或欄位組合，就能識別唯一記錄。
   * 在&#x200B;**[!UICONTROL Identification]**&#x200B;標籤中，保留&#x200B;**[!UICONTROL Identify the document from the working data]**&#x200B;選項未選中。

   ![](assets/import_template_example2.png)

1. 設定&#x200B;**[!UICONTROL Segmentation]**&#x200B;活動，以擷取一個轉場中已協調的收件者，以及在第二個轉場中無法協調但擁有足夠資料的收件者。

   然後，可以使用與已調節的收件人之間的轉換來更新資料庫。 然後，如果檔案中有一組最小資訊，則與未知收件人的轉換可用於在資料庫中建立新收件人條目。

   無法協調且沒有足夠資料的收件者會在補充的對外轉場中選取，並可匯出成個別檔案或略過。

   * 在活動的&#x200B;**[!UICONTROL General]**&#x200B;標籤中，將&#x200B;**[!UICONTROL Resource type]**&#x200B;設為&#x200B;**[!UICONTROL Temporary resource]**，並選擇&#x200B;**[!UICONTROL Reconciliation]**&#x200B;作為目標集。
   * 在&#x200B;**[!UICONTROL Advanced options]**&#x200B;頁籤中，選中&#x200B;**[!UICONTROL Generate complement]**&#x200B;選項可查看是否無法在資料庫中插入任何記錄。 如果需要，您可以對補充資料套用進一步的處理：檔案匯出、清單更新等。
   * 在&#x200B;**[!UICONTROL Segments]**&#x200B;標籤的第一個區段中，在傳入人口中新增篩選條件，以僅選擇描述檔的CRM ID不等於0的記錄。 這樣，在該子集中選擇與資料庫配置檔案協調的檔案資料。

      ![](assets/import_template_example3.png)

   * 添加第二個段，該段選擇具有足夠資料要插入到資料庫中的未協調記錄。 例如：電子郵件地址、名字和姓氏。 未協調的記錄的配置檔案的CRM ID值等於0。

      ![](assets/import_template_example3_2.png)

   * 在&#x200B;**[!UICONTROL Complement]**&#x200B;中選擇前兩個子集中未選擇的所有記錄。

1. 配置位於先前配置的&#x200B;**[!UICONTROL Segmentation]**&#x200B;活動首次出站轉移後的&#x200B;**[!UICONTROL Update data]**&#x200B;活動。

   * 選擇&#x200B;**[!UICONTROL Update]**&#x200B;作為&#x200B;**[!UICONTROL Operation type]** ，因為入站過渡僅包含資料庫中已存在的收件人。
   * 在&#x200B;**[!UICONTROL Identification]**&#x200B;標籤中，選擇&#x200B;**[!UICONTROL Using reconciliation criteria]**&#x200B;並定義&#x200B;**[!UICONTROL Dimension to update]** —— 在本例中為配置檔案——和在&#x200B;**[!UICONTROL Reconciliation]**&#x200B;活動中建立的連結之間的鍵。 在此範例中，會使用&#x200B;**CRM ID**&#x200B;自訂欄位。

      ![](assets/import_template_example6.png)

   * 在&#x200B;**[!UICONTROL Fields to update]**&#x200B;頁籤中，指定「概要檔案」維中的欄位，以使用檔案中相應列的值進行更新。 如果檔案列的名稱與收件人維欄位的名稱相同或幾乎相同，則可以使用魔術棒按鈕自動匹配不同的欄位。

      ![](assets/import_template_example6_2.png)

      >[!NOTE]
      >
      >如果您打算將直效郵件傳送給這些個人檔案，請務必包含郵遞區號，因為這項資訊對於直效郵件提供者而言十分重要。 另請確定已勾選設定檔資訊中的&#x200B;**[!UICONTROL Address specified]**&#x200B;方塊。 若要從工作流程更新此選項，只需將元素新增至要更新的欄位，然後將&#x200B;**1**&#x200B;指定為&#x200B;**[!UICONTROL Source]**，並選取`postalAddress/@addrDefined`欄位為&#x200B;**[!UICONTROL Destination]**。 有關直效郵件和使用&#x200B;**[!UICONTROL Address specified]**&#x200B;選項的更多資訊，請參見[本文檔](../../channels/using/about-direct-mail.md#recommendations)。

1. 配置&#x200B;**[!UICONTROL Deduplication]**&#x200B;活動，該活動位於包含未協調的配置檔案的轉換之後：

   * 在&#x200B;**[!UICONTROL Properties]**&#x200B;頁籤中，將&#x200B;**[!UICONTROL Resource type]**&#x200B;設定為從工作流的&#x200B;**[!UICONTROL Reconciliation]**&#x200B;活動生成的臨時資源。

      ![](assets/import_template_example4.png)

   * 在此範例中，電子郵件欄位可用來尋找獨特的描述檔。 您可以使用任何您確定已填入的欄位，以及唯一組合的一部分。
   * 選擇&#x200B;**[!UICONTROL Deduplication method]**。 在這種情況下，應用程式會自動決定在出現重複記錄時保存哪些記錄。

   ![](assets/import_template_example7.png)

1. 配置位於先前配置的&#x200B;**[!UICONTROL Deduplication]**&#x200B;活動之後的&#x200B;**[!UICONTROL Update data]**&#x200B;活動。

   * 選擇&#x200B;**[!UICONTROL Insert only]**&#x200B;作為&#x200B;**[!UICONTROL Operation type]** ，因為入站過渡只包含資料庫中不存在的配置檔案。
   * 在&#x200B;**[!UICONTROL Identification]**&#x200B;標籤中，選擇&#x200B;**[!UICONTROL Using reconciliation criteria]**&#x200B;並定義&#x200B;**[!UICONTROL Dimension to update]** —— 在本例中為配置檔案——和在&#x200B;**[!UICONTROL Reconciliation]**&#x200B;活動中建立的連結之間的鍵。 在此範例中，會使用&#x200B;**CRM ID**&#x200B;自訂欄位。

      ![](assets/import_template_example6.png)

   * 在&#x200B;**[!UICONTROL Fields to update]**&#x200B;頁籤中，指定「概要檔案」維中的欄位，以使用檔案中相應列的值進行更新。 如果檔案列的名稱與收件人維欄位的名稱相同或幾乎相同，則可以使用魔術棒按鈕自動匹配不同的欄位。

      ![](assets/import_template_example6_2.png)

      >[!NOTE]
      >
      >如果您打算將直效郵件傳送給這些個人檔案，請務必包含郵遞區號，因為這項資訊對於直效郵件提供者而言十分重要。 另請確定已勾選設定檔資訊中的&#x200B;**[!UICONTROL Address specified]**&#x200B;方塊。 若要從工作流程更新此選項，只需將元素新增至要更新的欄位，並將&#x200B;**1**&#x200B;指定為&#x200B;**[!UICONTROL Source]**，然後選取&#x200B;**[postalAddress/@addrDefined]**&#x200B;欄位為&#x200B;**[!UICONTROL Destination]**。 有關直效郵件和使用&#x200B;**[!UICONTROL Address specified]**&#x200B;選項的更多資訊，請參見[本文檔](../../channels/using/about-direct-mail.md#recommendations)。

1. 在&#x200B;**[!UICONTROL Segmentation]**&#x200B;活動進行第三次轉換後，如果要跟蹤未插入資料庫的資料，請添加&#x200B;**[!UICONTROL Extract file]**&#x200B;活動和&#x200B;**[!UICONTROL Transfer file]**&#x200B;活動。 設定這些活動，以匯出您需要的欄，並在FTP或SFTP伺服器上傳輸檔案，您可在其中擷取該欄。
1. 新增&#x200B;**[!UICONTROL End]**&#x200B;活動並儲存工作流程範本。

範本現在可以使用，而且適用於每個新的工作流程。 然後，需要全部指定包含要在&#x200B;**[!UICONTROL Load file]**&#x200B;活動中導入的資料的檔案。

![](assets/import_template_example9.png)
