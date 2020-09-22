---
title: 查詢
description: 「查詢」活動可讓您從 Adobe Campaign 資料庫中篩選及擷取一組元素。
page-status-flag: never-activated
uuid: b3c629fa-370e-481c-b347-fcf9f5a5e847
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 8d46ce28-0101-4f13-865a-2208ed6d6139
context-tags: query,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: eac45f6e5491703a39c19a4787be6f285e841e14
workflow-type: tm+mt
source-wordcount: '1708'
ht-degree: 96%

---


# 查詢{#query}

## 說明 {#description}

![](assets/query.png)

**[!UICONTROL Query]** 活動可讓您從 Adobe Campaign 資料庫中篩選及擷取元素總量。您可以透過專用索引標籤來定義目標母體的　**[!UICONTROL Additional data]**。此資料會儲存在其他欄中，且僅能用於進行中的工作流程。

活動使用查詢編輯器工具。[專屬區段](../../automating/using/editing-queries.md#about-query-editor)中會詳細說明此工具。

**相關主題：**

* [查詢範例](../../automating/using/query-samples.md)
* [使用案例：重新定位傳送新傳送給非開啟者的工作流程](../../automating/using/workflow-cross-channel-retargeting.md)

## 使用內容 {#context-of-use}

**[!UICONTROL Query]** 活動可用於各種類型的使用：

* 將個人分段以定義訊息、對象等的目標。
* 擴充整個 Adobe Campaign 資料庫表格的資料。
* 匯出資料。

## 設定 {#configuration}

1. 將 **[!UICONTROL Query]** 活動拖放至工作流程中。
1. 選取活動，然後使用所顯示快速操作中的 ![](assets/edit_darkgrey-24px.png) 按鈕將其開啟。依預設，活動會預先設定為搜尋設定檔。
1. 如果要對設定檔案資源以外的資源運行查詢，請轉至活動的 **[!UICONTROL Properties]** 索引標籤，然後選取 **[!UICONTROL Resource]** 和　**[!UICONTROL Targeting dimension]**。

   **[!UICONTROL Resource]** 可讓您調整浮動視窗中顯示的篩選條件，而與所選資源相關的 **[!UICONTROL Targeting dimension]**，則與您要取得的母體類型（識別的設定檔、傳送、連結至所選資源的資料等）相對應。

   如需詳細資訊，請參閱[目標維度和資源](#targeting-dimensions-and-resources)。

1. 在 **[!UICONTROL Target]** 索引標籤，定義並結合規則以執行查詢。
1. 您可以透過專用索引標籤來定義目標母體的　**[!UICONTROL Additional data]**。此資料會儲存在其他欄中，且僅能用於進行中的工作流程。尤其是，您可以從連結至查詢目標維度的 Adobe Campaign 資料庫表格新增資料。請參閱[擴充資料](#enriching-data)區段。

   >[!NOTE]
   >
   >依預設，會在查詢的 **[!UICONTROL Additional data]** 索引標籤的 **[!UICONTROL Advanced options]** 核取 **[!UICONTROL Remove duplicate rows (DISTINCT)]** 選項。如果 **[!UICONTROL Query]** 活動包含許多（來自 100個）已定義的其他資料，則建議基於效能原因取消選中此選項。請注意，取消核取此選項會導致重複，視查詢的資料而定。

1. 在 **[!UICONTROL Transition]** 索引標籤，**[!UICONTROL Enable an outbound transition]** 選項可讓您在查詢活動後新增出站轉變，即使它未擷取任何資料亦然。

   The outbound transition&#39;s segment code can be personalized using a standard expression and events variables (see [](../../automating/using/customizing-workflow-external-parameters.md)).

1. 確認活動的設定並儲存工作流程。

## 目標維度與資源 {#targeting-dimensions-and-resources}

目標維度和資源可讓您定義查詢要依據哪些元素來判斷傳送的目標。

它們是在目 [標映射中配置](../../administration/using/target-mappings-in-campaign.md)，並在建立工作流時在「查詢」活動 **[!UICONTROL Properties]** 的頁籤中定義。

>[!NOTE]
>
>建立對象時，也可定義目標維度（請參閱[本區段](../../audiences/using/creating-audiences.md)）。

![](assets/targeting_dimension1.png)

目標維度和資源會連結。因此，可用的目標維度視選取的資源而定。

例如，對於資源　**[!UICONTROL Profiles (profile)]**，將可使用下列目標維度：

![](assets/targeting_dimension2.png)

對於　**[!UICONTROL Deliveries (delivery)]**，清單將包含下列目標維度：

![](assets/targeting_dimension3.png)

在指定目標維度和資源後，查詢中有不同篩選器可供使用。

**[!UICONTROL Profiles (profile)]**　資源的可用篩選器範例：

![](assets/targeting_dimension4.png)

**[!UICONTROL Deliveries (delivery)]**　資源的可用篩選器範例：

![](assets/targeting_dimension5.png)

預設會設定目標維度和資源，以定位設定檔。不過，如果您想在遠端表格中尋找特定記錄，則使用與目標維度不同的資源可能會很實用。

有關此功能的詳細資訊，請參閱此使用案例： [使用與定位維度不同的資源](../../automating/using/using-resources-different-from-targeting-dimensions.md)

## 擴充資料 {#enriching-data}

**[!UICONTROL Query]**、**[!UICONTROL Incremental query]** 及 **[!UICONTROL Enrichment]**　的　**[!UICONTROL Additional data]**　索引標籤可讓您擴充目標資料，並將此資料傳輸至下列工作流程活動，以便在其中使用。您尤其可以新增：

* 簡單資料
* 彙總
* 集合

對於彙總及集合，會自動定義　**[!UICONTROL Alias]**，為複雜運算式提供技術 ID。此別名必須是唯一的，可讓您在之後輕鬆地找到彙總及集合。您可以修改它，使其具有易於識別的名稱。

>[!NOTE]
>
>別名必須遵守下列語法規則：僅允許使用英數字元和 &quot;_&quot; 字元。別名區分大小寫。別名必須以　&quot;@&quot;　字元開頭。緊接在　&quot;@&quot;　後面的字元不得為數值。例如： @myAlias_1　和　@_1Alias　是正確的；而　@myAlias#1　和　@1Alias　則不正確。

新增任何其他資料後，您可以根據所定義的其他資料建立條件，將額外的篩選層級套用至最初定位的資料。

>[!NOTE]
>
>依預設，會在查詢的 **[!UICONTROL Additional data]** 索引標籤的 **[!UICONTROL Advanced options]** 核取 **[!UICONTROL Remove duplicate rows (DISTINCT)]** 選項。如果 **[!UICONTROL Query]** 活動包含許多（來自 100個）已定義的其他資料，則建議基於效能原因取消選中此選項。請注意，取消核取此選項會導致重複，視查詢的資料而定。

本節將說明如何使用其他資料個人化電子郵件的使 [用案例](../../automating/using/personalizing-email-with-additional-data.md)。

### 新增簡單欄位 {#adding-a-simple-field}

將簡單欄位新增為其他資料後，該欄位就會直接顯示在活動的對外轉變中。這可讓使用者檢查，例如，查詢中的資料是否為所需資料。

1. 從 **[!UICONTROL Additional data]** 索引標籤新增元素。
1. 在開啟的視窗中，在 **[!UICONTROL Expression]** 欄位選取目標維度中直接可用的其中一個欄位或其中一個連結的維度。您可以編輯運算式，並使用維度欄位中的函式或簡單計算（集合除外）。

   如果您編輯的運算式不是簡單的 XPATH 路徑，則會自動建立 **[!UICONTROL Alias]**（例如：&quot;Year(&lt;@birthDate>)&quot;）。您也可以修改其內容。如果您只選取一個欄位（例如：&quot;@age&quot;），您不需要定義　**[!UICONTROL Alias]**。

1. 選取 **[!UICONTROL Add]** 以確認將欄位新增到其他資料。執行查詢時，與新增的欄位對應的附加列將出現在活動的出站轉換中。

![](assets/enrichment_add_simple_field.png)

### 新增彙總 {#adding-an-aggregate}

彙總可讓您從目標維度的欄位或連結至目標維度的維度欄位計算值。例如：設定檔購買的平均金額。
使用包含查詢的彙總時，其函式可傳回零，然後視為 NULL。使用查詢 **[!UICONTROL Output filtering]** 的索引標籤來篩選彙總值：

* 如果您想要零值，則應對 **[!UICONTROL is null]** 進行篩選。
* 如果您不想要零值，請對 **[!UICONTROL is not null]** 進行開選。

請注意，如果您需要對彙總套用排序，則應篩選掉零值，否則 NULL 值將顯示為最大數。

1. 從 **[!UICONTROL Additional data]** 索引標籤新增元素。
1. 在開啟的視窗中，選取您要用來在 **[!UICONTROL Expression]** 欄位中建立彙總的集合。

   會自動建立　**[!UICONTROL Alias]**。您也可以返回查詢的 **[!UICONTROL Additional data]** 索引標籤，以修改該項目。

   將開啟彙總定義視窗。

1. 從　**[!UICONTROL Data]**　索引標籤定義彙總總。根據所選彙總的類型，**[!UICONTROL Expression]**　欄位中只有與其資料相容的元素。例如，總和只能用數值資料計算。

   ![](assets/enrichment_add_aggregate.png)

   您可以為選取之集合的欄位新增數個彙總。請務必定義明確標籤，以區分活動出站資料詳細資訊中的不同列。

   您也可以更改為每個彙總自動定義的別名。

   ![](assets/enrichment_add_aggregate2.png)

1. 如有需要，您可以新增篩選器以限制已考慮的資料。

   請參閱[篩選已新增的資料](#filtering-added-data)區段。

1. 選取 **[!UICONTROL Confirm]** 以新增彙總。

>[!NOTE]
>
>不能直接從　**[!UICONTROL New additional data]**　視窗的　**[!UICONTROL Expression]**&#x200B;欄位建立包含彙總的運算式。

### 新增集合 {#adding-a-collection}

1. 從 **[!UICONTROL Additional data]** 索引標籤新增元素。
1. 在開啟的視窗中，選取您要新增至　**[!UICONTROL Expression]**　欄位中的集合。會自動建立　**[!UICONTROL Alias]**。您也可以返回查詢的 **[!UICONTROL Additional data]** 索引標籤，以修改該項目。
1. 選取 **[!UICONTROL Add]**。隨即開啟新視窗，讓您調整想要顯示的收集資料。
1. 在 **[!UICONTROL Parameters]** 索引標籤中，選取 **[!UICONTROL Collection]** 並定義要新增的集合行數。例如，如果您想要取得每個設定檔執行的三個最近購買，請在　**[!UICONTROL Number of lines to return]**　欄位中輸入　&quot;3&quot;。

   >[!NOTE]
   >
   >您必須輸入大於或等於　1　的數字。

1. 從 **[!UICONTROL Data]** 索引標籤，定義要針對每行顯示的集合欄位。

   ![](assets/enrichment_add_collection.png)

1. 如果您喜歡，您可以新增篩選來限制已考慮的集合行。

   請參閱[篩選已新增的資料](#filtering-added-data)區段。

1. 您也可以定義資料排序。

   例如，如果您在　**[!UICONTROL Parameters]**　索引標籤中選取要傳回　3　行，並且想要確定最近的　3　個採購，則可以在與交易相對應的集合的　&quot;date&quot;　欄位中定義降序排序。

1. 請參閱[排序其他資料](#sorting-additional-data)區段。
1. 選取 **[!UICONTROL Confirm]** 以新增集合。

### 篩選新增的資料 {#filtering-added-data}

當您新增彙總或集合時，可以指定其他篩選器來限制您要顯示的資料。

例如，如果您只想處理金額為　50　美元及以上的交易的收集行，則可以在　**[!UICONTROL Filter]**　索引標籤內與交易金額相對應的欄位中新增條件。

![](assets/enrichment_filter_data.png)

### 排序其他資料 {#sorting-additional-data}

在向查詢的資料中新增彙總或集合時，可以根據欄位的值或定義的運算式指定是否要應用排序（無論排序是升序還是降序）。

例如，如果只想保存設定檔案最近執行的交易，請在　**[!UICONTROL Parameters]**　索引標籤的　**[!UICONTROL Number of lines to return]**　欄位中輸入　&quot;1&quot;，然後透過　**[!UICONTROL Sort]**　索引標籤對與交易日期相對應的欄位套用降序排序。

![](assets/enrichment_sort_data.png)

### 根據其他資料篩選目標資料 {#filtering-the-targeted-data-according-to-additional-data}

新增其他資料後，新 **[!UICONTROL Output filtering]** 索引標籤會出現在　**[!UICONTROL Query]**。此標籤可讓您針對標籤中最初定位的資料套用額外的篩選，**[!UICONTROL Target]** 方法是考量新增的資料。

例如，如果您已將執行至少一個交易的所有設定檔案定位，並且每個設定檔案的平均交易金額的彙總計算都新增到　**[!UICONTROL Additional data]**　中，則可以改善最初使用此平均值計算的母體。

要執行此操作，在 **[!UICONTROL Output filtering]** 索引標籤中，對此額外資料新增條件。

![](assets/enrichment_output_filtering2.png)

![](assets/enrichment_output_filtering.png)
