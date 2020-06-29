---
title: 使用檔案中包含的資料豐富描述檔資料
description: 此範例說明如何以檔案中包含的購買資料豐富描述檔資料。
page-status-flag: never-activated
uuid: 8c1693ef-1312-422c-b05d-263553113f8f
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: f67c1caf-3284-4c34-a5b0-8654a95640ae
context-tags: enrichment,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7ffa48365875883a98904d6b344ac005afe26e18
workflow-type: tm+mt
source-wordcount: '528'
ht-degree: 0%

---


# 使用檔案中包含的資料豐富描述檔資料 {#enriching-profile-data-with-data-contained-in-a-file}

此範例說明如何使用檔案中包含的購買資料來豐富描述檔資料。我們認為購買資料儲存在協力廠商系統中。 每個描述檔都可儲存數個購買項目。 工作流程的最終目標是傳送電子郵件給已購買至少兩個項目的目標設定檔，以感謝他們的忠誠度。

工作流配置如下：

![](assets/enrichment_example_workflow.png)

* 一個 [查詢活動](../../automating/using/query.md) ，它定位將接收消息的配置檔案。
* 載 [入檔案](../../automating/using/load-file.md) ，以載入購買資料。 例如：

   ```
   tcode;tdate;customer;product;tamount
   aze123;21/05/2017;dannymars@example.com;TV;799
   aze124;28/05/2017;dannymars@example.com;Headphones;8
   aze125;31/07/2017;john.smith@example.com;Headphones;8
   aze126;14/12/2017;john.smith@example.com;Plastic Cover;4
   aze127;02/01/2018;dannymars@example.com;Case Cover;79
   aze128;04/03/2017;clara.smith@example.com;Phone;149
   ```

   在此示例檔案中，我們將使用電子郵件地址來協調資料與資料庫配置檔案。 您也可以如本檔案所述啟用唯 [一ID](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources)。

* Enrichment [](../../automating/using/enrichment.md) activity, that creates link been the transaction data loaded from the file and the profiles selected in the **[!UICONTROL Query]**. 該連結在活動的標 **[!UICONTROL Advanced relations]** 簽中定義。 連結以活動產生的轉場為 **[!UICONTROL Load file]** 基礎。 它使用配置檔案資源的「電子郵件」欄位和導入檔案的「客戶」列作為協調標準。

   ![](assets/enrichment_example_workflow2.png)

   建立連結後，會新增兩組 **[!UICONTROL Additional data]** 連結：

   * 兩個行的集合，這些行對應於每個配置檔案的最後兩個事務處理。 對於此系列，產品名稱、交易日期和產品價格會新增為其他資料。 對資料套用遞減排序。 若要建立系列，請從標籤 **[!UICONTROL Additional data]** 中：

      選擇先前在活動標籤中定 **[!UICONTROL Advanced relations]** 義的連結。

      ![](assets/enrichment_example_workflow3.png)

      檢 **[!UICONTROL Collection]** 查並指定要檢索的行數（本例中為2）。 在此畫面中，您可以自 **[!UICONTROL Alias]** 訂系列 **[!UICONTROL Label]** 和系列。 這些值將在參考此系列時，顯示在工作流程的下列活動中。

      ![](assets/enrichment_example_workflow4.png)

      若要 **[!UICONTROL Data]** 保留系列，請選取要用於最終傳送的欄。

      ![](assets/enrichment_example_workflow6.png)

      對事務日期應用降序排序，以確保檢索最新事務。

      ![](assets/enrichment_example_workflow7.png)

   * 匯總計算每個配置檔案的事務處理總數。 此匯總稍後將用於篩選至少記錄了兩個交易的描述檔。 要建立聚合，請從頁籤 **[!UICONTROL Additional data]** 中：

      選擇先前在活動標籤中定 **[!UICONTROL Advanced relations]** 義的連結。

      ![](assets/enrichment_example_workflow3.png)

      Select **[!UICONTROL Aggregate]**.

      ![](assets/enrichment_example_workflow8.png)

      要保 **[!UICONTROL Data]** 留，請定義「全 **部計數** 」匯總。 如果您需要，請指定自訂別名，以便在下列活動中更快找到別名。

      ![](assets/enrichment_example_workflow9.png)

* 只 [有一個區段](../../automating/using/segmentation.md) 的分段活動，可擷取至少記錄了兩個交易之初始目標的描述檔。 僅包含一個事務的配置檔案將被排除。 為此，區段的查詢是在先前定義的匯總上進行。

   ![](assets/enrichment_example_workflow5.png)

* 「電 [子郵件傳送](../../automating/using/email-delivery.md) 」活動，使用中定義的其他資料， **[!UICONTROL Enrichment]** 動態擷取描述檔最後兩次購買。 新增個人化欄位時，可在「其 **他資料(TargetData)」節點中找到其他資料** 。

   ![](assets/enrichment_example_workflow10.png)

**相關主題：**

* [利用外部資料豐富客戶個人檔案](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Managedatatofuelengagingexperiences)
