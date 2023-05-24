---
title: Adobe Campaign Standard資料模型最佳做法
description: 瞭解設計您的Adobe Campaign Standard資料模型時的最佳做法。
audience: developing
content-type: reference
topic-tags: about-custom-resources
context-tags: cusResource,overview;eventCusResource,overview
feature: Data Model
role: Developer
level: Experienced
exl-id: 58d4e02f-3c9a-4e5d-a6aa-fdbcec0d8dda
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '1556'
ht-degree: 1%

---

# 資料模型最佳實務{#data-model-best-practices}

本文檔概述了設計Adobe Campaign資料模型時的主要建議。


>[!NOTE]
>
>要建立和修改資源以擴展Adobe Campaign預定義的資料模型，請參閱 [此部分](../../developing/using/key-steps-to-add-a-resource.md)。
>
>可以在中查找內置資源的資料模型表示 [此頁](../../developing/using/datamodel-introduction.md)。

## 概覽 {#overview}

Adobe Campaign系統極其靈活，可以擴展到最初的實施之外。 但是，儘管可能性是無限的，但做出明智決策並建立堅實的基礎是開始設計您的資料模型的關鍵。

本文檔提供了常用案例和最佳做法，以瞭解如何正確設計您的Adobe Campaign工具。

## 資料模型體系結構 {#data-model-architecture}

Adobe Campaign Standard是一個功能強大的跨渠道市場活動管理系統，可幫助您調整線上和離線策略以創造個性化的客戶體驗。

### 以客戶為中心的方法 {#customer-centric-approach}

雖然大多數電子郵件服務提供商都在通過以清單為中心的方式與客戶進行溝通，但Adobe Campaign卻依賴關係資料庫來利用客戶及其屬性的更廣泛視圖。

以客戶為中心的方法如下圖所示。 的 **配置檔案** 以灰色表示的資源代表正圍繞其構建一切的主要客戶表：

![](assets/customer-centric-data-model.png)

Adobe Campaign預設資料模型在此 [節](../../developing/using/datamodel-introduction.md)。

<!--You can find a datamodel representation for the out-of-the-box resources [here](../../developing/using/datamodel-introduction.md).-->

<!--### What is a customer? {#customer-definition}

If you have customer data in more than one system, you need to determine which solution will allow you to identify records as one person. This work might require rules, eventually a match and merge processes to determine the primary record. This primary record should be the one sent to Adobe Campaign.

While some of this data cleansing might be performed in Adobe Campaign, the recommendation is to run these processes outside and only import clean data in Adobe Campaign. You should keep Campaign as a marketing solution more than a data cleansing tool.

Be able to provide a primary customer record which will be sent to Adobe Campaign.-->

### Adobe Campaign資料 {#data-for-campaign}

哪些資料應該發送到Adobe Campaign? 確定您的營銷活動所需的資料至關重要。

>[!NOTE]
>
>Adobe Campaign不是資料倉庫。 因此，不要嘗試將所有可能的客戶及其關聯資訊導入Adobe Campaign。

要決定Adobe Campaign是否需要某種屬性，請確定該屬性是否屬於下列類別之一：
* 用於 **分割**
* 用於 **資料管理流程** （例如，聚合計算）
* 用於 **個性化**
* 用於 **報告** （可以根據自定義配置檔案資料建立報告）

如果不是陷入其中，你很可能不需要這個屬性在Adobe Campaign。

### 資料類型 {#data-types}

為確保系統的良好體系結構和效能，請遵循以下最佳實踐在Adobe Campaign設定資料：
* 字串欄位的長度應始終與列一起定義。 預設情況下，Adobe Campaign的最大長度為255個字元，但Adobe建議在您已經知道該大小不會超過較短長度時將欄位保持較短。
* 如果您確定源系統中的欄位被高估而無法達到，則可以接受在Adobe Campaign使用的欄位比源系統中的欄位短。 這可能意味著Adobe Campaign的字串較短或整數較小。

## 配置資料結構 {#configuring-data-structure}

本節概述在以下情況下的最佳做法： [配置資源的資料結構](../../developing/using/configuring-the-resource-s-data-structure.md)。

### 標識符 {#identifiers}

Adobe Campaign資源有三個標識符，並且可以添加一個附加標識符。

下表介紹了這些標識符及其用途。

>[!NOTE]
>
>顯示名稱是通過Adobe Campaign用戶介面顯示給用戶的欄位的名稱。 技術名稱是資源定義中的實際欄位名稱（以及表列名稱）。

| 顯示名稱 | 技術名稱 | 說明 | 最佳實務 |
|--- |--- |--- |--- |
|  | PKey | <ul><li>PKey是Adobe Campaign表的物理主鍵。</li><li>此標識符通常對特定的Adobe Campaign實例唯一。</li><li>在Adobe Campaign Standard，此值對最終用戶不可見（URL除外）。</li></ul> | <ul><li>通過 [API系統](../../api/using/get-started-apis.md)，可以檢索PKey值（該值是生成/散列值，而不是物理鍵）。</li><li>除了通過API檢索、更新或刪除記錄之外，不建議將其用於其他任何用途。</li></ul> |
| ID | 名稱或內部名稱 | <ul><li>此資訊是表中記錄的唯一標識符。 可以手動更新此值。</li><li>此標識符在部署到其他Adobe Campaign實例時保留其值。 它必須具有與生成的值不同的名稱才能通過包導出。</li><li>這不是表的實際主鍵。</li></ul> | <ul><li>請勿使用特殊字元，如空格「」、半列「：」或連字元「 — 」。</li><li>所有這些字元都將替換為下划線「_」（允許的字元）。 例如，「abc-def」和「abc:def」將儲存為「abc_def」，並互相覆蓋。</li></ul> |
| 標籤 | label | <ul><li>標籤是Adobe Campaign中對象或記錄的業務標識符。</li><li>此對象允許空格和特殊字元。</li><li>它不能保證記錄的唯一性。</li></ul> | <ul><li>建議確定對象標籤的結構。</li><li>這是標識Adobe Campaign用戶的記錄或對象的最方便用戶的解決方案。</li></ul> |
| ACS ID | acsID | <ul><li>可以生成附加標識符：這樣 [ACS ID](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources)。</li><li>由於PKey不能在Adobe Campaign用戶介面中使用，因此這是獲得在插入配置檔案記錄期間生成的唯一值的解決方案。</li><li>僅當在將記錄插入Adobe Campaign之前在資源中啟用了該選項時，才能自動生成該值。</li></ul> | <ul><li>此UUID可用作協調鍵。</li><li>自動生成的ACS ID不能用作工作流或包定義中的引用。</li><li>此值特定於Adobe Campaign實例。</li></ul> |

