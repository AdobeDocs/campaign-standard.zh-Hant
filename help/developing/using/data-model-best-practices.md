---
title: Adobe Campaign Standard中的資料模型最佳實務
description: 瞭解設計Adobe Campaign Standard資料模型時的最佳實務。
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
source-wordcount: '1557'
ht-degree: 1%

---

# 資料模型最佳實務{#data-model-best-practices}

本檔案概述設計Adobe Campaign資料模型時的主要建議。


>[!NOTE]
>
>若要建立及修改資源以擴充Adobe Campaign預先定義的資料模型，請參閱[本節](../../developing/using/key-steps-to-add-a-resource.md)。
>
>您可以在[此頁面](../../developing/using/datamodel-introduction.md)中找到內建資源的資料模型表示法。

## 概覽 {#overview}

Adobe Campaign系統極為靈活，可延伸至初始實施以外的範圍。 不過，雖然可能性是無限的，但做出明智的決策並奠定堅實的基礎以開始設計您的資料模型是至關重要的。

本檔案提供常見使用案例和最佳實務，以瞭解如何正確架構您的Adobe Campaign工具。

## 資料模型架構 {#data-model-architecture}

Adobe Campaign Standard是功能強大的跨頻道行銷活動管理系統，可以協助您協調線上和離線策略，以建立個人化的客戶體驗。

### 以客戶為中心的方法 {#customer-centric-approach}

雖然大多數電子郵件服務提供者都是透過以清單為中心的方法與客戶通訊，但Adobe Campaign仰賴關聯式資料庫，以利用更廣大的客戶檢視及其屬性。

此以客戶為中心的方法如下圖所示。 以灰色顯示的&#x200B;**設定檔**&#x200B;資源代表正在建置所有內容的主要客戶資料表：

![](assets/customer-centric-data-model.png)

此[區段](../../developing/using/datamodel-introduction.md)中顯示Adobe Campaign預設資料模型。

<!--You can find a datamodel representation for the out-of-the-box resources [here](../../developing/using/datamodel-introduction.md).-->

<!--### What is a customer? {#customer-definition}

If you have customer data in more than one system, you need to determine which solution will allow you to identify records as one person. This work might require rules, eventually a match and merge processes to determine the primary record. This primary record should be the one sent to Adobe Campaign.

While some of this data cleansing might be performed in Adobe Campaign, the recommendation is to run these processes outside and only import clean data in Adobe Campaign. You should keep Campaign as a marketing solution more than a data cleansing tool.

Be able to provide a primary customer record which will be sent to Adobe Campaign.-->

### 適用於Adobe Campaign的資料 {#data-for-campaign}

哪些資料應該傳送至Adobe Campaign？ 決定行銷活動所需的資料至關重要。

>[!NOTE]
>
>Adobe Campaign不是Data Warehouse。 因此，請勿嘗試將所有可能的客戶及其相關資訊匯入Adobe Campaign。

若要在Adobe Campaign中決定是否需要屬性，請確定它是否屬於以下類別之一：
* 用於&#x200B;**分段**&#x200B;的屬性
* 用於&#x200B;**資料管理程式**&#x200B;的屬性（例如彙總計算）
* 用於&#x200B;**個人化**&#x200B;的屬性
* 用於&#x200B;**報告**&#x200B;的屬性（可根據自訂設定檔資料建立報告）

如果沒有上述任何專案，您很可能不需要在Adobe Campaign中使用此屬性。

### 資料類型 {#data-types}

為確保系統具備良好的架構和效能，請遵循下列最佳實務，在Adobe Campaign中設定資料：
* 字串欄位的長度一律應以欄定義。 依預設，Adobe Campaign中的長度上限為255個字元，但Adobe建議，如果您已知道大小不會超過較短的長度，請縮短欄位。
* 如果您確定來源系統中的大小被高估而無法達到，在Adobe Campaign中的欄位會比在來源系統中的欄位短，這是可以接受的。 這可能表示Adobe Campaign中的字串長度較短或整數較小。

