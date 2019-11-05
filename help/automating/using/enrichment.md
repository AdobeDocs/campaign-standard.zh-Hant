---
title: 擴充
description: 「擴充」活動是進階活動，可讓您定義要在工作流程中處理的其他資料。
page-status-flag: 從未激活
uuid: 8c1693ef-1312-422c-b05d-263553113f8f
contentOwner: 紹維亞
products: SG_CAMPAIGN/STANDARD
audience: 自動化
content-type: 參考
topic-tags: 定位活動
discoiquuid: f67c1caf-3284-4c34-a5b0-8654a95640ae
context-tags: 富集，主
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 擴充{#enrichment}

## 說明 {#description}

![](assets/enrichment.png)

活 **[!UICONTROL Enrichment]** 動是進階活動，可讓您定義要在工作流程中處理的其他資料。

## 使用內容 {#context-of-use}

活動 **[!UICONTROL Enrichment]** 通常用於定位活動後或匯入檔案後，以及允許使用定位資料之活動前。

此活動包含比活動更高級的富集函 **[!UICONTROL Query]** 數。 某些簡單的擴充案例可直接在查詢活動 [中執行](../../automating/using/query.md#enriching-data)。

使用活 **[!UICONTROL Enrichment]** 動時，您可以利用傳入的轉場，並設定活動以使用其他資料完成輸出轉場。 它可結合來自多組資料，或建立臨時資源的連結。

## 配置 {#configuration}

要配置活 **[!UICONTROL Enrichment]** 動：

1. 將活動拖放 **[!UICONTROL Enrichment]** 至工作流程。
1. 選擇活動，然後使用顯示的快 ![](assets/edit_darkgrey-24px.png) 速操作中的按鈕將其開啟。
1. 如果活動有數個傳入轉場，請選取 **[!UICONTROL Primary set]**。 此活動中配置的其他資料將添加到出站轉換中的此主集。

   如果主集已包含其他資料，您可以選擇保留或刪除這些資料。 如果取消選中該 **[!UICONTROL Keep all additional data from the main set]** 選項，則只有在中配置的其 **[!UICONTROL Enrichment]** 他資料會保留在出站過渡中。

1. 如果有數個傳入轉場，請在活動的標籤中定義主要集與其他傳入資料 **[!UICONTROL Advanced Relations]** 之間的關係。 您可以使用按鈕添加多個關 **[!UICONTROL Add element]** 系。

   定義新關係時，選擇要連結到主集的入站資料集。 然後定義關係類型。 根據傳入的資料和您的資料模型，可使用數種關係：

   * **[!UICONTROL 1 cardinality simple link]**:每個傳入資料的記錄都與來自主集的一個且僅一個記錄相關聯。 來自主集的每個記錄在連結資料中具有一個關聯記錄。
   * **[!UICONTROL N cardinality collection link]**:來自連結資料的0、1或更多(N)記錄可以關聯到主集的1個記錄。
   * **[!UICONTROL 0 or 1 cardinality simple link]**:來自主集的記錄可以與來自連結資料的0或1個記錄關聯，但不能與多個記錄關聯。
   定義 **[!UICONTROL Cardinality]** 後，定義 **[!UICONTROL Reconciliation criteria]**。 協 **[!UICONTROL Source expression]** 調標準可以是目標資源中的欄位、表達 [式](../../automating/using/advanced-expression-editing.md) ，或直接是引號之間指定的值。

   定義 **[!UICONTROL Label]** 和 **[!UICONTROL ID]** 在稍後工作流程中易於識別。

   >[!NOTE]
   >
   >您只能定義主集和連接到活動的其它入站過渡之間的關 **[!UICONTROL Enrichment]** 系。 對於旨在定義與資料庫資源關係的簡單案例，請使用「協調 [」活動](../../automating/using/reconciliation.md) 。

1. 從活動的標籤中定 **[!UICONTROL Additional data]** 義其他資料。 您可以定義與主要集的目標維度相關的其他資料（簡單欄位、匯總和系列），或根據在活動標籤中建立 **[!UICONTROL Advanced relations]** 的連結 **[!UICONTROL Enrichment]** 定義。

   請參閱「 [豐富資料](../../automating/using/query.md#enriching-data) 」一節。

1. 確認活動的設定並儲存工作流程。

現在，資料可用於在之後連接的活動中 **[!UICONTROL Enrichment]**。 例如，您可以在電子郵件內容中 **[!UICONTROL Additional data (targetData)]** 個人化欄位檔案總管的連結下找到它。

## 範例：使用檔案中包含的資料豐富描述檔資料 {#example--enriching-profile-data-with-data-contained-in-a-file}

此範例說明如何以檔案中包含的購買資料豐富描述檔資料。 我們認為購買資料儲存在協力廠商系統中。 每個描述檔都可儲存數個購買項目。 工作流程的最終目標是傳送電子郵件給已購買至少兩個項目的目標設定檔，以感謝他們的忠誠度。

工作流配置如下：

![](assets/enrichment_example_workflow.png)

* 定 **[!UICONTROL Query]** 位將接收訊息的設定檔的活動。
* 載 **[!UICONTROL Load file]** 入購買資料的活動。 例如：

   ```
   tcode;tdate;customer;product;tamount
   aze123;21/05/2017;dannymars@example.com;TV;799
   aze124;28/05/2017;dannymars@example.com;Headphones;8
   aze125;31/07/2017;john.smith@example.com;Headphones;8
   aze126;14/12/2017;john.smith@example.com;Plastic Cover;4
   aze127;02/01/2018;dannymars@example.com;Case Cover;79
   aze128;04/03/2017;clara.smith@example.com;Phone;149
   ```

   在此示例檔案中，我們將使用電子郵件地址來協調資料與資料庫配置檔案。 您也可以如本檔案所述啟用唯 [一ID](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources)。

* 在從 **[!UICONTROL Enrichment]** 檔案載入的事務處理資料與在中選擇的配置檔案之間建立連結的活動 **[!UICONTROL Query]**。 該連結在活動的標 **[!UICONTROL Advanced relations]** 簽中定義。 連結以活動產生的轉場為 **[!UICONTROL Load file]** 基礎。 它使用配置檔案資源的「電子郵件」欄位和導入檔案的「客戶」列作為協調標準。

   ![](assets/enrichment_example_workflow2.png)

   建立連結後，會新增兩組 **[!UICONTROL Additional data]** 連結：

   * 兩個行的集合，這些行對應於每個配置檔案的最後兩個事務處理。 對於此系列，產品名稱、交易日期和產品價格會新增為其他資料。 對資料套用遞減排序。 若要建立系列，請從標籤 **[!UICONTROL Additional data]** 中：

      選擇先前在活動標籤中定 **[!UICONTROL Advanced relations]** 義的連結。

      ![](assets/enrichment_example_workflow3.png)

      檢 **[!UICONTROL Collection]** 查並指定要檢索的行數（本例中為2）。 在此畫面中，您可以自 **[!UICONTROL Alias]** 訂系列 **[!UICONTROL Label]** 和系列。 這些值將在參考此系列時，顯示在工作流程的下列活動中。

      ![](assets/enrichment_example_workflow4.png)

      若要 **[!UICONTROL Data]** 保留系列，請選取要用於最終傳送的欄。

      ![](assets/enrichment_example_workflow6.png)

      對事務日期應用降序排序，以確保檢索最新事務。

      ![](assets/enrichment_example_workflow7.png)

   * 匯總計算每個配置檔案的事務處理總數。 此匯總稍後將用於篩選至少記錄了兩個交易的描述檔。 要建立聚合，請從頁籤 **[!UICONTROL Additional data]** 中：

      選擇先前在活動標籤中定 **[!UICONTROL Advanced relations]** 義的連結。

      ![](assets/enrichment_example_workflow3.png)

      Select **[!UICONTROL Aggregate]**.

      ![](assets/enrichment_example_workflow8.png)

      要保 **[!UICONTROL Data]** 留，請定義「全 **部計數** 」匯總。 如果您需要，請指定自訂別名，以便在下列活動中更快找到別名。

      ![](assets/enrichment_example_workflow9.png)

* 只 **[!UICONTROL Segmentation]** 有一個區段的活動，可擷取至少記錄了兩個交易之初始目標的描述檔。 僅包含一個事務的配置檔案將被排除。 為此，區段的查詢是在先前定義的匯總上進行。

   ![](assets/enrichment_example_workflow5.png)

* 使用 **[!UICONTROL Email delivery]** 中定義的其他資料動態擷取描述 **[!UICONTROL Enrichment]** 檔最後兩次購買的活動。 新增個人化欄位時，可在「其 **他資料(TargetData)」節點中找到其他資料** 。

   ![](assets/enrichment_example_workflow10.png)

**相關主題：**

* [利用外部資料豐富客戶個人檔案](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Managedatatofuelengagingexperiences)

