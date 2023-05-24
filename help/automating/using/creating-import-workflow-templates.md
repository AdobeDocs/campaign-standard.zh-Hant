---
title: 建立工作流程範本以匯入資料
description: 瞭解如何建立工作流模板以導入資料。
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

如果需要定期導入具有相同結構的檔案，則使用導入模板是最佳做法。

此示例說明如何預先設定可重複使用的工作流，以導入來自Adobe Campaign資料庫中CRM的配置檔案。

1. 從建立新工作流模板 **[!UICONTROL Resources > Templates > Workflow templates]**。
1. 添加以下活動：

   * **[!UICONTROL Load file]**:定義包含要導入的資料的檔案的預期結構。

      >[!NOTE]
      >
      >只能從單個檔案導入資料。 如果工作流具有多個 **[!UICONTROL Load file]** 活動，每次都使用同一檔案。

   * **[!UICONTROL Reconciliation]**:調節導入的資料與資料庫資料。
   * **[!UICONTROL Segmentation]**:建立篩選器以根據記錄是否可對帳的不同方式處理記錄。
   * **[!UICONTROL Deduplication]**:在將資料插入資料庫之前，從傳入檔案中消除重複資料。
   * **[!UICONTROL Update data]**:使用導入的配置檔案更新資料庫。

   ![](assets/import_template_example0.png)

1. 配置 **[!UICONTROL Load file]** 活動：

   * 通過上載示例檔案來定義預期的結構。 示例檔案應僅包含幾行，但必須包含導入所需的所有列。 檢查並編輯檔案格式以確保正確設定每列的類型：文本、日期、整數等。 例如：

      ```
      lastname;firstname;birthdate;email;crmID
      Smith;Hayden;23/05/1989;hayden.smith@mailtest.com;123456
      ```

   * 在 **[!UICONTROL File to load]** 選擇 **[!UICONTROL Upload a new file from the local machine]** 將欄位留空。 每次根據此模板建立新工作流時，都可以在此處指定所需的檔案，只要該檔案與定義的結構對應。

      可以使用任何選項，但必須相應修改模板。 例如，如果您選擇 **[!UICONTROL Use the file specified in the inbound transition]**，您可以 **[!UICONTROL Transfer file]** 活動，以從FTP/SFTP伺服器中檢索要導入的檔案。

      如果希望用戶能夠下載包含導入過程中發生的錯誤的檔案，請檢查 **[!UICONTROL Keep the rejects in a file]** 選項並指定 **[!UICONTROL File name]**。

      ![](assets/import_template_example1.png)

