---
title: 遞增查詢
seo-title: 遞增查詢
description: 遞增查詢
seo-description: 遞增查詢活動可讓您從Adobe Campaign資料庫篩選並提取元素族群。
page-status-flag: 從未啓動
uuid: 73b42422-e815-43ef-84c0-97c4433 cc98
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: reference
topic-tags: 定位活動
discoiquuid: 80961e73-42ec-463a-8496-cff69 fab0475
context-tags: 遞增，主要
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Incremental query{#incremental-query}

## Description {#description}

![](assets/incremental.png)

**[!UICONTROL Incremental query]** 此活動可讓您從Adobe Campaign資料庫篩選並提取元素族群。每次執行此活動時，會排除先前執行的結果。這可讓您僅定位新元素。

You can define **[!UICONTROL Additional data]** for the targeted population via a dedicated tab. 此資料儲存在其他欄中，只能用於進行中的工作流程。

活動使用查詢編輯器工具。This tool is detailed in a [dedicated section](../../automating/using/editing-queries.md#about-query-editor).

## Context of use {#context-of-use}

An **[!UICONTROL Incremental query]** has to be linked to a **[!UICONTROL Scheduler]** in order to define the execution frequency of the workflow, and therefore the query.

**[!UICONTROL Processed data]** 此標籤屬於此活動專屬，可讓您視需要檢視活動先前執行的任何結果。

**[!UICONTROL Incremental query]** 活動可用於各種類型的使用：

* 劃分個人來定義訊息、觀眾等目標。
* 匯出資料。

## Configuration {#configuration}

1. Drag and drop an **[!UICONTROL Incremental query]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. If you would like to run a query on a resource other than the profile resource, go to the activity's **[!UICONTROL Properties]** tab and select a **[!UICONTROL Resource]** and a **[!UICONTROL Targeting dimension]**.

   The **[!UICONTROL Resource]** allows you to refine the filters displayed in the palette whereas the **[!UICONTROL Targeting dimension]**, contextual with regard to the resource selected, corresponds to the type of population that you would like to obtain (identified profiles, deliveries, data linked to the selected resource, etc.).

1. **[!UICONTROL Target]** 在標籤中，透過定義和結合規則來執行查詢。
1. **[!UICONTROL Processed data]** 在標籤中，選擇您要用於下一個工作流程執行的遞增模式：

   * **[!UICONTROL Use the exclusion of the results of previous executions]**：每個新執行的結果會被排除在外。
   * **[!UICONTROL Use a date field]**：下一個執行只會考量選取日期欄位大於或等於 **[!UICONTROL Incremental query]** 活動的最後執行日期的結果。You can select any date field pertaining to the resource selected in the **[!UICONTROL Properties]** tab. 查詢大型資源(例如記錄檔資料)時，此模式具有較佳的效能。

      第一次執行工作流程後，您可以在此標籤中看到上次執行的執行日期。每次執行工作流程時都會自動更新它。您仍有可能透過手動輸入新值來覆蓋此值，使其符合您的需求。
   >[!NOTE]
   >
   >**[!UICONTROL Use a date field]** 此模式可根據選取的日期欄位提供更大的彈性。例如，如果選取的欄位對應至修改日期，日期欄位模式可讓您擷取最近更新過的資料，而其他模式只會排除先前執行中已定位的錄制，即使自上次執行工作流程後，也已修改記錄。

   ![](assets/incremental_query_usedatefield.png)

1. You can define **[!UICONTROL Additional data]** for the targeted population via a dedicated tab. 此資料儲存在其他欄中，只能用於進行中的工作流程。尤其是，您可以從連結至查詢目標維度的Adobe Campaign資料庫表格中新增資料。Consult the [Enriching data](../../automating/using/query.md#enriching-data) section.
1. 確認活動的設定並儲存工作流程。

## Enriching data {#enriching-data}

Just as for a query, you can enrich the data from an **[!UICONTROL Incremental query]**. Consult the [Enriching data](../../automating/using/query.md#enriching-data) section.

## Example: incremental query on subscribers to a service {#example--incremental-query-on-subscribers-to-a-service}

The following example shows the configuration of an **[!UICONTROL Incremental query]** activity which filters the profiles in the Adobe Campaign database that are subscribed to the **Running Newsletter** service, to send them a welcome email containing a promo code.

工作流程由下列元素組成：

![](assets/incremental_query_example1.png)

* **[!UICONTROL Scheduler]** 活動，每次星期一早上執行工作流程。

   ![](assets/incremental_query_example2.png)

* **[!UICONTROL Incremental query]** 活動，該活動會在第一次執行期間鎖定所有目前訂閱者，然後只有該星期的新訂閱者進行下列執行。

   ![](assets/incremental_query_example3.png)

* **[!UICONTROL Email delivery]** 活動。工作流程每周執行一次，但您可以匯總傳送的電子郵件和每個月的結果，例如在整個月內產生報表，而不只是一周。

   To do this, choose to create a **[!UICONTROL Recurring email]** here regrouping the emails and the results **[!UICONTROL By month]**.

   定義您的電子郵件內容，插入歡迎促銷代碼。

   For more on this, refer to the [Email delivery](../../automating/using/email-delivery.md) and [Defining email content](../../designing/using/about-personalization.md) sections.

然後開始工作流程執行。新訂戶每周都會收到歡迎電子郵件，其中包含促銷代碼。

## Example: incremental query on delivery logs {#example--incremental-query-on-delivery-logs}

You can use an **[!UICONTROL Incremental query]** activity to regularly export new logs in files. 如果您想要在外部報表或BI工具中使用記錄資料，它就很有用。

[Export logs](../../automating/using/exporting-logs.md) section中提供完整的範例。
