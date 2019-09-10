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
source-git-commit: bb65cbf808a95e8b42b2a682b7c0a9cc6225d920

---


# 編輯查詢{#editing-queries}

## 關於查詢編輯器 {#about-query-editor}

查詢編輯器是精靈，可讓您篩選Adobe Campaign資料庫中包含的資料。

此功能可讓您透過預先定義的篩選條件和規則，建立訪客以更好地鎖定收件者。

數個應用程式功能會使用它，以：

* 建立 **查詢** 類型 **觀眾**
* 定義 **電子郵件** 目標
* 定義 **工作流程** 活動中的人口族群

## 查詢編輯器介面 {#query-editor-interface}

查詢編輯器由 **浮動視窗** 和 **工作區**&#x200B;組成。

![](assets/query_editor_overview.png)

### Palette {#palette}

浮動視窗位於編輯器左側，可分為兩個標籤，其中包含分割為主題區塊的元素。這些標籤包括：

* **「捷徑」，**&#x200B;依預設提供或由執行個體管理員建立。您可以在這裡找到欄位、節點、群組、1-1連結、1-N連結和其他預先定義的篩選器。
* **可** 讓您存取目標資源中所有可用欄位的Explorer：節點、群組元素、連結(1-1和1-N)。

標籤中包含的元素必須移至工作區中，才能設定並考量查詢。視選取的定位維度(請參閱 [定位維度和資源](../../automating/using/query.md#targeting-dimensions-and-resources))，您可以：

* 逐一選取受眾或個人檔案
* 使用預先定義的篩選器
* 定義您所選擇欄位的簡單規則
* 定義進階規則，讓您可以將函數套用至特定欄位

### 工作區 {#workspace}

工作區是您可以設定及組合從浮動視窗中新增的規則、對象和預先定義篩選的中央區域。

當您從浮動視窗中移動元素至工作區時，會開啓新視窗，您可以開始 [建立查詢](../../automating/using/editing-queries.md#creating-queries)。

## 建立查詢 {#creating-queries}

查詢編輯器可用來定義訊息中的對象或測試描述檔、工作流程中的人口族群，以及建立查詢類型觀眾。

建立工作流程時 **[!UICONTROL Audience]** 可在視窗中定義查詢，同時建立傳送或 **查詢** 活動。

1. 將元素從浮動視窗移至工作區。編輯規則的視窗隨即開啓。

   * 對於字串或數值 **欄位**，請指定比較運算子和值。

      ![](assets/query_editor_audience_definition2.png)

   * 對於日期或日期和時間 **欄位**，您可以選擇定義特定日期、兩個日期之間的範圍，或相對於查詢執行日期的期間。

      ![](assets/query_editor_date_field.png)

   * 對於布林 **欄位**，請勾選連結至欄位可能值的方塊。
   * 對於 **群組** 欄位，選取您要建立規則的群組欄位，然後定義與其他欄位相同的條件。

      ![](assets/query_editor_audience_definition4.png)

   * 對於具有其他資料庫資源的 **1-1** 連結，請直接從表格選取值。

      ![](assets/query_editor_audience_definition5.png)

   * 對於 **具有其他資料庫資源的1-N** 連結，您可以在第二個資源的欄位上定義子查詢。

      您不需要指定子條件。

      例如，您只能在描述檔追蹤記錄檔上選取 **[!UICONTROL Exists]** 運算元，並核准規則。規則會傳回追蹤記錄檔的所有描述檔。

      ![](assets/query_editor_audience_definition6.png)

   * 對於 **預先定義的篩選**，請根據提供的條件輸入或選取您喜歡的元素。

      管理員可以建立篩選器來協助複雜和重復的查詢。這些項目會以預先設定規則的形式出現在查詢編輯器中，並限制使用者需要執行的步驟數。

      ![](assets/query-editor_filter_email-audience_filter.png)

1. 您可以指定規則的名稱。然後會顯示為工作區中的規則名稱。如果未指定規則，則會顯示條件的自動說明。
1. 若要結合工作區元素，請將它們互相連結，以建立不同群組和/或群組層級。接著您可以選取邏輯運算元，將元素組合在同一層級：

   * **[!UICONTROL AND]**：兩個准則間的交叉點。只會考量符合每個標準的元素。
   * **[!UICONTROL OR]**：兩種准則的聯合組織。會考量比對兩個標準至少一個的元素。
   * **[!UICONTROL EXCEPT]**：排除准則。符合第一個標準的元素會納入考量，除非它們也符合第二個標準。

1. 您現在可以使用動作列中的 ![](assets/count.png)![](assets/preview.png) 和按鈕，計算並預覽查詢所鎖定的元素數目。

   ![](assets/query_editor_combining_rules.png)

如果您想要修改查詢的元素，請按一下編輯圖示。規則會在先前設定時開啓，然後您就可以進行任何必要的調整。

您的查詢現在已建立並定義，可讓您建立更好的個人化傳送方式。

**相關主題：**

* [進階功能](../../automating/using/advanced-expression-editing.md)
* [定義篩選器](../../developing/using/configuring-filter-definition.md)
* [使用案例：建立一次一次的電子郵件傳送](../../automating/using/workflow-weekly-offer.md)
* [使用案例：建立在位置上分段的傳送](../../automating/using/workflow-segmentation-location.md)
* [使用案例：建立具有輔助功能的傳送](../../automating/using/workflow-created-query-with-complement.md)
* [使用案例：重新定位工作流程，將新傳送傳送至非opervers](../../automating/using/workflow-cross-channel-retargeting.md)
