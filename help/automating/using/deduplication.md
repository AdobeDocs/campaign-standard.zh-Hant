---
title: 去重復化
seo-title: 去重復化
description: 去重復化
seo-description: 「去重復化」活動可讓您刪除傳入活動結果中的重復項目。
page-status-flag: 從未啓動
uuid: 11a22a9c-3bfe-4953-8a52-2f4e93c128fb
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: reference
topic-tags: 定位活動
discoiquuid: e7a5e1e7-4680-46c7-98b8-0a47bb7be8b
context-tags: dudp，main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Deduplication{#deduplication}

## Description {#description}

![](assets/deduplication.png)

**[!UICONTROL Deduplication]** 活動可讓您刪除傳入活動結果中的重復項目。

## Context of use {#context-of-use}

**[!UICONTROL Deduplication]** 活動通常用於定位活動或匯入檔案之後，在允許使用目標資料的活動之前。

在去重復化期間，傳入的轉場會分開處理。例如，如果查詢結果中出現profile'A'，且在查詢結果中出現'A'，則不會對它進行去重復化。

因此，建議消除重復資料只能有一個傳入轉場。若要這麼做，您可以使用對應到您的定位需求(例如聯合活動等)的活動，結合不同的查詢。例如：

![](assets/dedup_bonnepratique.png)

## Configuration {#configuration}

若要設定去重復化活動，您必須輸入標籤、方法和去重復化標準，以及與結果相關的選項。

1. Drag and drop a **[!UICONTROL Deduplication]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.

   ![](assets/deduplication_1.png)

1. Select the **[!UICONTROL Resource type]** on which the deduplication has to be carried out:

   * **[!UICONTROL Database resource]** 如果對資料庫中已存在的資料進行去重復化。Select the **[!UICONTROL Filtering dimension]** and the **[!UICONTROL Targeting dimension]**, depending on the data that you want to deduplicate. By default, deduplication is carried out on the **profiles**.
   * **[!UICONTROL Temporary resource]** 如果對工作流程的暫存資料進行去重復化：選取 **[!UICONTROL Targeted set]** 包含資料重復的資料。匯入檔案或資料庫中的資料(例如區段代碼)後，可能會發生此使用案例。

1. Select the **[!UICONTROL Number of unique records to keep]**. 此欄位的預設值為1。值0可讓您保留所有重復項目。

   例如，如果記錄A和B被視為記錄Y的重復項目，則記錄C會被視為記錄Z的副本：

   * 如果欄位的值為1：僅保留Y和Z記錄。
   * 如果欄位的值為0：所有記錄都會保留下來。
   * 如果欄位的值為2：記錄C和Z，並保留A、B和Y的記錄，或視其後選取的去重復化方法而定。

1. Define the **[!UICONTROL Duplicate identification]** criteria by adding conditions in the list provided. 指定相同值允許識別重復項目的欄位和/或運算式：電子郵件地址、名字、姓氏等。條件的順序可讓您指定要先處理的項目。
1. In the drop-down list, select the **[!UICONTROL Deduplication method]** to use:

   * **[!UICONTROL Choose for me]**：隨機選取記錄，以避免重復。
   * **[!UICONTROL Following a list of values]**：可讓您定義一或多個欄位的值優先順序。若要定義值，請選取欄位或建立運算式，然後將值新增至適當表格。To define a new field, click the **[!UICONTROL Add]** button located above the list of values.

      ![](assets/deduplication_2.png)

   * **[!UICONTROL Non-empty value]**：這可讓您保留所選運算式值不是空的記錄。

      ![](assets/deduplication_3.png)

   * **[!UICONTROL Using an expression]**：這可讓您保留輸入的運算式值最小或最大的記錄。

      ![](assets/deduplication_4.png)

1. If needed, manage the activity's [Transitions](../../automating/using/executing-a-workflow.md#managing-an-activity-s-outbound-transitions) to access the advanced options for the outbound population.
1. 確認活動的設定並儲存工作流程。

## Example 1: Identifying duplicates before a delivery {#example-1--identifying-duplicates-before-a-delivery}

下列範例說明可讓您在傳送電子郵件前排除目標的重復資料。這表示您不需要多次傳送通訊給相同的個人檔案。

工作流程由：

![](assets/deduplication_example_workflow.png)

* A **[!UICONTROL Query]** which allows you to define the target of the email. 在這裡，工作流程會定位用戶端資料庫中已超過一年的所有設定檔。

   ![](assets/deduplication_example_query.png)

* **[!UICONTROL Deduplication]** 活動，可讓您識別來自上一個查詢的重復項目。在此範例中，每個複製只會儲存一個記錄。會使用電子郵件地址來識別重復的項目。這表示電子郵件傳送只能傳送一次，讓目標的電子郵件地址出現在定位中。

   The deduplication method selected is **[!UICONTROL Non-empty value]**. This allows you to ensure that amongst the records kept in case of duplicates, priority is given to those in which the **First name** has been provided. 如果電子郵件內容的個人化欄位使用第一個名稱，這會使其更具一致性。

   此外，還會新增額外轉場，以保留重復項目並加以列出。

   ![](assets/deduplication_example_dedup.png)

* An **[!UICONTROL Email delivery]** placed after the main outbound transition of the deduplication. The configuration for email deliveries is detailed in the [Email delivery](../../automating/using/email-delivery.md) section.
* A **[!UICONTROL Save audience]** activity placed after the additional transition of the deduplication to save the duplicates in a **Duplicates** audience. 可重復使用此對象，直接排除每個電子郵件傳遞的成員。

## Example 2: Deduplicating the data from an imported file {#example-2--deduplicating-the-data-from-an-imported-file}

此範例顯示如何在將資料載入資料庫之前，先從匯入的檔案刪除資料。此程序可改善資料庫中載入的資料品質。

工作流程由：

![](assets/deduplication_example2_workflow.png)

* A file that contains a list of profiles is imported using a **[!UICONTROL Load file]** activity. 在此範例中，匯入的檔案為. csv格式，並包含10個描述檔：

   ```
   lastname;firstname;dateofbirth;email
   Smith;Hayden;23/05/1989;hayden.smith@example.com
   Mars;Daniel;17/11/1987;dannymars@example.com
   Smith;Clara;08/02/1989;hayden.smith@example.com
   Durance;Allison;15/12/1978;allison.durance@example.com
   Lucassen;Jody;28/03/1988;jody.lucassen@example.com
   Binder;Tom;19/01/1982;tombinder@example.com
   Binder;Tommy;19/01/1915;tombinder@example.com
   Connor;Jade;10/10/1979;connor.jade@example.com
   Mack;Clarke;02/03/1985;clarke.mack@example.com
   Ross;Timothy;04/07/1986;timross@example.com
   ```

   此檔案也可用來偵測並定義欄的格式。From the **[!UICONTROL Column definition]** tab, make sure that each column of the imported file is configured correctly.

   ![](assets/deduplication_example2_fileloading.png)

* **[!UICONTROL Deduplication]** 活動。匯入檔案後，再將資料插入資料庫後，就會直接進行去重復化。It should therefore be based on the **[!UICONTROL Temporary resource]** from the **[!UICONTROL Load file]** activity.

   在此範例中，我們想要針對檔案中包含的每個唯一電子郵件地址保留單一項目。Duplicate identification is therefore carried out on the **email** column of the temporary resource. 但是，檔案中會出現兩個電子郵件地址。因此，兩行將視為重復。

   ![](assets/deduplication_example2_dedup.png)

* **[!UICONTROL Update data]** 活動可讓您將資料從去重復化程序插入資料庫中。只有在資料更新後，才會將匯入的資料識別為屬於描述檔維度的資料。

   Here, we would like to **[!UICONTROL Insert only]** the profiles that do not already exist in the database. We are going to do this by using the file's email column and the email field from the **Profile** dimension as the reconciliation key.

   ![](assets/deduplication_example2_writer1.png)

   Specify the mappings between the file's columns from which you want to insert the data and the database fields from the **[!UICONTROL Fields to update]** tab.

   ![](assets/deduplication_example2_writer2.png)

然後開始工作流程。從去重復化程序儲存的記錄會新增至資料庫中的描述檔。
