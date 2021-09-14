---
title: Adobe Campaign Standard中的資料模型最佳實務
description: 了解設計Adobe Campaign Standard資料模型時的最佳實務。
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

本檔案概述設計Adobe Campaign資料模型時的主要建議。


>[!NOTE]
>
>若要建立和修改資源以擴充Adobe Campaign預先定義的資料模型，請參閱[此區段](../../developing/using/key-steps-to-add-a-resource.md)。
>
>您可以在[此頁面](../../developing/using/datamodel-introduction.md)中找到內建資源的資料模型表示法。

## 概覽 {#overview}

Adobe Campaign系統極具彈性，可擴充至初次實作以外。 不過，雖然可能性是無限的，但做出明智的決策並建立堅實的基礎，才能開始設計您的資料模型，這一點至關重要。

本檔案提供常見使用案例和最佳實務，協助您了解如何正確架構Adobe Campaign工具。

## 資料模型架構 {#data-model-architecture}

Adobe Campaign Standard是功能強大的跨頻道行銷活動管理系統，可協助您協調線上和離線策略，以建立個人化的客戶體驗。

### 以客戶為中心的方法 {#customer-centric-approach}

雖然大部分的電子郵件服務提供者都透過清單導向方法與客戶通訊，但Adobe Campaign需仰賴關係資料庫，才能運用客戶及其屬性的更廣泛檢視。

下圖顯示以客戶為中心的方法。 以灰色顯示的&#x200B;**設定檔**&#x200B;資源代表正在建置所有內容的主要客戶表格：

![](assets/customer-centric-data-model.png)

Adobe Campaign預設資料模型顯示在此[節](../../developing/using/datamodel-introduction.md)中。

<!--You can find a datamodel representation for the out-of-the-box resources [here](../../developing/using/datamodel-introduction.md).-->

<!--### What is a customer? {#customer-definition}

If you have customer data in more than one system, you need to determine which solution will allow you to identify records as one person. This work might require rules, eventually a match and merge processes to determine the primary record. This primary record should be the one sent to Adobe Campaign.

While some of this data cleansing might be performed in Adobe Campaign, the recommendation is to run these processes outside and only import clean data in Adobe Campaign. You should keep Campaign as a marketing solution more than a data cleansing tool.

Be able to provide a primary customer record which will be sent to Adobe Campaign.-->

### Adobe Campaign的資料 {#data-for-campaign}

哪些資料應傳送至Adobe Campaign? 判斷行銷活動所需的資料至關重要。

>[!NOTE]
>
>Adobe Campaign不是資料倉庫。 因此，請勿嘗試將所有可能的客戶及其相關資訊匯入Adobe Campaign。

要決定是否需要某個屬性(在Adobe Campaign)，請確定該屬性是否屬於以下類別之一：
* 用於&#x200B;**segmentation**&#x200B;的屬性
* 用於&#x200B;**資料管理進程**&#x200B;的屬性（例如聚合計算）
* 用於&#x200B;**個人化**&#x200B;的屬性
* 用於&#x200B;**reporting**&#x200B;的屬性（可以根據自訂設定檔資料建立報表）

若未落入其中任何一個，您很可能在Adobe Campaign中不需要此屬性。

### 資料類型 {#data-types}

若要確保系統的良好架構和效能，請遵循下列最佳實務，在Adobe Campaign中設定資料：
* 字串欄位的長度應一律以欄定義。 依預設，Adobe Campaign中的最大長度為255個字元，但如果您已知道大小不會超過較短的長度，Adobe建議將欄位保持在較短的長度。
* 如果您確定源系統中的欄位被高估且無法達到，則可以接受在Adobe Campaign中的欄位比在源系統中的欄位短。 這可能表示Adobe Campaign中字串較短或整數較小。

## 配置資料結構 {#configuring-data-structure}

本節概述[配置資源的資料結構](../../developing/using/configuring-the-resource-s-data-structure.md)時的最佳做法。

### 識別碼 {#identifiers}

Adobe Campaign資源有三個識別碼，且可以新增其他識別碼。

下表說明這些識別碼及其用途。

>[!NOTE]
>
>顯示名稱是透過Adobe Campaign使用者介面向使用者顯示的欄位名稱。 技術名稱是資源定義中的實際欄位名稱（和表列名稱）。

| 顯示名稱 | 技術名稱 | 說明 | 最佳實務 |
|--- |--- |--- |--- |
|  | PKey | <ul><li>PKey是Adobe Campaign表的物理主鍵。</li><li>此識別碼通常對特定Adobe Campaign例項不重複。</li><li>在Adobe Campaign Standard中，此值不會顯示給一般使用者（URL除外）。</li></ul> | <ul><li>通過[API系統](../../api/using/get-started-apis.md)，可以檢索PKey值（該值是生成的/雜湊的值，而不是物理密鑰）。</li><li>除了透過API擷取、更新或刪除記錄外，不建議將其用於其他任何項目。</li></ul> |
| ID | name或internalName | <ul><li>此資訊是表中記錄的唯一標識符。 此值可手動更新。</li><li>此識別碼會在部署至不同的Adobe Campaign例項時保留其值。 其名稱必須與產生的值不同，才能透過套件匯出。</li><li>這不是表的實際主鍵。</li></ul> | <ul><li>請勿使用特殊字元，例如空格&quot; &quot;、半欄&quot;:&quot;或連字型大小&quot;-&quot;。</li><li>所有這些字元都將替換為底線「_」（允許的字元）。 例如，「abc-def」和「abc:def」會儲存為「abc_def」並互相覆寫。</li></ul> |
| 標籤 | label | <ul><li>標籤是Adobe Campaign中物件或記錄的業務識別碼。</li><li>此對象允許空格和特殊字元。</li><li>它不能保證記錄的獨特性。</li></ul> | <ul><li>建議您判斷物件標籤的結構。</li><li>這是最方便使用者為Adobe Campaign使用者識別記錄或物件的解決方案。</li></ul> |
| ACS ID | acsId | <ul><li>可產生其他識別碼：[ACS ID](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources)。</li><li>由於PKey無法在Adobe Campaign使用者介面中使用，因此此解決方案可取得插入設定檔記錄期間產生的唯一值。</li><li>只有在資源中啟用選項後，記錄插入Adobe Campaign中之前，才能自動產生值。</li></ul> | <ul><li>此UUID可作為調解金鑰。</li><li>自動生成的ACS ID不能用作工作流或包定義中的引用。</li><li>此值是Adobe Campaign例項專屬的值。</li></ul> |

