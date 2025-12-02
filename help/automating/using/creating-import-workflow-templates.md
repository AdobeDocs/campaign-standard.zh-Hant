---
title: 建立工作流程範本以匯入資料
description: 瞭解如何建立工作流程範本以匯入資料。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
old-role: Data Architect
role: Developer
level: Experienced
exl-id: 5974a52c-8721-4575-b452-2982d6497235
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '1176'
ht-degree: 1%

---

# 建立工作流程範本以匯入資料 {#import-workflow-template}

如果您需要定期匯入具有相同結構的檔案，使用匯入範本是最佳做法。

此範例說明如何預先設定一個工作流程，此工作流程可重複用於匯入來自Adobe Campaign資料庫中CRM之設定檔的工作流程。

1. 從&#x200B;**[!UICONTROL Resources > Templates > Workflow templates]**&#x200B;建立新的工作流程範本。
1. 新增下列活動：

   * **[!UICONTROL Load file]**：定義包含要匯入之資料的檔案預期結構。

     >[!NOTE]
     >
     >您只能從單一檔案匯入資料。 如果工作流程有多個&#x200B;**[!UICONTROL Load file]**&#x200B;活動，則每次都會使用相同的檔案。

   * **[!UICONTROL Reconciliation]**：使用資料庫資料調解匯入的資料。
   * **[!UICONTROL Segmentation]**：建立篩選條件以依據是否可以調解記錄而以不同方式處理記錄。
   * **[!UICONTROL Deduplication]**：將資料插入資料庫之前，先從內送檔案刪除重複資料。
   * **[!UICONTROL Update data]**：使用匯入的設定檔更新資料庫。

   ![](assets/import_template_example0.png)

1. 設定&#x200B;**[!UICONTROL Load file]**&#x200B;活動：

   * 透過上傳範例檔案來定義預期的結構。 範例檔案應該只包含幾行，但應包含匯入所需的所有欄。 檢查並編輯檔案格式，確定每欄的型別已正確設定：文字、日期、整數等。 例如：

     ```
     lastname;firstname;birthdate;email;crmID
     Smith;Hayden;23/05/1989;hayden.smith@mailtest.com;123456
     ```

   * 在&#x200B;**[!UICONTROL File to load]**&#x200B;區段中，選取&#x200B;**[!UICONTROL Upload a new file from the local machine]**&#x200B;並保留欄位空白。 每次從這個範本建立新工作流程時，只要檔案符合定義的結構，您就可以在此處指定所要的檔案。

     您可以使用任何選項，但必須據以修改範本。 例如，如果您選取&#x200B;**[!UICONTROL Use the file specified in the inbound transition]**，您可以先新增&#x200B;**[!UICONTROL Transfer file]**&#x200B;活動，再擷取要從FTP/SFTP伺服器匯入的檔案。

     如果您希望使用者能夠下載包含匯入期間發生錯誤的檔案，請核取&#x200B;**[!UICONTROL Keep the rejects in a file]**&#x200B;選項並指定&#x200B;**[!UICONTROL File name]**。

     ![](assets/import_template_example1.png)

1. 設定&#x200B;**[!UICONTROL Reconciliation]**&#x200B;活動。 此活動在此內容的目的是識別傳入資料。

   * 在&#x200B;**[!UICONTROL Relations]**&#x200B;索引標籤中，選取&#x200B;**[!UICONTROL Create element]**&#x200B;並定義匯入資料和收件者目標維度之間的連結（請參閱[目標維度與資源](../../automating/using/query.md#targeting-dimensions-and-resources)）。 在此範例中，**CRM ID**&#x200B;自訂欄位是用來建立加入條件。 只要允許您識別唯一記錄，就使用所需的欄位或欄位組合。
   * 在&#x200B;**[!UICONTROL Identification]**&#x200B;索引標籤中，保留&#x200B;**[!UICONTROL Identify the document from the working data]**&#x200B;選項為未核取。

   ![](assets/import_template_example2.png)

