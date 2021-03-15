---
solution: Campaign Standard
product: campaign
title: Adobe Campaign Standard的資料模型最佳實踐
description: 瞭解設計您的Adobe Campaign Standard資料模型時的最佳範例。
audience: developing
content-type: reference
topic-tags: about-custom-resources
context-tags: cusResource,overview;eventCusResource,overview
feature: 資料模型
role: 開發人員
level: 經驗豐富
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '1560'
ht-degree: 1%

---


# 資料模型最佳實務{#data-model-best-practices}

本檔案概述設計您的Adobe Campaign資料模型時的主要建議。


>[!NOTE]
>
>要建立和修改資源以擴展Adobe Campaign預定義的資料模型，請參閱[本節](../../developing/using/key-steps-to-add-a-resource.md)。
>
>您可以在[本頁](../../developing/using/datamodel-introduction.md)中找到內置資源的資料模型表示。

## 概觀 {#overview}

Adobe Campaign系統極為靈活，可以擴展至最初的實施範圍之外。 不過，儘管可能性無限，但必須做出明智決策並建立堅實的基礎，才能開始設計您的資料模型。

本檔案提供常見的使用案例和最佳範例，以瞭解如何正確設計您的Adobe Campaign工具。

## 資料模型體系結構{#data-model-architecture}

Adobe Campaign Standard是功能強大的跨通道宣傳管理系統，可協助您調整線上和線下策略，以建立個人化客戶體驗。

### 以客戶為中心的方法{#customer-centric-approach}

雖然大多數電子郵件服務供應商都是透過以清單為中心的方式與客戶溝通，但Adobe Campaign仍依賴關係資料庫，以運用更廣泛的客戶及其屬性檢視。

以客戶為中心的方法如下圖所示。 **Profile**&#x200B;資源以灰色表示正在構建所有內容的主要客戶表：

![](assets/customer-centric-data-model.png)

此[部分](../../developing/using/datamodel-introduction.md)中顯示了Adobe Campaign預設資料模型。

<!--You can find a datamodel representation for the out-of-the-box resources [here](../../developing/using/datamodel-introduction.md).-->

<!--### What is a customer? {#customer-definition}

If you have customer data in more than one system, you need to determine which solution will allow you to identify records as one person. This work might require rules, eventually a match and merge processes to determine the primary record. This primary record should be the one sent to Adobe Campaign.

While some of this data cleansing might be performed in Adobe Campaign, the recommendation is to run these processes outside and only import clean data in Adobe Campaign. You should keep Campaign as a marketing solution more than a data cleansing tool.

Be able to provide a primary customer record which will be sent to Adobe Campaign.-->

### Adobe Campaign資料{#data-for-campaign}

哪些資料應該傳送至Adobe Campaign? 確定行銷活動所需的資料至關重要。

>[!NOTE]
>
>Adobe Campaign不是資料倉庫。 因此，請勿嘗試將所有可能的客戶及其相關資訊匯入Adobe Campaign。

要決定是否需要在Adobe Campaign使用某個屬性，請確定屬性是否屬於以下類別：
* 用於&#x200B;**segmentation**&#x200B;的屬性
* 用於&#x200B;**資料管理進程**&#x200B;的屬性（例如聚合計算）
* 用於&#x200B;**個人化**&#x200B;的屬性
* 用於&#x200B;**reporting**&#x200B;的屬性（可以根據自訂描述檔資料建立報表）

如果不是落入其中任何一個圈套，你很可能不需要Adobe Campaign的這個屬性。

### 資料類型 {#data-types}

為確保系統的良好架構和效能，請遵循下列最佳實務，在Adobe Campaign設定資料：
* 字串欄位的長度應一律以欄定義。 依預設，Adobe Campaign的最大長度為255個字元，但Adobe建議您在已知大小不會超過較短長度時，將欄位保持在較短的長度。
* 如果您確定源系統的大小被高估且無法達到，那麼在Adobe Campaign的欄位比源系統的欄位短是可以接受的。 這可能意味著Adobe Campaign的字串較短或整數較小。

