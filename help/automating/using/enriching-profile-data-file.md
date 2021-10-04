---
title: 使用檔案包含的資料擴充設定檔資料
description: 此範例顯示如何以檔案中包含的購買資料擴充設定檔資料。
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: enrichment,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: d5c19884-5a3e-4676-899c-53074a3b0efc
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 75%

---

# 使用檔案包含的資料擴充設定檔資料 {#enriching-profile-data-with-data-contained-in-a-file}

此示例說明如何使用檔案中包含的購買資料來豐富配置檔案資料。我們在此處認為購買資料儲存在第三方系統中。 每個設定檔都可儲存數個購買項目。工作流程的最終目標是傳送電子郵件給已購買至少兩個項目的目標設定檔，以感謝他們的忠誠度。

工作流設定如下：

![](assets/enrichment_example_workflow.png)

* [查詢](../../automating/using/query.md)活動，目標為將接收訊息的設定檔。
* 載入購買資料的[載入檔案](../../automating/using/load-file.md)活動。 例如：

   ```
   tcode;tdate;customer;product;tamount
   aze123;21/05/2017;dannymars@example.com;TV;799
   aze124;28/05/2017;dannymars@example.com;Headphones;8
   aze125;31/07/2017;john.smith@example.com;Headphones;8
   aze126;14/12/2017;john.smith@example.com;Plastic Cover;4
   aze127;02/01/2018;dannymars@example.com;Case Cover;79
   aze128;04/03/2017;clara.smith@example.com;Phone;149
   ```

   使用此範例檔案，使用電子郵件地址來調解資料與資料庫設定檔。 您也可以啟用唯一 ID，如[本文件](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources)所述。

* [擴充](../../automating/using/enrichment.md)活動，在從檔案載入的交易資料與在&#x200B;**[!UICONTROL Query]**&#x200B;中選取的設定檔之間建立連結。 該連結在活動的 **[!UICONTROL Advanced relations]** 索引標籤中定義。連結以來自 **[!UICONTROL Load file]** 活動的轉變為基礎。它使用設定檔資源的「電子郵件」欄位和匯入檔案的「客戶」列作為調解標準。

   ![](assets/enrichment_example_workflow2.png)

   建立連結後，會新增兩組 **[!UICONTROL Additional data]**：

   * 兩個行的集合，這些行與每個設定檔的最後兩個交易相對應。對於此系列，會將產品名稱、交易日期和產品價格新增為其他資料。對資料套用遞減排序。若要建立系列，請從 **[!UICONTROL Additional data]** 索引標籤：

      選與之前在活動之 **[!UICONTROL Advanced relations]** 索引標籤中定義的連結。

      ![](assets/enrichment_example_workflow3.png)

      檢查 **[!UICONTROL Collection]** 並指定要擷取的行數（在本範例中為 2）。在此畫面中，您可以自訂 **[!UICONTROL Alias]** 及系列的 **[!UICONTROL Label]**。在參考此系列時，可在工作流程的下列活動中看到這些值。

      ![](assets/enrichment_example_workflow4.png)

      若要 **[!UICONTROL Data]** 保留系列，請選取要用於最終傳送的欄。

      ![](assets/enrichment_example_workflow6.png)

      對交易日期應用降序排序，以確保擷取最新交易。

      ![](assets/enrichment_example_workflow7.png)

   * 彙總計算每個設定檔的交易總數。此彙總稍後將用於篩選至少記錄兩個交易的設定檔。若要建立彙總，請從 **[!UICONTROL Additional data]** 索引標籤：

      選與之前在活動之 **[!UICONTROL Advanced relations]** 索引標籤中定義的連結。

      ![](assets/enrichment_example_workflow3.png)

      選取 **[!UICONTROL Aggregate]**。

      ![](assets/enrichment_example_workflow8.png)

      若要保留 **[!UICONTROL Data]**，定義&#x200B;**全部計數**&#x200B;彙總。如有需要，請指定自訂別名，以便在下列活動中更快速地找到別名。

      ![](assets/enrichment_example_workflow9.png)

* [區段](../../automating/using/segmentation.md)活動，只包含一個區段，可擷取至少已記錄兩個交易之初始目標的設定檔。 將排除僅包含一個交易的設定檔。要執行此操作，區段的查詢會在先前定義的彙總上進行。

   ![](assets/enrichment_example_workflow5.png)

* [電子郵件傳送](../../automating/using/email-delivery.md)活動，使用&#x200B;**[!UICONTROL Enrichment]**&#x200B;中定義的其他資料，以動態擷取設定檔進行的最後兩次購買。 新增個人化欄位時，可在&#x200B;**其他資料　(TargetData)**　節點中找到其他資料。

   ![](assets/enrichment_example_workflow10.png)

**相關主題：**

* [利用外部資料擴充客戶設定檔](https://helpx.adobe.com/tw/campaign/kb/simplify-campaign-management.html#Managedatatofuelengagingexperiences)