### 識別鍵 {#keys}

在Adobe Campaign建立的每個資源必須至少有一個唯一 [標識密鑰](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys)。

<!--Most organizations are importing records from external systems. While the physical key of a resource lies behind the PKey attribute, it is possible to determine a custom key in addition.

This custom key is the actual record primary key in the external system feeding Adobe Campaign.

When an out-of-the-box resource has both an internal auto-generated and an internal custom key, the internal key will be set as a unique index in the physical database table.-->

建立自定義資源時，有兩個選項：

* 自動生成的密鑰和內部自定義密鑰的組合。 如果系統鍵是複合鍵或不是整數，則此選項很有意義。 整數在大表中提供更高的效能，並與其他表聯接。
* 使用主鍵作為外部系統主鍵。 此解決方案通常是首選的，因為它簡化了資料導入和導出的方法，並且在不同的系統之間具有一致的密鑰。

在工作流中，不應將標識鍵用作引用。

<!--For more on defining identification keys, see [this section](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys).-->

### 索引 {#indexes}

Adobe Campaign自動添加 [索引](../../developing/using/configuring-the-resource-s-data-structure.md#defining-indexes) 到資源中定義的所有主鍵和內部鍵。

* Adobe建議定義附加索引，因為它可能會提高效能。
* 但是，不要添加太多索引，因為索引在資料庫上使用空間。 許多索引也可能對效能產生負面影響。
* 仔細選擇需要定義的索引。

<!--For more on defining indexes, see [this section](../../developing/using/configuring-the-resource-s-data-structure.md#defining-indexes).

When you are performing an initial import with very high volumes of data insert in Adobe Campaign database, it is recommended to run that import without custom indexes at first. It will allow to accelerate the insertion process. Once you’ve completed this important import, it is possible to enable the index(es).-->

### 連結 {#links}

定義與其他資源的連結 [此部分](../../developing/using/configuring-the-resource-s-data-structure.md#defining-links-with-other-resources)。

* 雖然可以將任何表加入工作流中，但Adobe建議直接在資料結構定義中定義資源之間的公用連結。
* 連結應與表中的實際資料對齊定義。 錯誤的定義可能影響通過連結檢索到的資料，例如意外地複製記錄。
* 將連結與資源名稱一致命名：連結名稱應有助於瞭解遠程表是什麼。
* 不要將「id」作為尾碼的連結命名。 例如，將其命名為「transaction」，而不是「transactionId」。

<!--For more on defining links with other resources, see [this section](../../developing/using/configuring-the-resource-s-data-structure.md#defining-links-with-other-resources).-->

## 效能 {#performance}

為確保在任何時間都能獲得更好的效能，請遵循以下最佳做法。

### 一般性建議 {#general-recommendations}

* 避免在查詢中使用「CONTAINS」等操作。 如果知道預期的內容並希望過濾，請將相同條件與「EQUAL TO」或其他特定篩選器運算子一起應用。
* 在工作流中生成資料時，避免與非索引欄位連接。
* 請確保在工作時間之外執行導入和導出等過程。
* 確保有所有日常活動的時間表，並遵守時間表。
* 如果日進程中的一個或幾個失敗，並且必須在當天運行，請確保在手動進程啟動時沒有運行衝突的進程，因為這可能會影響系統效能。
* 確保在導入流程期間或執行任何手動流程期間未運行任何每日市場活動。
* 使用一個或多個引用表，而不是在每行中複製欄位。 使用鍵/值對時，最好選擇數字鍵。
* 短字串仍然可接受。 如果引用表已在外部系統中就位，則重新使用它將有助於與Adobe Campaign的資料整合。

### 一對多關係 {#one-to-many-relationships}

* 資料設計影響可用性和功能性。 如果您設計的資料模型具有許多一對多關係，則用戶在應用程式中構造有意義的邏輯會更加困難。 一對多過濾邏輯對於非技術營銷人員來說很難正確構造和理解。
* 將所有基本欄位放在一個表中是件好事，因為它使用戶更容易生成查詢。 有時，如果可以避免聯接，則在表間複製某些欄位也對效能有利。
* 某些內置功能將不能引用一對多關係，例如「提供加權公式」和「交付」。

### 大表 {#large-tables}

以下是使用大型表和複雜連接設計資料模型時應遵循的一些最佳做法。

* 減少列數，特別是通過標識未使用的列數。
* 通過避免複雜的連接（例如在若干條件和/或幾列上的連接）來優化資料模型關係。
* 對於聯接鍵，請始終使用數字資料而不是字串。
* 盡可能減少日誌保留深度。 如果需要更深的歷史記錄，可以聚合計算和/或處理自定義日誌表以儲存更大的歷史記錄。
