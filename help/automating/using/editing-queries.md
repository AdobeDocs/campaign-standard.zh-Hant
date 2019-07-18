---
title: 編輯查詢
seo-title: 編輯查詢
description: 編輯查詢
seo-description: 運用預先定義的篩選條件和規則來建立人口族群。
page-status-flag: 從未啓動
uuid: a49c7739-a96 c-45cb-9ac5-1ce299161 a97
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: reference
topic-tags: 篩選資料
discoiquuid: 84306a-1e-0d9f-44cc-88a7-36d7e5b4da1f
context-tags: QueryFilter，概觀；觀眾，主要
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Editing queries{#editing-queries}

## About query editor {#about-query-editor}

查詢編輯器是精靈，可讓您篩選Adobe Campaign資料庫中包含的資料。

此功能可讓您透過預先定義的篩選條件和規則，建立訪客以更好地鎖定收件者。

數個應用程式功能會使用它，以：

* Create **Query** type **audiences**
* Define **email** targets
* Define populations in **workflow** activities

## Query editor interface {#query-editor-interface}

The query editor is made up of a **Palette** and a **Workspace**.

![](assets/query_editor_overview.png)

### Palette {#palette}

浮動視窗位於編輯器左側，可分為兩個標籤，其中包含分割為主題區塊的元素。這些標籤包括：

* **「捷徑」，**&#x200B;依預設提供或由執行個體管理員建立。您可以在這裡找到欄位、節點、群組、1-1連結、1-N連結和其他預先定義的篩選器。
* **可** 讓您存取目標資源中所有可用欄位的Explorer：節點、群組元素、連結(1-1和1-N)。

標籤中包含的元素必須移至工作區中，才能設定並考量查詢。Depending on the targeting dimension selected (see [Targeting dimensions and resources](../../automating/using/query.md#targeting-dimensions-and-resources)), you can:

* 逐一選取受眾或個人檔案
* 使用預先定義的篩選器
* 定義您所選擇欄位的簡單規則
* 定義進階規則，讓您可以將函數套用至特定欄位

### Workspace {#workspace}

工作區是您可以設定及組合從浮動視窗中新增的規則、對象和預先定義篩選的中央區域。

When you move an element from the palette into the workspace, a new window opens and you can start [Creating queries](../../automating/using/editing-queries.md#creating-queries).

## Creating queries {#creating-queries}

查詢編輯器可用來定義訊息中的對象或測試描述檔、工作流程中的人口族群，以及建立查詢類型觀眾。

Queries can be defined in the **[!UICONTROL Audience]** window while creating a delivery or in a **Query** activity while creating a workflow.

1. 將元素從浮動視窗移至工作區。編輯規則的視窗隨即開啓。

   * For a string or numerical **field**, specify the comparison operator and the value.

      ![](assets/query_editor_audience_definition2.png)

   * For a date or date and time **field**, you can choose to define a specific date, a range between two dates, or a period relative to the query's execution date.

      ![](assets/query_editor_date_field.png)

   * For a Boolean **field**, check the boxes linked to the possible values for the field.
   * For a **grouping** field, select the grouping field on which you want to create the rule, then define the condition in the same way as for the other fields.

      ![](assets/query_editor_audience_definition4.png)

   * For a **1-1** link with another database resource, select a value directly from the table targeted.

      ![](assets/query_editor_audience_definition5.png)

   * For a **1-N** link with another database resource, you can define a sub-query on the fields of this second resource.

      您不需要指定子條件。

      For example, you can only select the **[!UICONTROL Exists]** operator on the profile tracking logs and approve the rule. 規則會傳回追蹤記錄檔的所有描述檔。

      ![](assets/query_editor_audience_definition6.png)

   * For a **predefined filter**, enter or select the elements you like according to the criteria offered.

      管理員可以建立篩選器來協助複雜和重復的查詢。這些項目會以預先設定規則的形式出現在查詢編輯器中，並限制使用者需要執行的步驟數。

      ![](assets/query-editor_filter_email-audience_filter.png)

1. 您可以指定規則的名稱。然後會顯示為工作區中的規則名稱。如果未指定規則，則會顯示條件的自動說明。
1. 若要結合工作區元素，請將它們互相連結，以建立不同群組和/或群組層級。接著您可以選取邏輯運算元，將元素組合在同一層級：

   * **[!UICONTROL AND]**：兩個准則間的交叉點。只會考量符合每個標準的元素。
   * **[!UICONTROL OR]**：兩種准則的聯合組織。會考量比對兩個標準至少一個的元素。
   * **[!UICONTROL EXCEPT]**：排除准則。符合第一個標準的元素會納入考量，除非它們也符合第二個標準。

1. You can now calculate and preview the number of elements targeted by your query using the ![](assets/count.png) and ![](assets/preview.png) buttons from the action bar.

   ![](assets/query_editor_combining_rules.png)

如果您想要修改查詢的元素，請按一下編輯圖示。規則會在先前設定時開啓，然後您就可以進行任何必要的調整。

您的查詢現在已建立並定義，可讓您建立更好的個人化傳送方式。

**相關主題：**

* [進階功能](../../automating/using/advanced-expression-editing.md)
* [定義篩選器](../../developing/using/configuring-filter-definition.md)

