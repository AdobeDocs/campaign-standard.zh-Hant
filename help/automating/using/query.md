---
title: Query
seo-title: Query
description: Query
seo-description: 「查詢」活動可讓您從Adobe Campaign資料庫篩選並提取元素族群。
page-status-flag: 從未啓動
uuid: b3c629fa-370e-481c-b347-fcf9 f5 a5 e847
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: reference
topic-tags: 定位活動
discoiquuid: 8d46ce28-0101-4f13-865a-2208ed6d6139
context-tags: query，main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d50d486ed77cb7989df47133bb49fde3227ae3a5

---


# Query{#query}

## Description {#description}

![](assets/query.png)

**[!UICONTROL Query]** 此活動可讓您從Adobe Campaign資料庫篩選並提取元素族群。You can define **[!UICONTROL Additional data]** for the targeted population via a dedicated tab. 此資料儲存在其他欄中，只能用於進行中的工作流程。

活動使用查詢編輯器工具。This tool is detailed in a [dedicated section](../../automating/using/editing-queries.md#about-query-editor).

## Context of use {#context-of-use}

**[!UICONTROL Query]** 活動可用於各種類型的使用：

* 劃分個人來定義訊息、觀眾等目標。
* 豐富整個Adobe Campaign資料庫表格的資料。
* 匯出資料。

## Configuration {#configuration}

1. Drag and drop a **[!UICONTROL Query]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear. 依預設，活動已預先設定為搜尋設定檔。
1. If you would like to run a query on a resource other than the profile resource, go to the activity's **[!UICONTROL Properties]** tab and select a **[!UICONTROL Resource]** and a **[!UICONTROL Targeting dimension]**.

   The **[!UICONTROL Resource]** allows you to refine the filters displayed in the palette whereas the **[!UICONTROL Targeting dimension]**, contextual with regard to the resource selected, corresponds to the type of population that you would like to obtain (identified profiles, deliveries, data linked to the selected resource, etc.).

   For more on this, refer to [Targeting dimensions and resources](../../automating/using/query.md#targeting-dimensions-and-resources)

1. **[!UICONTROL Target]** 在標籤中，透過定義和結合規則來執行查詢。
1. You can define **[!UICONTROL Additional data]** for the targeted population via a dedicated tab. 此資料儲存在其他欄中，只能用於進行中的工作流程。尤其是，您可以從連結至查詢目標維度的Adobe Campaign資料庫表格中新增資料。Consult the [Enriching data](../../automating/using/query.md#enriching-data) section.

   >[!NOTE]
   >
   >By default, the **[!UICONTROL Remove duplicate rows (DISTINCT)]** option is checked in the **[!UICONTROL Advanced options]** of the **[!UICONTROL Additional data]** tab of the query. If the **[!UICONTROL Query]** activity contains many (from 100) additional data defined, it is recommended to uncheck this option, for performance reasons. 請小心，取消勾選此選項可能會造成重復，視查詢的資料而定。

1. **[!UICONTROL Transition]** 在標籤中， **[!UICONTROL Enable an outbound transition]** 此選項可讓您在查詢活動後新增傳出轉場，即使它擷取無資料亦然。

   The outbound transition's segment code can be personalized using a standard expression and events variables (see [Customizing activities with events variables](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables)).

1. 確認活動的設定並儲存工作流程。

## Targeting dimensions and resources {#targeting-dimensions-and-resources}

定位維度和資源可讓您定義要根據哪個元素來決定傳送目標。

定位維度是在定位對應中定義。For more on this, refer to [this section](../../administration/using/target-mappings-in-campaign.md).

### Defining the targeting dimension and resource of a query {#defining-the-targeting-dimension-and-resource-of-a-query}

Targeting dimension and resources are defined when creating a workflow, in the **[!UICONTROL Properties]** tab of a Query activity.

>[!NOTE]
>
>The targeting dimension can also be defined when creating an audience (see [this section](../../audiences/using/creating-audiences.md)).

![](assets/targeting_dimension1.png)

鎖定維度和資源。因此，可用的定位維度取決於所選資源。

For example, for the Resource **[!UICONTROL Profiles (profile)]**, the following targeting dimensions will be available:

![](assets/targeting_dimension2.png)

While for **[!UICONTROL Deliveries (delivery)]**, the list will contain the following targeting dimensions:

![](assets/targeting_dimension3.png)

指定定位維度和資源後，查詢中就會提供不同篩選。

**[!UICONTROL Profiles (profile)]** 資源可用篩選的範例：

![](assets/targeting_dimension4.png)

**[!UICONTROL Deliveries (delivery)]** 資源可用篩選的範例：

![](assets/targeting_dimension5.png)

### Using resources different from targeting dimensions {#using-resources-different-from-targeting-dimensions}

依預設，定位維度和資源會設定為定位設定檔。

不過，如果您想要在遠處表格中查閱特定記錄，則可從定位維度使用不同的資源。

**範例1：識別透過標籤傳送的個人檔案」，歡迎返回！**」。

* 在這種情況下，我們想要定位個人檔案。We will set the targeting dimension to **[!UICONTROL Profiles (profile)]**.
* 我們想要根據傳送標籤篩選選取的設定檔。We will therefore set the resource to **[!UICONTROL Delivery logs]**. 如此，我們就可直接在傳送記錄表格中篩選，提供更佳的效能。

![](assets/targeting_dimension6.png)

![](assets/targeting_dimension7.png)

**範例2：識別未透過「歡迎傳回」標籤的個人檔案。」**

在先前的範例中，我們使用了不同於定位維度的資源。This operation is only possible if you want to find a record that **is present** in the distant table (delivery logs in our example).

If we want to find a record that **is not present** in the distant table (for example, profiles who were not targeted by a specific delivery), you must use the same resource and targeting dimension, as the record will not be present in the distant table (delivery logs).

* 在這種情況下，我們想要定位個人檔案。We will set the targeting dimension to **[!UICONTROL Profiles (profile)]**.
* 我們想要根據傳送標籤篩選選取的設定檔。當我們尋找不存在於傳送記錄表格中的記錄時，無法直接在傳送記錄檔上篩選。We will therefore set the resource to **[!UICONTROL Profile (profile)]** and build our query on the profiles table.

![](assets/targeting_dimension8.png)

![](assets/targeting_dimension9.png)

## Enriching data {#enriching-data}

**[!UICONTROL Additional data]** 此標籤的標籤 **[!UICONTROL Query]****[!UICONTROL Incremental query]****[!UICONTROL Enrichment]** 可讓您豐富資料目標，並將此資料傳輸至下列工作流程活動，以便在其中使用。您尤其可以新增：

* 簡單資料
* 整合
* 系列

For aggregates and collections, an **[!UICONTROL Alias]** is automatically defined to give a technical ID to a complex expression. 此別名必須是唯一的，因此可在稍後輕鬆找到組合和系列。您可以修改它，為它提供容易辨識的名稱。

>[!NOTE]
>
>別名必須遵守下列語法規則：僅授權英字元和「_」字元。別名區分大小寫。別名必須以「@」字元開頭。緊接在「@」後面的字元不能是數值。例如：@ Myalias_1和@_1別名正確無誤；而@ myalias#和@1別名不正確。

新增任何其他資料後，您可以根據定義的其他資料建立條件，對最初定位的資料套用其他篩選層級。

>[!NOTE]
>
>By default, the **[!UICONTROL Remove duplicate rows (DISTINCT)]** option is checked in the **[!UICONTROL Advanced options]** of the **[!UICONTROL Additional data]** tab of the query. If the **[!UICONTROL Query]** activity contains many (from 100) additional data defined, it is recommended to uncheck this option, for performance reasons. 請小心，取消勾選此選項可能會造成重復，視查詢的資料而定。

### Adding a simple field {#adding-a-simple-field}

將簡單欄位新增為其他資料，該欄位就會直接出現在活動的對外轉場中。這可讓使用者檢查例如，查詢中的資料是想要的資料。

1. From the **[!UICONTROL Additional data]** tab, add a new element.
1. In the window that opens, in the **[!UICONTROL Expression]** field, select one of the fields available directly in the targeting dimension or in one of the linked dimensions. 您可以從維度欄位編輯運算式並使用函數或簡單計算(統合除外)。

   **[!UICONTROL Alias]** 如果您編輯不是簡單XPATH路徑的運算式(例如：「年(&lt;@ fordDate&gt;)」)。如果您喜歡，可以修改它。If you only select one field (for example: "@age"), you do not need to define an **[!UICONTROL Alias]**.

1. Select **[!UICONTROL Add]** to confirm adding the field to the additional data. 執行查詢時，會在活動的對外轉場中顯示對應於所新增欄位的其他欄。

![](assets/enrichment_add_simple_field.png)

### Adding an aggregate {#adding-an-aggregate}

匯總可讓您從定位維度的欄位或連結到定位維度的維度欄位中計算值。例如：設定檔所購買的平均金額。

1. From the **[!UICONTROL Additional data]** tab, add a new element.
1. In the window that opens, select the collection that you want to use to create your aggregate in the **[!UICONTROL Expression]** field.

   An **[!UICONTROL Alias]** is created automatically. If you like, you can modify it by going back to the query's **[!UICONTROL Additional data]** tab.

   匯總定義視窗隨即開啓。

1. Define an aggregate from the **[!UICONTROL Data]** tab. Depending on the type of aggregate selected, only the elements whose data is compatible are available in the **[!UICONTROL Expression]** field. 例如，只能使用數值資料來計算總和。

   ![](assets/enrichment_add_aggregate.png)

   您可以為選取的系列欄位新增幾個匯總。請務必定義明確標籤，以便區分活動對外資料詳細資料的不同欄。

   您也可以變更每個匯總自動定義的別名。

   ![](assets/enrichment_add_aggregate2.png)

1. 如有需要，您可以新增篩選器來限制考量的資料。

   Refer to the [Filtering added data](../../automating/using/query.md#filtering-added-data) section.

1. Select **[!UICONTROL Confirm]** to add aggregates.

>[!NOTE]
>
>You cannot create an expression containing an aggregate directly from the **[!UICONTROL Expression]** field of the **[!UICONTROL New additional data]** window.

### Adding a collection {#adding-a-collection}

1. From the **[!UICONTROL Additional data]** tab, add a new element.
1. In the window that opens, select the collection that you want to add in the **[!UICONTROL Expression]** field. An **[!UICONTROL Alias]** is created automatically. If you like, you can modify it by going back to the query's **[!UICONTROL Additional data]** tab.
1. Select **[!UICONTROL Add]**. 新視窗隨即開啓，讓您可以調整想要顯示的系列資料。
1. In the **[!UICONTROL Parameters]** tab, select **[!UICONTROL Collection]** and define the number of lines of the collection that you want to add. For example, if you want to get the three most recent purchases carried out by each profile, enter "3" in the **[!UICONTROL Number of lines to return]** field.

   >[!NOTE]
   >
   >您必須輸入大於或等於的數字。

1. From the **[!UICONTROL Data]** tab, define the fields of the collection that you want to display for each line.

   ![](assets/enrichment_add_collection.png)

1. 如果您喜歡，可以新增篩選器來限制納入的系列行。

   Refer to the [Filtering added data](../../automating/using/query.md#filtering-added-data) section.

1. 您可以視需要定義資料排序。

   For example, if you have selected 3 lines to return in the **[!UICONTROL Parameters]** tab, and you want to determine the three most recent purchases, you can define a descending sort on the "date" field of the collection that corresponds to the transactions.

1. Refer to the [Sorting additional data](../../automating/using/query.md#sorting-additional-data) section.
1. Select **[!UICONTROL Confirm]** to add the collection.

### Filtering added data {#filtering-added-data}

新增匯總或系列時，您可以指定另一個篩選，以限制想要顯示的資料。

For example, if you want to only process the collection lines of transactions with amounts of 50 dollars and above, you can add a condition on the field corresponding to the transaction amount from the **[!UICONTROL Filter]** tab.

![](assets/enrichment_filter_data.png)

### Sorting additional data {#sorting-additional-data}

當您將匯總或系列新增至查詢資料時，您可以根據欄位值或定義的運算式來指定是否要套用排序(無論是遞增還是遞減)。

For example, if you want to save only the transaction that was carried out most recently by a profile, enter "1" in the **[!UICONTROL Number of lines to return]** field of the **[!UICONTROL Parameters]** tab, and apply a descending sort on the field corresponding to the transaction date via the **[!UICONTROL Sort]** tab.

![](assets/enrichment_sort_data.png)

### Filtering the targeted data according to additional data {#filtering-the-targeted-data-according-to-additional-data}

Once you have added additional data, a new **[!UICONTROL Output filtering]** tab appears in the **[!UICONTROL Query]**. This tab allows you to apply an additional filter on the data initially targeted in the **[!UICONTROL Target]** tab, by taking into account the added data.

For example, if you have targeted all of the profiles that carried out at least one transaction and an aggregate calculating the average transaction amount carried out for each profile was added to the **[!UICONTROL Additional data]**, you can refine the population initially calculated using this average.

To do this, in the **[!UICONTROL Output filtering]** tab, simply add a condition on this additional data.

![](assets/enrichment_output_filtering2.png)

![](assets/enrichment_output_filtering.png)

### Example: personalizing an email with additional data {#example--personalizing-an-email-with-additional-data}

下列範例說明新增不同類型的其他資料至查詢，以及其作為電子郵件中的個人化欄位。

For this example, [custom resources](../../developing/using/data-model-concepts.md) are used:

* **已擴充描述檔** 資源，以新增允許儲存每個描述檔忠誠度點的欄位。
* **建立交易** 資源並識別資料庫中描述檔進行的所有購買。每次交易都會儲存日期、價格和購買的產品。
* A **products** resource was created and references the products available for purchase.

其目標是傳送電子郵件至至少一筆交易已儲存的描述檔。透過這封電子郵件，客戶將會收到最後交易的提醒，以及他們所有交易的總覽：購買的產品數、總花費次數，提醒他們他們已獲得的忠誠度總點數。

工作流程的呈現方式如下：

![](assets/enrichment_example1.png)

1. Add a **[!UICONTROL Query]** activity, which allows you to target the profiles that have carried out at least one transaction.

   ![](assets/enrichment_example2.png)

   From the query's **[!UICONTROL Additional data]** tab, define the different data to be displayed in the final email:

   * The simple field of the **profile** dimension corresponding to the loyalty points. Refer to the [Adding a simple field](../../automating/using/query.md#adding-a-simple-field) section.
   * 根據交易收集進行兩個匯總：購買的產品數和花費的總金額。You can add them from the **[!UICONTROL Data]** tab of the aggregate configuration window, using the **Count** and **Sum** aggregates. Refer to the [Adding an aggregate](../../automating/using/query.md#adding-an-aggregate) section.
   * 一個系列，傳回上次交易的金額、日期和產品。

      To do this, you have to add the different fields that you want to display from the **[!UICONTROL Data]** tab of the collection configuration window.

      To return only the most recent transaction, you have to enter "1" for the **[!UICONTROL Number of lines to return]** and apply a descending sort on the **Date** field of the collection from the **[!UICONTROL Sort]** tab.

      Refer to the [Adding a collection](../../automating/using/query.md#adding-a-collection) and [Sorting additional data](../../automating/using/query.md#sorting-additional-data) sections.
   ![](assets/enrichment_example4.png)

   If you would like to check that the data is correctly transferred by the activity's outbound transition, start the workflow for the first time (without the **[!UICONTROL Email delivery]** activity) and open the query's outbound transition.

   ![](assets/enrichment_example5.png)

1. Add an **[!UICONTROL Email delivery]** activity. 在電子郵件內容中，插入對應於查詢中計算資料的個人化欄位。You can find it via the **[!UICONTROL Additional data (targetData)]** link of the personalization fields explorer.

   ![](assets/enrichment_example3.png)

您的工作流程現在已可供執行。查詢中定位的描述檔會收到一封個人化電子郵件，內含從其交易計算的資料。

## Query samples {#query-samples}

### Targeting on simple profile attributes {#targeting-on-simple-profile-attributes}

以下範例顯示設定為18到30歲之目標男性的查詢活動。

![](assets/query_sample_1.png)

### Targeting on email attributes {#targeting-on-email-attributes}

下列範例顯示設定為電子郵件地址網域「orange.co.uk」的設定檔活動的查詢活動。

![](assets/query_sample_emaildomain.png)

下列範例顯示設定為電子郵件地址之目標設定檔的查詢活動。

![](assets/query_sample_emailnotempty.png)

### Targeting profiles whose birthday is today {#targeting-profiles-whose-birthday-is-today}

下列範例顯示設定其生日之目標設定檔的查詢活動。

1. Drag the **[!UICONTROL Birthday]** filter in your query.

   ![](assets/query_sample_birthday.png)

1. Set the **[!UICONTROL Filter type]** to **[!UICONTROL Relative]** and select **[!UICONTROL Today]**.

   ![](assets/query_sample_birthday2.png)

### Targeting profiles who opened a specific delivery {#targeting-profiles-who-opened-a-specific-delivery}

下列範例顯示設定為篩選描述檔的查詢活動，以「夏季時間」為標籤開啓傳送。

1. Drag the **[!UICONTROL Opened]** filter in your query.

   ![](assets/query_sample_opened.png)

1. Select the delivery then click **[!UICONTROL Confirm]**.

   ![](assets/query_sample_opened2.png)

### Targeting profiles for whom deliveries failed for a specific reason {#targeting-profiles-for-whom-deliveries-failed-for-a-specific-reason}

下列範例顯示已設定為篩選描述檔的查詢活動，因為他們的mailbox已滿。This query is only available for users with administration rights and belonging to the **[!UICONTROL All (all)]** organizational units (see [this section](../../administration/using/organizational-units.md)).

1. Select the **[!UICONTROL Delivery logs]** resource in order to filter directly in the delivery log table (see [Using resources different from targeting dimensions](../../automating/using/query.md#using-resources-different-from-targeting-dimensions)).

   ![](assets/query_sample_failure1.png)

1. Drag the **[!UICONTROL Nature of failure]** filter in your query.

   ![](assets/query_sample_failure2.png)

1. 選擇您要定位的失敗類型。**[!UICONTROL Mailbox full]**&#x200B;在我們的個案中。

   ![](assets/query_sample_failure3.png)

### Targeting profiles not contacted during the last 7 days {#targeting-profiles-not-contacted-during-the-last-7-days}

下列範例顯示設定的查詢活動，以篩選過去天未與之聯絡的設定檔。

1. Drag the **[!UICONTROL Delivery logs (logs)]** filter in your query.

   ![](assets/query_sample_7days.png)

   Select **[!UICONTROL Does not exist]** in the drop-down list, then drag the **[!UICONTROL Delivery]** filter.

   ![](assets/query_sample_7days1.png)

1. 設定篩選如下。

   ![](assets/query_sample_7days2.png)

### Targeting profiles who clicked a specific link {#targeting-profiles-who-clicked-a-specific-link-}

1. Drag the **[!UICONTROL Tracking logs (tracking)]** filter in your query.

   ![](assets/query_sample_trackinglogs.png)

1. Drag the **[!UICONTROL Label (urlLabel)]** filter.

   ![](assets/query_sample_trackinglogs2.png)

1. In the **[!UICONTROL Value]** field, type the label that was defined when inserting the link in the delivery, then confirm.

   ![](assets/query_sample_trackinglogs3.png)