## 設定資料結構 {#configuring-data-structure}

本節概述[設定資源的資料結構](../../developing/using/configuring-the-resource-s-data-structure.md)時的最佳實務。

### 識別碼 {#identifiers}

Adobe Campaign資源有三個識別碼，您可以新增另一個識別碼。

下表說明這些識別碼及其用途。

>[!NOTE]
>
>顯示名稱是透過Adobe Campaign使用者介面向使用者顯示的欄位名稱。 技術名稱是資源定義中的實際欄位名稱（以及表格欄名稱）。

| 顯示名稱 | 技術名稱 | 說明 | 最佳實務 |
|--- |--- |--- |--- |
|  | PKey | <ul><li>pkey是Adobe Campaign表格的實體主索引鍵。</li><li>此識別碼通常是特定Adobe Campaign執行個體的唯一識別碼。</li><li>一般使用者在Adobe Campaign Standard中看不到此值（URL除外）。</li></ul> | <ul><li>透過[API系統](../../api/using/get-started-apis.md)，可以擷取PKey值（這是產生/雜湊值，而非實體金鑰）。</li><li>不建議將其用於透過API擷取、更新或刪除記錄以外的其他任何情況。</li></ul> |
| ID | name或internalName | <ul><li>此資訊是表格中記錄的唯一識別碼。 此值可以手動更新。</li><li>部署在Adobe Campaign的其他執行個體時，此識別碼會保留其值。 其名稱必須與產生的值不同，才能透過套件匯出。</li><li>這不是表格的實際主索引鍵。</li></ul> | <ul><li>請勿使用空格「 」、分欄「： 」或連字型大小「 — 」等特殊字元。</li><li>所有這些字元都會取代為底線「_」（允許的字元）。 例如，「abc-def」和「abc：def」會儲存為「abc_def」並互相覆寫。</li></ul> |
| 標籤 | 標籤 | <ul><li>標籤是Adobe Campaign中物件或記錄的商業識別碼。</li><li>此物件允許使用空格和特殊字元。</li><li>它無法保證記錄的唯一性。</li></ul> | <ul><li>建議您決定物件標籤的結構。</li><li>這是為Adobe Campaign使用者識別記錄或物件的最好用的解決方案。</li></ul> |
| ACS ID | acsId | <ul><li>可產生額外的識別碼： [ACS ID](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources)。</li><li>由於PKey無法在Adobe Campaign使用者介面中使用，此解決方案可取得插入設定檔記錄期間產生的唯一值。</li><li>只有在記錄插入Adobe Campaign之前已在資源中啟用選項，才能自動產生值。</li></ul> | <ul><li>此UUID可作為調解金鑰使用。</li><li>自動產生的ACS ID不能用作工作流程或封裝定義中的參考。</li><li>此值專屬於Adobe Campaign執行個體。</li></ul> |

### 識別索引鍵 {#keys}

在Adobe Campaign中建立的每個資源都必須至少有一個唯一的[識別碼](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys)。

<!--Most organizations are importing records from external systems. While the physical key of a resource lies behind the PKey attribute, it is possible to determine a custom key in addition.

This custom key is the actual record primary key in the external system feeding Adobe Campaign.

When an out-of-the-box resource has both an internal auto-generated and an internal custom key, the internal key will be set as a unique index in the physical database table.-->

建立自訂資源時，您有兩個選項：

* 自動產生索引鍵和內部自訂索引鍵的組合。 如果您的系統金鑰是複合金鑰或非整數，此選項會很有趣。 整數在大表格中及與其他表格結合時，可提供更高的效能。
* 使用主鍵作為外部系統主鍵。 此解決方案通常較偏好使用，因為它會簡化匯入和匯出資料的方法，並在不同系統間使用一致的金鑰。