1. 配置 **[!UICONTROL Reconciliation]** 的子菜單。 此上下文中此活動的目的是標識傳入資料。

   * 在 **[!UICONTROL Relations]** 頁籤 **[!UICONTROL Create element]** 並定義導入的資料與目標維的收件人之間的連結(請參閱 [目標維度和資源](../../automating/using/query.md#targeting-dimensions-and-resources))。 在此示例中， **CRM ID** custom欄位用於建立聯接條件。 使用需要的欄位或欄位組合，只要它允許標識唯一記錄。
   * 在 **[!UICONTROL Identification]** 頁籤 **[!UICONTROL Identify the document from the working data]** 複選框。

   ![](assets/import_template_example2.png)

1. 配置 **[!UICONTROL Segmentation]** 活動，用於檢索一個轉換中已協調的收件人和在第二個轉換中具有足夠資料的無法協調的收件人。

   然後，可以使用與已協調的收件人進行的轉換來更新資料庫。 如果檔案中有最小資訊集，則具有未知收件人的轉換可用於在資料庫中建立新收件人條目。

   無法協調且沒有足夠資料的收件人將在補充出站轉換中選擇，並可以在單獨的檔案中導出，或只是忽略。

   * 在 **[!UICONTROL General]** 頁籤，設定 **[!UICONTROL Resource type]** 至 **[!UICONTROL Temporary resource]** 選擇 **[!UICONTROL Reconciliation]** 作為目標集。
   * 在 **[!UICONTROL Advanced options]** 頁籤 **[!UICONTROL Generate complement]** 的子菜單。 如果需要，可對補充資料應用進一步處理：檔案導出、清單更新等。
   * 在 **[!UICONTROL Segments]** 頁籤，在入站人口中添加篩選條件，以僅選擇配置檔案的CRM ID不等於0的記錄。 這樣，在該子集中選擇與來自資料庫的概要檔案協調的檔案中的資料。

      ![](assets/import_template_example3.png)

   * 添加第二個段，該段選擇具有足夠資料要插入資料庫的未協調記錄。 例如：電子郵件地址、名字和姓氏。 未協調的記錄的配置檔案的CRM ID值等於0。

      ![](assets/import_template_example3_2.png)

   * 未在前兩個子集中選擇的所有記錄將在 **[!UICONTROL Complement]**。

1. 配置 **[!UICONTROL Update data]** 位於 **[!UICONTROL Segmentation]** 活動。

   * 選擇 **[!UICONTROL Update]** 如 **[!UICONTROL Operation type]** 因為入站轉換僅包含資料庫中已存在的收件人。
   * 在 **[!UICONTROL Identification]** 頁籤 **[!UICONTROL Using reconciliation criteria]** 並定義鍵 **[!UICONTROL Dimension to update]**  — 本例中的配置檔案 — 以及在 **[!UICONTROL Reconciliation]** 的子菜單。 在此示例中， **CRM ID** 自定義欄位。

      ![](assets/import_template_example6.png)

   * 在 **[!UICONTROL Fields to update]** 頁籤中，指示「配置檔案」維中的欄位，以使用檔案中相應列的值進行更新。 如果檔案列的名稱與收件人維欄位的名稱相同或幾乎相同，則可以使用魔棒按鈕自動匹配不同的欄位。

      ![](assets/import_template_example6_2.png)

      >[!NOTE]
      >
      >如果您計畫向這些配置檔案發送直郵，請確保包括郵政地址，因為此資訊對直郵提供商至關重要。 同時確保 **[!UICONTROL Address specified]** 的子菜單。 要從工作流更新此選項，只需將元素添加到要更新的欄位，然後指定 **1** 如 **[!UICONTROL Source]** 的 `postalAddress/@addrDefined` 欄位 **[!UICONTROL Destination]**。 有關直郵和使用的詳細資訊 **[!UICONTROL Address specified]** 選項，請參閱 [此文檔](../../channels/using/about-direct-mail.md#recommendations)。

1. 配置 **[!UICONTROL Deduplication]** 位於包含未協調配置檔案的轉換後的活動：

   * 在 **[!UICONTROL Properties]** 頁籤 **[!UICONTROL Resource type]** 到 **[!UICONTROL Reconciliation]** 的子目錄。

      ![](assets/import_template_example4.png)

   * 在此示例中，電子郵件欄位用於查找唯一的配置檔案。 您可以使用您確定已填充的任何欄位，並使用唯一組合的一部分。
   * 選擇 **[!UICONTROL Deduplication method]**。 在這種情況下，應用程式自動決定在記錄重複時保留哪些記錄。

   ![](assets/import_template_example7.png)

1. 配置 **[!UICONTROL Update data]** 位於 **[!UICONTROL Deduplication]** 活動。

   * 選擇 **[!UICONTROL Insert only]** 如 **[!UICONTROL Operation type]** 因為入站轉換只包含資料庫中不存在的配置檔案。
   * 在 **[!UICONTROL Identification]** 頁籤 **[!UICONTROL Using reconciliation criteria]** 並定義鍵 **[!UICONTROL Dimension to update]**  — 本例中的配置檔案 — 以及在 **[!UICONTROL Reconciliation]** 的子菜單。 在此示例中， **CRM ID** 自定義欄位。

      ![](assets/import_template_example6.png)

   * 在 **[!UICONTROL Fields to update]** 頁籤中，指示「配置檔案」維中的欄位，以使用檔案中相應列的值進行更新。 如果檔案列的名稱與收件人維欄位的名稱相同或幾乎相同，則可以使用魔棒按鈕自動匹配不同的欄位。

      ![](assets/import_template_example6_2.png)

      >[!NOTE]
      >
      >如果您計畫向這些配置檔案發送直郵，請確保包括郵政地址，因為此資訊對直郵提供商至關重要。 同時確保 **[!UICONTROL Address specified]** 的子菜單。 要從工作流更新此選項，只需將元素添加到要更新的欄位，然後指定 **1** 如 **[!UICONTROL Source]** 的 **[郵政地址/@addrDefined]** 欄位 **[!UICONTROL Destination]**。 有關直郵和使用的詳細資訊 **[!UICONTROL Address specified]** 選項，請參閱 [此文檔](../../channels/using/about-direct-mail.md#recommendations)。

1. 在 **[!UICONTROL Segmentation]** 活動，添加 **[!UICONTROL Extract file]** 活動和 **[!UICONTROL Transfer file]** 活動。 配置這些活動以導出所需的列，並在FTP或SFTP伺服器上傳輸檔案，在該伺服器上可以檢索該檔案。
1. 添加 **[!UICONTROL End]** 並保存工作流模板。

現在可以使用該模板，並且可用於每個新工作流。 然後，需要指定包含要在 **[!UICONTROL Load file]** 的子菜單。

![](assets/import_template_example9.png)
