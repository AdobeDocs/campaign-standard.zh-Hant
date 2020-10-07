---
title: 使用檔案包含的資料擴充設定檔資料
description: 此範例顯示如何以檔案中包含的購買資料擴充設定檔資料。
page-status-flag: never-activated
uuid: 8c1693ef-1312-422c-b05d-263553113f8f
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: f67c1caf-3284-4c34-a5b0-8654a95640ae
context-tags: enrichment,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 使用檔案包含的資料擴充設定檔資料 {#enriching-profile-data-with-data-contained-in-a-file}

此範例說明如何使用檔案中包含的購買資料來豐富描述檔資料。我們認為購買資料儲存在協力廠商系統中。 每個設定檔都可儲存數個購買項目。工作流程的最終目標是傳送電子郵件給已購買至少兩個項目的目標設定檔，以感謝他們的忠誠度。

工作流設定如下：

![](assets/enrichment_example_workflow.png)

* A [Query](../../automating/using/query.md) activity that targets the profiles who will receive the message.
* A [Load file](../../automating/using/load-file.md) activity that loads the purchase data. 例如：

   ```
   tcode;tdate;customer;product;tamount
   aze123;21/05/2017;dannymars@example.com;TV;799
   aze124;28/05/2017;dannymars@example.com;Headphones;8
   aze125;31/07/2017;john.smith@example.com;Headphones;8
   aze126;14/12/2017;john.smith@example.com;Plastic Cover;4
   aze127;02/01/2018;dannymars@example.com;Case Cover;79
   aze128;04/03/2017;clara.smith@example.com;Phone;149
   ```

   在此範例檔案中，我們將使用電子郵件地址來調解資料與資料庫設定檔。您也可以啟用唯一 ID，如[本文件](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources)所述。

* An [Enrichment](../../automating/using/enrichment.md) activity that creates a link between the transaction data loaded from the file and the profiles selected in the **[!UICONTROL Query]**. 該連結在活動的 **[!UICONTROL Advanced relations]** 索引標籤中定義。連結以來自 **[!UICONTROL Load file]** 活動的轉變為基礎。它使用設定檔資源的「電子郵件」欄位和匯入檔案的「客戶」列作為調解標準。

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

* A [Segmentation](../../automating/using/segmentation.md) activity with only one segment, that retrieves profiles of the initial target that have at least two transactions recorded. 將排除僅包含一個交易的設定檔。要執行此操作，區段的查詢會在先前定義的彙總上進行。

   ![](assets/enrichment_example_workflow5.png)

* An [Email delivery](../../automating/using/email-delivery.md) activity that uses the additional data defined in the **[!UICONTROL Enrichment]** to dynamically retrieve the two last purchases made by the profile. 新增個人化欄位時，可在&#x200B;**其他資料　(TargetData)**　節點中找到其他資料。

   ![](assets/enrichment_example_workflow10.png)

**相關主題：**

* [利用外部資料擴充客戶設定檔](https://helpx.adobe.com/tw/campaign/kb/simplify-campaign-management.html#Managedatatofuelengagingexperiences)