在工作流程中，身分識別鍵不應作為參照使用。

<!--For more on defining identification keys, see [this section](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys).-->

### 索引 {#indexes}

Adobe Campaign會自動將[索引](../../developing/using/configuring-the-resource-s-data-structure.md#defining-indexes)新增至資源中定義的所有主要和內部索引鍵。

* Adobe建議定義其他索引，因為這可以改善效能。
* 不過，請勿加入太多索引，因為它們會使用資料庫上的空間。 許多索引也可能對效能造成負面影響。
* 請仔細選取需要定義的索引。

<!--For more on defining indexes, see [this section](../../developing/using/configuring-the-resource-s-data-structure.md#defining-indexes).

When you are performing an initial import with very high volumes of data insert in Adobe Campaign database, it is recommended to run that import without custom indexes at first. It will allow to accelerate the insertion process. Once you’ve completed this important import, it is possible to enable the index(es).-->

### 連結 {#links}

定義與其他資源的連結會顯示在[本節](../../developing/using/configuring-the-resource-s-data-structure.md#defining-links-with-other-resources)中。

* 雖然可以在工作流程中聯結任何表格，但Adobe建議直接在資料結構定義中定義資源之間的通用連結。
* 連結的定義應與表格中的實際資料一致。 錯誤的定義可能會影響透過連結擷取的資料，例如意外地重複記錄。
* 使用與資源名稱一致的名稱來命名連結：連結名稱應該有助於瞭解遠端表格是什麼。
* 請勿將含有「id」的連結命名為尾碼。 例如，將其命名為「transaction」而非「transactionId」。

<!--For more on defining links with other resources, see [this section](../../developing/using/configuring-the-resource-s-data-structure.md#defining-links-with-other-resources).-->

## 績效 {#performance}

為了確保隨時提供更優異的效能，請遵循下列最佳實務。

### 一般性建議 {#general-recommendations}

* 避免在查詢中使用「CONTAINS」等操作。 如果您知道預期結果並想要篩選，請套用包含「等於」或其他特定篩選運運算元的相同條件。
* 在工作流程中建置資料時，請避免加入非索引欄位。
* 請嘗試並確保匯入和匯出等程式在工作時間進行。
* 請確定所有日常活動都有排程，並遵守排程。
* 如果有一或數個每日處理作業失敗，且必須在同一天執行，請確定啟動手動處理作業時沒有衝突處理作業在執行，因為這會影響系統效能。
* 確保在匯入程式期間或執行任何手動程式時，不會執行任何每日行銷活動。
* 使用一或多個參考表格，而不是在每一列複製欄位。 使用索引鍵/值配對時，最好選擇數字索引鍵。
* 簡短的字串仍可接受。 如果外部系統中已有參考表格，重複使用相同表格將促進與Adobe Campaign的資料整合。

### 一對多關係 {#one-to-many-relationships}

* 資料設計會影響可用性和功能。 如果您在設計資料模型時有許多一對多關係，這會讓使用者更難以在應用程式中建構有意義的邏輯。 非技術行銷人員可能很難正確建構和瞭解一對多篩選器邏輯。
* 將所有重要欄位放在一個表格中很好，因為這樣使用者更容易建立查詢。 有時候，如果可以避免聯結，跨表格複製某些欄位對效能也有好處。
* 某些內建功能無法參考一對多關係，例如「優惠加權」公式和「傳送」。

### 大型表格 {#large-tables}

以下是使用大型表格和複雜聯結設計資料模型時應遵循的一些最佳實務。

* 減少欄數，特別是識別未使用的欄。
* 藉由避免複雜的聯結（例如多個條件和/或數個欄上的聯結）來最佳化資料模型關係。
* 若是聯結鍵，請一律使用數值資料，而非字元字串。
* 儘可能減少記錄保留的深度。 如果您需要更深入的記錄，您可以彙總計算和/或處理自訂記錄表，以儲存更大的記錄。
