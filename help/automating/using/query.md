---
title: 查詢
description: 「查詢」活動可讓您從Adobe Campaign資料庫中篩選及擷取一組元素。
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
source-git-commit: 87e0611fae0560aca276caa3c4cf793e9c095d72
workflow-type: tm+mt
source-wordcount: '1725'
ht-degree: 0%

---


# 查詢{#query}

## 說明 {#description}

![](assets/query.png)

此活 **[!UICONTROL Query]** 動可讓您從Adobe Campaign資料庫中篩選及擷取元素總量。 您可以透過 **[!UICONTROL Additional data]** 專用標籤來定義目標人口。 此資料會儲存在其他欄中，且僅能用於進行中的工作流程。

活動使用查詢編輯器工具。 此工具在專屬章節中 [有詳細說明](../../automating/using/editing-queries.md#about-query-editor)。

**相關主題：**

* [查詢示例](../../automating/using/query-samples.md)
* [使用案例： 重新定位傳送新傳送給非開啟者的工作流程](../../automating/using/workflow-cross-channel-retargeting.md)

## 使用內容 {#context-of-use}

此活 **[!UICONTROL Query]** 動可用於各種類型的使用：

* 將個人分段以定義訊息、對象等的目標。
* 豐富整個Adobe Campaign資料庫表格的資料。
* 匯出資料.

## 配置 {#configuration}

1. 將活動拖放 **[!UICONTROL Query]** 到工作流程中。
1. 選擇活動，然後使用顯示的快 ![](assets/edit_darkgrey-24px.png) 速操作中的按鈕將其開啟。 依預設，活動會預先設定為搜尋描述檔。
1. 如果要對配置檔案資源以外的資源運行查詢，請轉至活動的頁籤， **[!UICONTROL Properties]** 然後選擇 **[!UICONTROL Resource]** 和 **[!UICONTROL Targeting dimension]**。

   您 **[!UICONTROL Resource]** 可以調整浮動視窗中顯示的篩選條件，而與所選資源相關的 **[!UICONTROL Targeting dimension]**，則與您要取得的人口類型（識別的設定檔、傳送、連結至所選資源的資料等）相對應。

   如需詳細資訊，請參閱「定 [位維度和資源」](#targeting-dimensions-and-resources)。

1. 在標籤 **[!UICONTROL Target]** 中，定義並結合規則以執行查詢。
1. 您可以透過 **[!UICONTROL Additional data]** 專用標籤來定義目標人口。 此資料會儲存在其他欄中，且僅能用於進行中的工作流程。 尤其是，您可以從連結至查詢定位維度的Adobe Campaign資料庫表格新增資料。 請參閱「 [豐富資料](#enriching-data) 」一節。

   >[!NOTE]
   >
   >預設情況下， **[!UICONTROL Remove duplicate rows (DISTINCT)]** 選項會在查 **[!UICONTROL Advanced options]** 詢的選 **[!UICONTROL Additional data]** 項卡中選中。 如果活 **[!UICONTROL Query]** 動包含許多（來自100個）已定義的其他資料，則建議基於效能原因取消選中此選項。 請注意，取消勾選此選項會導致重複，視查詢的資料而定。

1. 在標籤 **[!UICONTROL Transition]** 中，選 **[!UICONTROL Enable an outbound transition]** 項可讓您在查詢活動後新增傳出轉場，即使它未擷取任何資料亦然。

   使用標準運算式和事件變數可個人化傳出轉場的區段代碼(請參閱使用事 [件變數自訂活動](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables))。

1. 確認活動的設定並儲存工作流程。

## 定位維度與資源 {#targeting-dimensions-and-resources}

定位維度和資源可讓您定義查詢要依據哪些元素來判斷傳送的目標。

定位維度是在定位映射中定義。 如需詳細資訊，請參閱[本章節](../../administration/using/target-mappings-in-campaign.md)。

定位維度和資源是在建立工作流程時，在「查詢」活動 **[!UICONTROL Properties]** 的標籤中定義。

>[!NOTE]
>
>建立對象時，也可定義定位維度(請參 [閱本節](../../audiences/using/creating-audiences.md))。

![](assets/targeting_dimension1.png)

定位維度和資源會連結。 因此，可用的定位維度取決於選取的資源。

例如，對於「資源」, **[!UICONTROL Profiles (profile)]**&#x200B;將可使用下列定位維度：

![](assets/targeting_dimension2.png)

對於， **[!UICONTROL Deliveries (delivery)]**&#x200B;清單將包含下列定位維度：

![](assets/targeting_dimension3.png)

在指定定位維度和資源後，查詢中就可使用不同的篩選。

資源的可用篩選器示 **[!UICONTROL Profiles (profile)]** 例：

![](assets/targeting_dimension4.png)

資源的可用篩選器示 **[!UICONTROL Deliveries (delivery)]** 例：

![](assets/targeting_dimension5.png)

預設會設定定位維度和資源，以定位描述檔。 不過，如果您想在遠端表格中尋找特定記錄，則使用與定位維度不同的資源可能會很有用。

有關此功能的詳細資訊，請參閱此使用案例： [使用與定位維度不同的資源](../../automating/using/using-resources-different-from-targeting-dimensions.md)

## 豐富資料 {#enriching-data}

「和 **[!UICONTROL Additional data]** 」活 **[!UICONTROL Query]**&#x200B;動的標 **[!UICONTROL Incremental query]****[!UICONTROL Enrichment]** 簽可讓您豐富目標資料，並將此資料傳輸至下列工作流程活動，以便在其中使用。 您尤其可以新增：

* 簡單資料
* 聚合
* 系列

對於匯整和系列，會自動 **[!UICONTROL Alias]** 定義一個字元，為複雜運算式提供技術ID。 此別名必須是唯一的，可讓您在之後輕鬆找到匯總和系列。 您可以修改它，使其具有易於辨識的名稱。

>[!NOTE]
>
>別名必須遵守下列語法規則： 僅授權英數字元和&quot;_&quot;字元。 別名區分大小寫。 別名必須以&quot;@&quot;字元開頭。 緊接在&quot;@&quot;後面的字元不得為數值。 例如： @myAlias_1和@_1Alias正確； 而@myAlias#1和@1Alias則不正確。

新增任何其他資料後，您可以根據所定義的其他資料建立條件，將額外的篩選層級套用至最初定位的資料。

>[!NOTE]
>
>預設情況下， **[!UICONTROL Remove duplicate rows (DISTINCT)]** 選項會在查 **[!UICONTROL Advanced options]** 詢的選 **[!UICONTROL Additional data]** 項卡中選中。 如果活 **[!UICONTROL Query]** 動包含許多（來自100個）已定義的其他資料，則建議基於效能原因取消選中此選項。 請注意，取消勾選此選項會導致重複，視查詢的資料而定。

本節將說明如何使用其他資料個人化電子郵件的使 [用案例](../../automating/using/personalizing-email-with-additional-data.md)。

### 新增簡單欄位 {#adding-a-simple-field}

將簡單欄位新增為其他資料後，該欄位就會直接顯示在活動的對外轉場中。 這可讓使用者檢查，例如，查詢中的資料是否為所需資料。

1. 從標籤 **[!UICONTROL Additional data]** 中新增元素。
1. 在開啟的視窗中，在欄位中 **[!UICONTROL Expression]** ，選取目標維度中直接可用的其中一個欄位或其中一個連結的維度。 您可以編輯表達式，並使用維欄位中的函式或簡單計算（集合除外）。

   如果 **[!UICONTROL Alias]** 編輯的表達式不是簡單的XPATH路徑，則會自動建立一個表達式(例如： &quot;Year(&lt;@birthDate>)&quot;)。 如果您願意，可以修改它。 如果您只選取一個欄位(例如： &quot;@age&quot;)，您不需要定義 **[!UICONTROL Alias]**。

1. 選擇 **[!UICONTROL Add]** 以確認將欄位添加到其他資料。 執行查詢時，與添加的欄位對應的附加列將出現在活動的出站轉換中。

![](assets/enrichment_add_simple_field.png)

### 添加聚合 {#adding-an-aggregate}

匯總可讓您從定位維度的欄位或連結至定位維度的維度欄位計算值。 例如： 描述檔購買的平均金額。
使用帶查詢的聚合時，其函式可返回零，然後視為NULL。 使用查 **[!UICONTROL Output filtering]** 詢的標籤來篩選匯總值：

* 如果您想要零值，您應加以篩選 **[!UICONTROL is null]**。
* 的雙曲餘切值 **[!UICONTROL is not null]**。

請注意，如果您需要對匯總應用排序，則應過濾掉零值，否則NULL值將顯示為最大數。

1. 從標籤 **[!UICONTROL Additional data]** 中新增元素。
1. 在開啟的視窗中，選取您要用來在欄位中建立匯總的系 **[!UICONTROL Expression]** 列。

   系統 **[!UICONTROL Alias]** 會自動建立。 如果您喜歡，可返回查詢的頁籤修改該 **[!UICONTROL Additional data]** 選項。

   將開啟聚合定義窗口。

1. 從標籤中定義匯 **[!UICONTROL Data]** 總。 根據所選聚合的類型，欄位中只有與其資料相容的元 **[!UICONTROL Expression]** 素。 例如，總和只能用數值資料計算。

   ![](assets/enrichment_add_aggregate.png)

   您可以為選取之系列的欄位新增數個匯總。 請務必定義明確標籤，以區分活動出站資料詳細資訊中的不同列。

   您也可以更改為每個聚合自動定義的別名。

   ![](assets/enrichment_add_aggregate2.png)

1. 如有需要，您可以新增篩選器以限制已考慮的資料。

   請參閱篩選已 [新增的資料](#filtering-added-data) 區段。

1. 選擇 **[!UICONTROL Confirm]** 以添加聚合。

>[!NOTE]
>
>不能直接從窗口的欄位建立包含 **[!UICONTROL Expression]** 聚合的表達 **[!UICONTROL New additional data]** 式。

### 新增系列 {#adding-a-collection}

1. 從標籤 **[!UICONTROL Additional data]** 中新增元素。
1. 在開啟的視窗中，選取您要新增至欄位中的系列 **[!UICONTROL Expression]** 。 系統 **[!UICONTROL Alias]** 會自動建立。 如果您喜歡，可返回查詢的頁籤修改該 **[!UICONTROL Additional data]** 選項。
1. Select **[!UICONTROL Add]**. 隨即開啟新視窗，讓您調整想要顯示的收集資料。
1. 在標籤 **[!UICONTROL Parameters]** 中，選 **[!UICONTROL Collection]** 擇並定義要添加的系列行數。 例如，如果您想要取得每個描述檔執行的三個最近購買，請在欄位中輸入&quot;3&quot; **[!UICONTROL Number of lines to return]** 。

   >[!NOTE]
   >
   >您必須輸入大於或等於1的數字。

1. 在標籤 **[!UICONTROL Data]** 中，定義要針對每行顯示的系列欄位。

   ![](assets/enrichment_add_collection.png)

1. 如果您喜歡，您可以新增篩選來限制已考慮的系列行。

   請參閱篩選已 [新增的資料](#filtering-added-data) 區段。

1. 如果您喜歡，可以定義資料排序。

   例如，如果您在標籤中選擇了3行要返回，並且想要確定最近的3個採購，則可以在與事務處理對應的系列的「日期」欄位中定義降序排序。 **[!UICONTROL Parameters]**

1. 請參閱「排 [序其他資料](#sorting-additional-data) 」一節。
1. 選取 **[!UICONTROL Confirm]** 以新增系列。

### 篩選新增的資料 {#filtering-added-data}

當您新增匯總或系列時，可以指定其他篩選器來限制您要顯示的資料。

例如，如果您只想處理金額為50美元及以上的事務處理的收集行，則可以在標籤中與事務處理金額對應的欄位中添加條 **[!UICONTROL Filter]** 件。

![](assets/enrichment_filter_data.png)

### 排序其他資料 {#sorting-additional-data}

在向查詢的資料中添加聚合或集合時，可以根據欄位的值或定義的表達式指定是否要應用排序（無論排序是升序還是降序）。

例如，如果只想保存配置檔案最近執行的事務，請在標籤的欄位中輸入&quot;1&quot;，然後通過標籤對與事務日期對應的欄位應用降序 **[!UICONTROL Number of lines to return]****[!UICONTROL Parameters]****[!UICONTROL Sort]** 排序。

![](assets/enrichment_sort_data.png)

### 根據其他資料篩選目標資料 {#filtering-the-targeted-data-according-to-additional-data}

新增其他資料後，新標籤 **[!UICONTROL Output filtering]** 會出現在 **[!UICONTROL Query]**。 此標籤可讓您針對標籤中最初定位的資料套用額外的篩選， **[!UICONTROL Target]** 方法是考量新增的資料。

例如，如果您已將執行至少一個事務處理的所有配置檔案定位，並且每個配置檔案的平均事務處理金額的匯總計算都添加到中 **[!UICONTROL Additional data]**，則可以細化最初使用此平均值計算的人口。

若要這麼做，請在標 **[!UICONTROL Output filtering]** 簽中，在此額外資料上新增條件。

![](assets/enrichment_output_filtering2.png)

![](assets/enrichment_output_filtering.png)