1. 設定&#x200B;**[!UICONTROL Segmentation]**&#x200B;活動以在一個轉變中擷取已調解的收件者，以及在第二個轉變中無法調解但擁有足夠資料的收件者。

   然後可以使用包含已調解收件者的轉變來更新資料庫。 如果檔案中有最少的一組資訊，則可使用具有未知收件者的轉變在資料庫中建立新的收件者專案。

   無法調解且資料不足的收件者，會選取在補充外站轉變中，並可匯出至個別檔案或直接忽略。

   * 在活動的&#x200B;**[!UICONTROL General]**&#x200B;索引標籤中，將&#x200B;**[!UICONTROL Resource type]**&#x200B;設定為&#x200B;**[!UICONTROL Temporary resource]**&#x200B;並選取&#x200B;**[!UICONTROL Reconciliation]**&#x200B;作為目標集。
   * 在&#x200B;**[!UICONTROL Advanced options]**&#x200B;索引標籤中，核取&#x200B;**[!UICONTROL Generate complement]**&#x200B;選項以檢視是否有任何記錄無法插入資料庫中。 如有需要，您可以對補充資料套用進一步處理：檔案匯出、清單更新等。
   * 在&#x200B;**[!UICONTROL Segments]**&#x200B;索引標籤的第一個區段中，對入站母體新增篩選條件，以僅選取設定檔的CRM ID不等於0的記錄。 如此一來，會在該子集中選取檔案中與資料庫設定檔調解的資料。

     ![](assets/import_template_example3.png)

   * 新增第二個區段，選取有足夠資料可插入資料庫中的未調解記錄。 例如：電子郵件地址、名字和姓氏。 未調解的記錄其設定檔的CRM ID值等於0。

     ![](assets/import_template_example3_2.png)

   * 在前兩個子集中未選取的所有記錄都會在&#x200B;**[!UICONTROL Complement]**&#x200B;中選取。

1. 設定位於先前設定之&#x200B;**[!UICONTROL Update data]**&#x200B;活動的第一個出站轉變之後的&#x200B;**[!UICONTROL Segmentation]**&#x200B;活動。

   * 選取&#x200B;**[!UICONTROL Update]**&#x200B;作為&#x200B;**[!UICONTROL Operation type]**，因為入站轉變僅包含資料庫中已存在的收件者。
   * 在&#x200B;**[!UICONTROL Identification]**&#x200B;索引標籤中，選取&#x200B;**[!UICONTROL Using reconciliation criteria]**&#x200B;並定義&#x200B;**[!UICONTROL Dimension to update]** — 此案例中的設定檔 — 與&#x200B;**[!UICONTROL Reconciliation]**&#x200B;活動中建立的連結之間的索引鍵。 在此範例中，使用&#x200B;**CRM ID**&#x200B;自訂欄位。

     ![](assets/import_template_example6.png)

   * 在&#x200B;**[!UICONTROL Fields to update]**&#x200B;索引標籤中，指出設定檔維度中的欄位，以使用檔案中對應欄的值進行更新。 如果檔案欄的名稱相同或幾乎與收件者維度欄位的名稱相同，您可以使用魔術棒按鈕來自動比對不同的欄位。

     ![](assets/import_template_example6_2.png)

     >[!NOTE]
     >
     >如果您打算傳送直接郵件給這些設定檔，請務必包含郵寄地址，因為此資訊對於直接郵件提供者至關重要。 也請確定已核取設定檔資訊中的&#x200B;**[!UICONTROL Address specified]**&#x200B;方塊。 若要從工作流程更新此選項，只要在要更新的欄位中新增元素，並將&#x200B;**1**&#x200B;指定為&#x200B;**[!UICONTROL Source]**&#x200B;並選取`postalAddress/@addrDefined`欄位為&#x200B;**[!UICONTROL Destination]**&#x200B;即可。 如需直接郵件及使用&#x200B;**[!UICONTROL Address specified]**&#x200B;選項的詳細資訊，請參閱[此檔案](../../channels/using/about-direct-mail.md#recommendations)。

