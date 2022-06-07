---
title: 分段
description: 「分段」活動可讓您從工作流程中先前放置的活動計算的母體中建立一或多個分段。
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: segmentation,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 3761ee4a-1ce5-4f9e-b2a5-84388b6b9db8
source-git-commit: 7767b39a48502f97e2b3af9d21a3f49b9283ab2e
workflow-type: tm+mt
source-wordcount: '878'
ht-degree: 82%

---

# 細分{#segmentation}

## 說明 {#description}

![](assets/segmentation.png)

**[!UICONTROL Segmentation]** 活動可讓您從工作流程中先前放置之活動計算的母體中建立一或多個分段。在活動結束時，可以在單一轉變或不同轉變中處理這些轉變。

>[!NOTE]
>
>依預設，入站母體的成員只能屬於單一分段。篩選會根據活動中分段的順序套用。

**相關主題：**
* [用例：位置分割](../../automating/using/workflow-segmentation-location.md)
* [用例：按年齡組分割](../../automating/using/segmentation-age-groups.md)

## 使用內容 {#context-of-use}

一般而言，**[!UICONTROL Segmentation]** 活動會放置在目標定位活動（查詢、交叉點、聯合、排除等）之後，以便依據要形成的區段來定義標準母體。

**相關主題**

* [用例：根據年齡組分段個人資料](../../automating/using/segmentation-age-groups.md)。

## 設定 {#configuration}

1. 將 **[!UICONTROL Segmentation]** 活動拖放至工作流程中。
1. 選取活動，然後使用所顯示快速操作中的 ![](assets/edit_darkgrey-24px.png) 按鈕將其開啟。
1. 在 **[!UICONTROL General]** 頁籤 **[!UICONTROL Resource type]** 其中必須進行分割：

   * **[!UICONTROL Database resource]** 如果對資料庫中已存在的資料執行分段。根據您要分段的資料選取 **[!UICONTROL Filtering dimension]**。依預設，會對&#x200B;**設定檔**&#x200B;執行分段。
   * **[!UICONTROL Temporary resource]** 如果對工作流的臨時資料執行分段：選取包含要分段資料的 **[!UICONTROL Targeted set]**。在匯入檔案或資料庫中的資料已變得充實之後，可以使用此使用案例。

1. 選取要使用的出站轉變類型：

   * **[!UICONTROL Generate one transition per segment]**：在活動結束時，會為每個已設定的分段新增一個出站轉變。
   * **[!UICONTROL Generate all segments in one transition]**：所有已設定的分段都會重新分組為單一入站轉變。指定轉變標籤。每個分段的成員會保留已指派給它們的分段代碼。

1. 使用 ![](assets/add_darkgrey-24px.png) 或 **[!UICONTROL Add an element]** 按鈕新增區段並指定標準屬性：

   * **[!UICONTROL Do not activate the transition if the population is empty]**：只有在擷取資料時，才會啟用分段。
   * **[!UICONTROL Filter initial population (query)]**：可讓您篩選此分段的母體。
   * **[!UICONTROL Limit segment population]**：可讓您限制分段大小。
   * **[!UICONTROL Filter and limit segment population]**：可讓您篩選群體母體並限制其大小。
   * **[!UICONTROL Label]**：分段標籤。
   * **[!UICONTROL Segment code]**:分配給段填充的代碼。可使用標準表達式和事件變數個性化段代碼(請參閱 [此頁](../../automating/using/customizing-workflow-external-parameters.md))。
   * **[!UICONTROL Exclude segment from population]**：可讓您從活動的對外母體中排除指定的分段。只有在選取選項時，才能使用　**[!UICONTROL Generate all segments in the same transition]**　選項。

   ![](assets/wkf_segment_new_segment.png)

1. 開啟分段的詳細資料檢視，以存取後者的設定選項。要執行此操作，請核取活動分段清單中的相關方塊，然後選取 ![](assets/wkf_segment_parameters_24px.png)。
1. 如果已核取篩選初始母體族群的選項，請開啟 **[!UICONTROL Filter]** 索引標籤並指定分段的母體族群。這些篩選條件是以步驟　4　中選取的篩選維度為基礎。如需母體篩選的進一步資訊，請諮詢[查詢編輯](../../automating/using/editing-queries.md)區段。

   如果對暫時資源執行分段，此索引標籤無法使用母體的計數及預覽。

1. 如果已核取限制分段大小的選項，請開啟　**[!UICONTROL Limitation]** 索引標籤。

   首先，選取您要使用 **[!UICONTROL Type of limit]**：

   * **[!UICONTROL Random sampling]**：如有需要，考量　**[!UICONTROL Filter]**　索引標籤的設定時，會隨機選取區段母體。
   * **[!UICONTROL Ordered sampling]**：分段母體是依順序選取。因此，必須指定要考慮的欄以及要套用的排序類型。例如，如果您在套用　**[!UICONTROL Descending sort]**　並設定　100 的限制時，選取&#x200B;**年齡**&#x200B;欄位作為排序欄時，則只會保留 100 個最年長人員的設定檔。

   現在指定區段的大小 **[!UICONTROL Limit]**：

   * **[!UICONTROL Size (as a % of the initial population)]**：使用活動初始母體百分比來指定區段大小。
   * **[!UICONTROL Maximum size]**：指定區段母體的成員數上限。
   * **[!UICONTROL By data grouping]**：您可以根據入站母體的特定欄位值來限制區段母體。選取要分組的欄位，然後指定要使用的值。
   * **[!UICONTROL By data grouping (as a %)]**：您可以使用百分比，根據特定入站母體欄位的值來限制區段母體。選取要套用分組的欄位，然後指定要使用的值。

      >[!NOTE]
      >
      >可為每個值使用不同限制。例如，您可以為 **[!UICONTROL Gender]** 欄位指定分組，而且將包含 **[!UICONTROL Male]** 成員的母體限制為 10 人，並將包含 **[!UICONTROL Female]** 成員的母體限制為 30 人。如果您使用數個資料分組欄位，所有分組都必須有相同的大小。
   ![](assets/wkf_segment_limit_by_grouping.png)

1. 確認區段的設定。
1. 重複此程序的步驟 6 到 10，視需要盡量新增區段。
1. 如有需要，在 **[!UICONTROL Advanced options]** 索引標籤中編輯參數：

   * 的 **[!UICONTROL Enable overlapping of outbound populations]** 選項定義如何管理屬於多個段的配置檔案：
      * 如果未啟用該選項， **[!UICONTROL Segmentation]** 活動檢查配置檔案在多個輸出轉換中不存在，即使此配置檔案滿足多個子集的條件。
      * 啟用該選項後，如果配置檔案滿足其篩選條件，則可以在幾個子集中找到它們。
   * 如果已為入站人口分配了要保留的段代碼，請檢查 **[!UICONTROL Concatenate the code of each segment]** 的雙曲餘切值。 會將活動中指定的區段代碼新增至初始區段代碼。
   * 如果需要利用剩餘人口，請檢查 **[!UICONTROL Generate complement]** 的雙曲餘切值。 請參閱 [用例：使用補碼建立交貨](../../automating/using/workflow-created-query-with-complement.md)。

1. 確認活動的設定並儲存工作流程。