### 識別鍵 {#keys}

在Adobe Campaign中建立的每個資源必須至少有一個唯一的[標識鍵](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys)。

<!--Most organizations are importing records from external systems. While the physical key of a resource lies behind the PKey attribute, it is possible to determine a custom key in addition.

This custom key is the actual record primary key in the external system feeding Adobe Campaign.

When an out-of-the-box resource has both an internal auto-generated and an internal custom key, the internal key will be set as a unique index in the physical database table.-->

建立自訂資源時，有兩個選項：

* 自動產生金鑰和內部自訂金鑰的組合。 如果您的系統密鑰是複合密鑰或不是整數，則此選項很有趣。 整數在大表中提供更高的效能，並與其他表連接。
* 使用主鍵作為外部系統主鍵。 此解決方案通常較為理想，因為它簡化了資料匯入和匯出的方法，且在不同系統之間具有一致的鍵值。

在工作流程中，身分識別索引鍵不應作為參考使用。

<!--For more on defining identification keys, see [this section](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys).-->

### 索引 {#indexes}

Adobe Campaign會自動將[index](../../developing/using/configuring-the-resource-s-data-structure.md#defining-indexes)新增至資源中定義的所有主要和內部索引鍵。

* Adobe建議定義其他索引，因為這可能改善效能。
* 但是，請勿添加太多索引，因為它們在資料庫上使用空間。 許多索引也可能對效能產生負面影響。
* 請謹慎選取需要定義的索引。

<!--For more on defining indexes, see [this section](../../developing/using/configuring-the-resource-s-data-structure.md#defining-indexes).

When you are performing an initial import with very high volumes of data insert in Adobe Campaign database, it is recommended to run that import without custom indexes at first. It will allow to accelerate the insertion process. Once you’ve completed this important import, it is possible to enable the index(es).-->

### 連結 {#links}

在[此部分](../../developing/using/configuring-the-resource-s-data-structure.md#defining-links-with-other-resources)中定義與其他資源的連結。

* 雖然可以在工作流中連接任何表，但Adobe建議直接在資料結構定義中定義資源之間的公用連結。
* 連結的定義應與表格中的實際資料一致。 錯誤的定義可能會影響透過連結擷取的資料，例如意外重複記錄。
* 以資源名稱一致地為連結命名：連結名稱應有助於了解遠距表格的內容。
* 請勿將連結命名為尾碼為「id」。 例如，將其命名為「transaction」，而非「transactionId」。

<!--For more on defining links with other resources, see [this section](../../developing/using/configuring-the-resource-s-data-structure.md#defining-links-with-other-resources).-->

## 效能 {#performance}

為了隨時確保效能更佳，請遵循下列最佳實務。

### 一般性建議 {#general-recommendations}

* 避免在查詢中使用「CONTAINS」等操作。 如果您知道需要什麼並且想要篩選，請使用「等於」或其他特定篩選運算子套用相同條件。
* 在工作流程中建立資料時，請避免加入非索引欄位。
* 請嘗試確保在工作時間完成匯入和匯出等程式。
* 請確定所有每日活動都有排程並遵守排程。
* 如果日常進程中的一個或幾個失敗，並且如果強制在同一天運行該進程，請確保在啟動手動進程時沒有運行衝突進程，因為這可能影響系統效能。
* 請確定在匯入程式期間或執行任何手動程式期間，沒有執行任何每日促銷活動。
* 使用一個或多個引用表，而不是在每行中重複一個欄位。 使用索引鍵/值組時，最好選擇數值索引鍵。
* 短字串仍可接受。 如果外部系統中已有參考表格，則重複使用這些表格將有助於與Adobe Campaign的資料整合。

### 一對多關係 {#one-to-many-relationships}

* 資料設計會影響可用性和功能。 如果您設計的資料模型具有許多一對多關係，則會讓使用者更難在應用程式中建構有意義的邏輯。 非技術行銷人員可能難以正確建構及了解一對多篩選邏輯。
* 將所有必要欄位放在一個表格中是件好事，因為這可讓使用者更輕鬆地建立查詢。 有時，如果可以避免加入，則跨表複製某些欄位對效能也有好處。
* 某些內建功能將無法參考一對多關係，例如選件加權公式和傳送。

### 大表 {#large-tables}

以下是使用大型表和複雜聯接設計資料模型時應遵循的一些最佳做法。

* 減少欄數，尤其是識別未使用的欄數。
* 通過避免複雜的聯接（例如在多個條件和/或多個列上的聯接）來優化資料模型關係。
* 對於聯接鍵，請始終使用數字資料，而不是字元字串。
* 盡量減少記錄保留的深度。 如果您需要更深入的歷史記錄，則可以匯總計算和/或處理自定義日誌表以儲存較大的歷史記錄。