## 配置資料結構{#configuring-data-structure}

本節概述[配置資源資料結構](../../developing/using/configuring-the-resource-s-data-structure.md)時的最佳做法。

### 標識符{#identifiers}

Adobe Campaign資源有三個識別碼，並且可以添加一個附加的識別碼。

下表說明這些識別碼及其用途。

>[!NOTE]
>
>顯示名稱是透過Adobe Campaign使用者介面向使用者顯示的欄位名稱。 技術名稱是資源定義中的實際欄位名稱（和表列名稱）。

| 顯示名稱 | 技術名稱 | 說明 | 最佳實務 |
|--- |--- |--- |--- |
|  | PKey | <ul><li>PKey是Adobe Campaign桌的物理主鍵。</li><li>此識別碼通常對特定的Adobe Campaign例項唯一。</li><li>在Adobe Campaign Standard，一般使用者看不到此值（URL除外）。</li></ul> | <ul><li>通過[API系統](../../api/using/get-started-apis.md)，可以檢索PKey值（該值是生成／散列值，而不是物理密鑰）。</li><li>建議不要將它用於任何其他目的，而不是透過API擷取、更新或刪除記錄。</li></ul> |
| ID | name或internalName | <ul><li>此資訊是表中記錄的唯一標識符。 此值可以手動更新。</li><li>此識別碼會在部署在不同的Adobe Campaign例項時保留其值。 它的名稱必須與生成的值不同，才能通過包導出。</li><li>這不是表的實際主鍵。</li></ul> | <ul><li>請勿使用特殊字元，例如空格&quot;&quot;、半欄&quot;:&quot;或連字型大小&quot;-&quot;。</li><li>所有這些字元都會以底線&quot;_&quot;（允許的字元）取代。 例如，&quot;abc-def&quot;和&quot;abc:def&quot;會儲存為&quot;abc_def&quot;，並互相覆寫。</li></ul> |
| 標籤 | 標籤 | <ul><li>標籤是Adobe Campaign中對象或記錄的業務標識符。</li><li>此對象允許空格和特殊字元。</li><li>它不保證記錄的獨特性。</li></ul> | <ul><li>建議您決定物件標籤的結構。</li><li>這是最易於使用的解決方案，可為Adobe Campaign用戶識別記錄或對象。</li></ul> |
| ACS ID | acsId | <ul><li>可產生其他識別碼：[ACS ID](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources)。</li><li>由於PKey不能用於Adobe Campaign用戶介面，因此這是一種獲得在插入配置檔案記錄期間生成的唯一值的解決方案。</li><li>只有在將記錄插入Adobe Campaign之前在資源中啟用了該選項，才能自動生成該值。</li></ul> | <ul><li>此UUID可用作協調鍵。</li><li>自動生成的ACS ID不能用作工作流或包定義中的引用。</li><li>此值是Adobe Campaign實例的特定值。</li></ul> |

### 識別鍵 {#keys}

在Adobe Campaign建立的每個資源至少必須有一個唯一的[標識鍵](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys)。

<!--Most organizations are importing records from external systems. While the physical key of a resource lies behind the PKey attribute, it is possible to determine a custom key in addition.

This custom key is the actual record primary key in the external system feeding Adobe Campaign.

When an out-of-the-box resource has both an internal auto-generated and an internal custom key, the internal key will be set as a unique index in the physical database table.-->

建立自定義資源時，有兩個選項：

* 自動產生的金鑰與內部自訂金鑰的組合。 如果您的系統金鑰是複合金鑰或非整數，這個選項就很有趣。 整數在大表格和與其他表格連接時，可提供更高的效能。
* 使用主鍵作為外部系統主鍵。 此解決方案通常較為受歡迎，因為它可簡化資料匯入和匯出的方式，而且不同系統之間的索引鍵一致。