1. 設定位於包含未調解設定檔之轉變之後的&#x200B;**[!UICONTROL Deduplication]**&#x200B;活動：

   * 在&#x200B;**[!UICONTROL Properties]**&#x200B;索引標籤中，將&#x200B;**[!UICONTROL Resource type]**&#x200B;設定為從工作流程的&#x200B;**[!UICONTROL Reconciliation]**&#x200B;活動產生的暫存資源。

     ![](assets/import_template_example4.png)

   * 在此範例中，電子郵件欄位用於尋找唯一設定檔。 您可以使用任何您確定已填的欄位，以及唯一組合的一部分。
   * 選擇&#x200B;**[!UICONTROL Deduplication method]**。 在此情況下，應用程式會自動決定要保留哪些記錄以防重複。

   ![](assets/import_template_example7.png)

1. 設定位於先前設定的&#x200B;**[!UICONTROL Update data]**&#x200B;活動之後的&#x200B;**[!UICONTROL Deduplication]**&#x200B;活動。

   * 選取&#x200B;**[!UICONTROL Insert only]**&#x200B;作為&#x200B;**[!UICONTROL Operation type]**，因為入站轉變只包含資料庫中不存在的設定檔。
   * 在&#x200B;**[!UICONTROL Identification]**&#x200B;索引標籤中，選取&#x200B;**[!UICONTROL Using reconciliation criteria]**&#x200B;並定義&#x200B;**[!UICONTROL Dimension to update]** — 此案例中的設定檔 — 與&#x200B;**[!UICONTROL Reconciliation]**&#x200B;活動中建立的連結之間的索引鍵。 在此範例中，使用&#x200B;**CRM ID**&#x200B;自訂欄位。

     ![](assets/import_template_example6.png)

   * 在&#x200B;**[!UICONTROL Fields to update]**&#x200B;索引標籤中，指出設定檔維度中的欄位，以使用檔案中對應欄的值進行更新。 如果檔案欄的名稱相同或幾乎與收件者維度欄位的名稱相同，您可以使用魔術棒按鈕來自動比對不同的欄位。

     ![](assets/import_template_example6_2.png)

     >[!NOTE]
     >
     >如果您打算傳送直接郵件給這些設定檔，請務必包含郵寄地址，因為此資訊對於直接郵件提供者至關重要。 也請確定已核取設定檔資訊中的&#x200B;**[!UICONTROL Address specified]**&#x200B;方塊。 若要從工作流程更新此選項，只要在要更新的欄位中新增元素，並將&#x200B;**1**&#x200B;指定為&#x200B;**[!UICONTROL Source]**，並選取&#x200B;**[postalAddress/@addrDefined]**&#x200B;欄位為&#x200B;**[!UICONTROL Destination]**&#x200B;即可。 如需直接郵件及使用&#x200B;**[!UICONTROL Address specified]**&#x200B;選項的詳細資訊，請參閱[此檔案](../../channels/using/about-direct-mail.md#recommendations)。

1. 在&#x200B;**[!UICONTROL Segmentation]**&#x200B;活動的第三個轉變之後，如果您要追蹤未插入資料庫中的資料，請新增&#x200B;**[!UICONTROL Extract file]**&#x200B;活動和&#x200B;**[!UICONTROL Transfer file]**&#x200B;活動。 設定這些活動以匯出您需要的欄，並在FTP或SFTP伺服器上傳輸檔案，以便您擷取檔案。
1. 新增&#x200B;**[!UICONTROL End]**&#x200B;活動並儲存工作流程範本。

範本現在可用於每個新工作流程。 然後只需指定包含要在&#x200B;**[!UICONTROL Load file]**&#x200B;活動中匯入之資料的檔案。

![](assets/import_template_example9.png)
