---
title: 豐富型
seo-title: 豐富型
description: 豐富型
seo-description: 「Rich」活動是進階活動，可讓您定義工作流程中的其他資料。
page-status-flag: 從未啓動
uuid: 8c1693ef-1312-422c-b05 d-263555113f8 f
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: reference
topic-tags: 定位活動
discoiquuid: f67c1caf-3284-4c34-a5 b0-8654a95640 ae
context-tags: 擴充，主要
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 782a5f89b0361f1cbe59c9b353ca90dec90c3906

---


# 豐富型{#enrichment}

## 說明 {#description}

![](assets/enrichment.png)

**[!UICONTROL Enrichment]** 活動是進階活動，可讓您定義工作流程中的其他資料。

## 使用內容 {#context-of-use}

**[!UICONTROL Enrichment]** 活動通常用於定位活動或匯入檔案之後，在允許使用目標資料的活動之前。

此活動包含比 **[!UICONTROL Query]** 活動更進階的擴充功能。有些簡單的擴充案例可直接在 [查詢活動](../../automating/using/query.md#enriching-data)中執行。

透過 **[!UICONTROL Enrichment]** 活動，您可以運用傳入的轉變，並設定活動，以額外資料完成輸出轉場。它可結合來自多個集合的資料，或建立暫存資源的連結。

## 組態配置 {#configuration}

若要設定 **[!UICONTROL Enrichment]** 活動：

1. 將 **[!UICONTROL Enrichment]** 活動拖放至工作流程中。
1. 選取活動，然後使用顯示的快速動作 ![](assets/edit_darkgrey-24px.png) 按鈕將其開啓。
1. 如果活動有幾個傳入的轉場效果，請選取 **[!UICONTROL Primary set]**。在此活動中設定的其他資料將會新增至對外轉場中的這個主要集。

   如果主要集已包含其他資料，您可以選擇保留或移除這些資料。如果您取消勾選 **[!UICONTROL Keep all additional data from the main set]** 選項，只有已設定的額外資料 **[!UICONTROL Enrichment]** 會保留在對外轉換中。

1. 如果有幾個傳入的轉場效果，請在活動 **[!UICONTROL Advanced Relations]** 標籤中定義主要集和其他傳入資料之間的關係。您可以使用 **[!UICONTROL Add element]** 按鈕新增數個關係。

   定義新關係時，選取您要連結至主要集的傳入資料集。然後定義關係類型。有幾種關係類型可供使用，視傳入的資料和您的資料模型而定：

   * **[!UICONTROL 1 cardinality simple link]**：傳入資料的每個記錄會關聯到一個，而一個記錄只會從主要集合中記錄。主要集中的每個記錄都有連結資料中的一個相關記錄。
   * **[!UICONTROL N cardinality collection link]**：連結資料中的0、或以上(N)記錄可關聯至主要設定的記錄。
   * **[!UICONTROL 0 or 1 cardinality simple link]**：來自主要集的記錄可與連結資料(但不限於多個)關聯。
   定義 **[!UICONTROL Cardinality]** 好之後，定義 **[!UICONTROL Reconciliation criteria]**&#x200B;一個。協調標準可以 **[!UICONTROL Source expression]** 是目標資源、 [運算式或](../../automating/using/advanced-expression-editing.md) 直接在引號之間指定的值的欄位。

   定義稍後 **[!UICONTROL Label]****[!UICONTROL ID]** 在工作流程中很容易識別的項目。

   >[!NOTE]
   >
   >您只能定義主要集與其他與 **[!UICONTROL Enrichment]** 活動連結的傳入轉場之間的關係。對於更簡單的案例來定義與資料庫資源的關係，請使用 [「調解](../../automating/using/reconciliation.md) 」活動。

1. 從活動 **[!UICONTROL Additional data]** 的標籤中定義其他資料。您可以定義與主要集定位維度相關的其他資料(簡單欄位、組合和系列)，或根據活動 **[!UICONTROL Advanced relations]** 標籤中建立的連結 **[!UICONTROL Enrichment]** 。

   請參閱 [豐富資料](../../automating/using/query.md#enriching-data) 區段。

1. 確認活動的設定並儲存工作流程。

資料現在可用於之後連接的活動中 **[!UICONTROL Enrichment]**。例如，您可以在電子郵件內容中的個人化欄位瀏覽器 **[!UICONTROL Additional data (targetData)]** 連結下找到它。

## 範例：豐富描述檔資料與檔案中包含的資料 {#example--enriching-profile-data-with-data-contained-in-a-file}

此範例說明如何使用檔案包含的購買資料充實個人檔案資料。我們認為購買資料儲存在第三方系統中。每個描述檔都可以儲存在檔案中的數個購買項目。工作流程的最終目標是傳送電子郵件給至少購買兩個項目的目標設定檔，以感謝他們的忠誠度。

工作流程的設定如下：

![](assets/enrichment_example_workflow.png)

* 針對將接收訊息之個人檔案的 **[!UICONTROL Query]** 活動。
* 載入購買資料的 **[!UICONTROL Load file]** 活動。例如：

   ```
   tcode;tdate;customer;product;tamount
   aze123;21/05/2017;dannymars@example.com;TV;799
   aze124;28/05/2017;dannymars@example.com;Headphones;8
   aze125;31/07/2017;john.smith@example.com;Headphones;8
   aze126;14/12/2017;john.smith@example.com;Plastic Cover;4
   aze127;02/01/2018;dannymars@example.com;Case Cover;79
   aze128;04/03/2017;clara.smith@example.com;Phone;149
   ```

   透過此範例檔案，我們將使用電子郵件地址將資料與資料庫設定檔協調。您也可以依照本文件 [](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources)所述啓用唯一ID。

* **[!UICONTROL Enrichment]** 在從檔案載入的交易資料與在中選取的描述檔之間建立連結的活動 **[!UICONTROL Query]**。連結會定義在活動 **[!UICONTROL Advanced relations]** 的索引標籤中。連結是根據 **[!UICONTROL Load file]** 來自活動的轉場而定。它會使用描述檔資源的「電子郵件」欄位和匯入檔案的「客戶」欄做為協調標準。

   ![](assets/enrichment_example_workflow2.png)

   建立連結後，會新增 **[!UICONTROL Additional data]** 兩組：

   * 對應每個描述檔的兩個最後一個交易之兩行的集合。對於此系列，產品名稱、交易日期和產品價格會新增為其他資料。遞減排序會套用至資料。若要從 **[!UICONTROL Additional data]** 標籤建立系列：

      選取先前在活動 **[!UICONTROL Advanced relations]** 標籤中定義的連結。

      ![](assets/enrichment_example_workflow3.png)

      勾選 **[!UICONTROL Collection]** 並指定要擷取的行數(在此範例中為2)。在此畫面中，您可以自訂 **[!UICONTROL Alias]** 系列 **[!UICONTROL Label]** 和系列。參照此系列時，這些值會顯示在工作流程的下列活動中。

      ![](assets/enrichment_example_workflow4.png)

      至於 **[!UICONTROL Data]** 保留系列，請選取最終傳送中將使用的欄。

      ![](assets/enrichment_example_workflow6.png)

      在交易日期上套用遞減排序，以確定擷取最新交易。

      ![](assets/enrichment_example_workflow7.png)

   * 匯總計算每個描述檔的交易總數。稍後將使用此匯總，篩選至少記錄兩筆交易的描述檔。若要建立匯總，請從 **[!UICONTROL Additional data]** 標籤中：

      選取先前在活動 **[!UICONTROL Advanced relations]** 標籤中定義的連結。

      ![](assets/enrichment_example_workflow3.png)

      選取 **[!UICONTROL Aggregate]**。

      ![](assets/enrichment_example_workflow8.png)

      如 **[!UICONTROL Data]** 要保持，請定義 **「全部匯總」** 匯總。如果您需要，請指定自訂別名，以在下列活動中快速找到它。

      ![](assets/enrichment_example_workflow9.png)

* **[!UICONTROL Segmentation]** 僅含一個區段的活動，擷取至少記錄兩筆交易的初始目標設定檔。只排除一筆交易的描述檔。若要這麼做，區段的查詢是在先前定義的匯總上進行。

   ![](assets/enrichment_example_workflow5.png)

* **[!UICONTROL Email delivery]** 使用中定義的其他資料來動態 **[!UICONTROL Enrichment]** 擷取由描述檔進行之兩次購買的活動。新增個人化欄位時，可在 **其他資料(targetData)** 節點中找到其他資料。

   ![](assets/enrichment_example_workflow10.png)

**相關主題：**

* [運用外部資料豐富客戶個人檔案](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Managedatatofuelengagingexperiences)