在工作流程中，不應使用識別碼作為參考。

<!--For more on defining identification keys, see [this section](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys).-->

### 索引 {#indexes}

Adobe Campaign自動將[index](../../developing/using/configuring-the-resource-s-data-structure.md#defining-indexes)添加到資源中定義的所有主鍵和內部鍵。

* Adobe建議定義其他索引，因為它可以改善效能。
* 但是，不要添加太多索引，因為它們在資料庫上使用空間。 許多索引也可能對效能產生負面影響。
* 仔細選擇需要定義的索引。

<!--For more on defining indexes, see [this section](../../developing/using/configuring-the-resource-s-data-structure.md#defining-indexes).

When you are performing an initial import with very high volumes of data insert in Adobe Campaign database, it is recommended to run that import without custom indexes at first. It will allow to accelerate the insertion process. Once you’ve completed this important import, it is possible to enable the index(es).-->

### 連結 {#links}

定義與其他資源的連結在[本節](../../developing/using/configuring-the-resource-s-data-structure.md#defining-links-with-other-resources)中顯示。

* 雖然可以在工作流中連接任何表，但Adobe建議直接在資料結構定義中定義資源之間的公共連結。
* 連結的定義應與表格中的實際資料一致。 錯誤的定義可能會影響透過連結擷取的資料，例如意外重複記錄。
* 以資源名稱一致命名連結：連結名稱應有助於瞭解遠程表是什麼。
* 請勿將連結命名為「id」為尾碼。 例如，將其命名為&quot;transaction&quot;，而非&quot;transactionId&quot;。

<!--For more on defining links with other resources, see [this section](../../developing/using/configuring-the-resource-s-data-structure.md#defining-links-with-other-resources).-->

## 效能{#performance}

為了確保隨時都能提供更佳的效能，請遵循下列最佳實務。

### 一般性建議 {#general-recommendations}

* 請避免在查詢中使用「CONTAINS」等操作。 如果您知道要篩選的項目，請使用「EQUAL TO」或其他特定篩選運算子套用相同的條件。
* 在工作流程中建立資料時，請避免加入非索引欄位。
* 請試著確保在工作時間完成匯入和匯出等程式。
* 請確定所有日常活動都有排程，並遵守排程。
* 如果一個或幾個日進程失敗，並且如果強制在同一天運行該進程，請確保手動進程啟動時沒有運行衝突的進程，因為這可能影響系統效能。
* 請確定匯入程式期間或執行任何手動程式時，未執行任何每日促銷活動。
* 使用一或多個參考表，而不是在每一列中複製欄位。 使用鍵／值對時，最好選擇數字鍵。
* 短字串仍可接受。 如果引用表已在外部系統中就位，則重複使用表將有助於與Adobe Campaign的資料整合。

### 一對多關係{#one-to-many-relationships}

* 資料設計會影響可用性和功能。 如果您設計的資料模型具有許多一對多關係，使用者就很難在應用程式中建構有意義的邏輯。 一對多篩選邏輯對於不具備技術背景的行銷人員而言可能很難正確建構和理解。
* 將所有必要欄位都放在一個表格中是好事，因為這可讓使用者更輕鬆地建立查詢。 有時，如果在表中複製某些欄位，則避免連接也會對效能有好處。
* 某些內建功能將無法參考一對多關係，例如選件加權公式和傳送。

### 大表{#large-tables}

以下是使用大型表和複雜連接設計資料模型時應遵循的一些最佳實踐。

* 減少欄數，尤其是識別未使用的欄數。
* 通過避免複雜的連接（如多個條件和／或多個列上的連接）來優化資料模型關係。
* 對於連接鍵，請始終使用數字資料，而不是字串。
* 盡可能減少日誌保留深度。 如果您需要更深入的歷史記錄，您可以匯總計算和／或處理自訂的日誌表，以儲存較大的歷史記錄。