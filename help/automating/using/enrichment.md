---
title: 豐富型
seo-title: 豐富型
description: 豐富型
seo-description: 「Rich」活動是進階活動，可讓您定義工作流程中的其他資料。
page-status-flag: 從未啓動
uuid: 8c1693ef-1312-422c-b05 d-263555113f8 f
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: reference
topic-tags: 定位活動
discoiquuid: f67c1caf-3284-4c34-a5 b0-8654a95640 ae
context-tags: 擴充，主要
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Enrichment{#enrichment}

## Description {#description}

![](assets/enrichment.png)

**[!UICONTROL Enrichment]** 活動是進階活動，可讓您定義工作流程中的其他資料。

## Context of use {#context-of-use}

**[!UICONTROL Enrichment]** 活動通常用於定位活動或匯入檔案之後，在允許使用目標資料的活動之前。

This activity contains more advanced enrichment functions than the **[!UICONTROL Query]** activity. Some simple cases of enrichment can be directly performed in the [Query activity](../../automating/using/query.md#enriching-data).

With the **[!UICONTROL Enrichment]** activity, you can leverage the inbound transition and configure the activity to complete the output transition with additional data. 它可結合來自多個集合的資料，或建立暫存資源的連結。

## Configuration {#configuration}

To configure an **[!UICONTROL Enrichment]** activity:

1. Drag and drop an **[!UICONTROL Enrichment]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. If the activity has several inbound transitions, select the **[!UICONTROL Primary set]**. 在此活動中設定的其他資料將會新增至對外轉場中的這個主要集。

   如果主要集已包含其他資料，您可以選擇保留或移除這些資料。If you uncheck the **[!UICONTROL Keep all additional data from the main set]** option, only the additional data configured in the **[!UICONTROL Enrichment]** are kept in the outbound transition.

1. If there are several inbound transitions, define relations between the primary set and the other inbound data in the **[!UICONTROL Advanced Relations]** tab of the activity. You can add several relations using the **[!UICONTROL Add element]** button.

   定義新關係時，選取您要連結至主要集的傳入資料集。然後定義關係類型。有幾種關係類型可供使用，視傳入的資料和您的資料模型而定：

   * **[!UICONTROL 1 cardinality simple link]**：傳入資料的每個記錄會關聯到一個，而一個記錄只會從主要集合中記錄。主要集中的每個記錄都有連結資料中的一個相關記錄。
   * **[!UICONTROL N cardinality collection link]**：連結資料中的0、或以上(N)記錄可關聯至主要設定的記錄。
   * **[!UICONTROL 0 or 1 cardinality simple link]**：來自主要集的記錄可與連結資料(但不限於多個)關聯。
   Once the **[!UICONTROL Cardinality]** is defined, define a **[!UICONTROL Reconciliation criteria]**. The **[!UICONTROL Source expression]** of the reconciliation criteria can be a field from the target resource, an [expression](../../automating/using/advanced-expression-editing.md) or directly a value specified between quotes.

   Define a **[!UICONTROL Label]** and an **[!UICONTROL ID]** that will be easy to identify later in the workflow.

   >[!NOTE]
   >
   >You can only define relations between the primary set and the other inbound transitions connected to the **[!UICONTROL Enrichment]** activity. For simpler cases aiming at defining relations with database resources, use a [Reconciliation](../../automating/using/reconciliation.md) activity.

1. Define the additional data from the **[!UICONTROL Additional data]** tab of the activity. You can define additional data (simple fields, aggregates and collections) related to the targeting dimension of the primary set or based on the links created in the **[!UICONTROL Advanced relations]** tab of the **[!UICONTROL Enrichment]** activity.

   Consult the [Enriching data](../../automating/using/query.md#enriching-data) section.

1. 確認活動的設定並儲存工作流程。

The data is now available to use in the activities connected after the **[!UICONTROL Enrichment]**. For example, you can find it under the **[!UICONTROL Additional data (targetData)]** link of the personalization fields explorer in an email content.

## Example: Enriching profile data with data contained in a file {#example--enriching-profile-data-with-data-contained-in-a-file}

此範例說明如何使用檔案包含的購買資料充實個人檔案資料。我們認為購買資料儲存在第三方系統中。每個描述檔都可以儲存在檔案中的數個購買項目。工作流程的最終目標是傳送電子郵件給至少購買兩個項目的目標設定檔，以感謝他們的忠誠度。

工作流程的設定如下：

![](assets/enrichment_example_workflow.png)

* A **[!UICONTROL Query]** activity that targets the profiles who will receive the message.
* A **[!UICONTROL Load file]** activity that loads the purchase data. 例如：

   ```
   tcode;tdate;customer;product;tamount
   aze123;21/05/2017;dannymars@example.com;TV;799
   aze124;28/05/2017;dannymars@example.com;Headphones;8
   aze125;31/07/2017;john.smith@example.com;Headphones;8
   aze126;14/12/2017;john.smith@example.com;Plastic Cover;4
   aze127;02/01/2018;dannymars@example.com;Case Cover;79
   aze128;04/03/2017;clara.smith@example.com;Phone;149
   ```

   透過此範例檔案，我們將使用電子郵件地址將資料與資料庫設定檔協調。You can also enable unique IDs as described in [this document](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources).

* **[!UICONTROL Enrichment]** 在從檔案載入的交易資料與在中選取的描述檔之間建立連結的活動 **[!UICONTROL Query]**。The link is defined in the **[!UICONTROL Advanced relations]** tab of the activity. The link is based on the transition coming from the **[!UICONTROL Load file]** activity. 它會使用描述檔資源的「電子郵件」欄位和匯入檔案的「客戶」欄做為協調標準。

   ![](assets/enrichment_example_workflow2.png)

   Once the link is created, two sets of **[!UICONTROL Additional data]** are added:

   * 對應每個描述檔的兩個最後一個交易之兩行的集合。對於此系列，產品名稱、交易日期和產品價格會新增為其他資料。遞減排序會套用至資料。To create the collection, from the **[!UICONTROL Additional data]** tab:

      Select the link previously defined in the **[!UICONTROL Advanced relations]** tab of the activity.

      ![](assets/enrichment_example_workflow3.png)

      Check **[!UICONTROL Collection]** and specify the number of lines to retrieve (2 in this example). In this screen, you can customize the **[!UICONTROL Alias]** and the **[!UICONTROL Label]** of the collection. 參照此系列時，這些值會顯示在工作流程的下列活動中。

      ![](assets/enrichment_example_workflow4.png)

      As **[!UICONTROL Data]** to keep for the collection, select the columns that will be used in the final delivery.

      ![](assets/enrichment_example_workflow6.png)

      在交易日期上套用遞減排序，以確定擷取最新交易。

      ![](assets/enrichment_example_workflow7.png)

   * 匯總計算每個描述檔的交易總數。稍後將使用此匯總，篩選至少記錄兩筆交易的描述檔。To create the aggregate, from the **[!UICONTROL Additional data]** tab:

      Select the link previously defined in the **[!UICONTROL Advanced relations]** tab of the activity.

      ![](assets/enrichment_example_workflow3.png)

      Select **[!UICONTROL Aggregate]**.

      ![](assets/enrichment_example_workflow8.png)

      As **[!UICONTROL Data]** to keep, define a **Count All** aggregate. 如果您需要，請指定自訂別名，以在下列活動中快速找到它。

      ![](assets/enrichment_example_workflow9.png)

* **[!UICONTROL Segmentation]** 僅含一個區段的活動，擷取至少記錄兩筆交易的初始目標設定檔。只排除一筆交易的描述檔。若要這麼做，區段的查詢是在先前定義的匯總上進行。

   ![](assets/enrichment_example_workflow5.png)

* **[!UICONTROL Email delivery]** 使用中定義的其他資料來動態 **[!UICONTROL Enrichment]** 擷取由描述檔進行之兩次購買的活動。The additional data can be found in the **Additional data (TargetData)** node when adding a personalization field.

   ![](assets/enrichment_example_workflow10.png)

