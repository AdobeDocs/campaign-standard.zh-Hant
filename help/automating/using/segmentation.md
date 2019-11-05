---
title: 細分
description: 「區段」活動可讓您從工作流程中先前放置的活動計算的人口中建立一或多個區段。
page-status-flag: 從未激活
uuid: 77796f18-cad5-4e7a-9d7b-4ed0dd8943bf
contentOwner: 紹維亞
products: SG_CAMPAIGN/STANDARD
audience: 自動化
content-type: 參考
topic-tags: 定位活動
discoiquuid: 0ccd9d02-772e-406b-874a-5381dd0c8709
context-tags: 分段，主要
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 細分{#segmentation}

## 說明 {#description}

![](assets/segmentation.png)

活 **[!UICONTROL Segmentation]** 動可讓您從工作流程中先前放置的活動計算的人口中建立一個或多個區段。 在活動結束時，可以在單個轉變或不同轉變中處理這些轉變。

>[!NOTE]
>
>依預設，傳入人口的成員只能屬於單一區段。 篩選會根據活動中區段的順序套用。

## 使用內容 {#context-of-use}

活 **[!UICONTROL Segmentation]** 動通常位於定位活動（查詢、交叉點、聯合、排除等）之後以定義基於其形成的段的標準總量。

## 配置 {#configuration}

1. 將活動拖放 **[!UICONTROL Segmentation]** 至工作流程。
1. 選擇活動，然後使用顯示的快 ![](assets/edit_darkgrey-24px.png) 速操作中的按鈕將其開啟。
1. 選取 **[!UICONTROL Resource type]** 必須執行區段的位置：

   * **[!UICONTROL Database resource]** 如果對資料庫中已存在的資料執行分段。 根據 **[!UICONTROL Filtering dimension]** 您要分段的資料選擇。 依預設，會對描述檔執行 **分段**。
   * **[!UICONTROL Temporary resource]** 如果對工作流的臨時資料執行分段：選取包 **[!UICONTROL Targeted set]** 含要分段的資料。 在導入檔案或資料庫中的資料已富集後，可以遇到此使用案例。

1. 選擇要使用的出站過渡類型：

   * **[!UICONTROL Generate one transition per segment]**:在活動結束時，會為每個已設定的區段新增一個出站轉場。
   * **[!UICONTROL Generate all segments in one transition]**:所有已設定的區段都會重新分組為單一對外轉移。 指定轉場標籤。 每個區段的成員會保留已指派給它們的區段代碼。

1. 使用或按鈕新增區 ![](assets/add_darkgrey-24px.png) 段並 **[!UICONTROL Add an element]** 指定標準屬性：

   * **[!UICONTROL Do not activate the transition if the population is empty]**:只有在擷取資料時，才會啟用區段。
   * **[!UICONTROL Filter initial population (query)]**:可讓您篩選此區段的人口。
   * **[!UICONTROL Limit segment population]**:可讓您限制區段大小。
   * **[!UICONTROL Filter and limit segment population]**:可讓您篩選群體人口並限制其大小。
   * **[!UICONTROL Label]**:區段標籤。
   * **[!UICONTROL Segment code]**:指派給區段人口的代碼。區段代碼可使用標準運算式和事件變數進行個人化(請參閱使用事件變 [數自訂活動](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables))。
   * **[!UICONTROL Exclude segment from population]**:可讓您從活動的對外人口中排除指定的區段。 只有在選取選項時，才 **[!UICONTROL Generate all segments in the same transition]** 能使用此選項。
   ![](assets/wkf_segment_new_segment.png)

1. 開啟區段的詳細資料檢視，以存取後者的設定選項。 若要這麼做，請勾選活動區段清單中的相關方塊，然後選取 ![](assets/wkf_segment_parameters_24px.png)。
1. 如果勾選了篩選初始人口族群的選項，請開 **[!UICONTROL Filter]** 啟標籤並指定區段的人口族群。 這些篩選條件是以步驟4中選取的篩選維度為基礎。 有關人口篩 [選的詳細資訊](../../automating/using/editing-queries.md) ，請參閱查詢編輯區段。

   如果對臨時資源執行分段，則此標籤中不提供人口計數和預覽。

1. 如果已勾選限制區段大小的選項，請開啟標 **[!UICONTROL Limitation]** 簽。

   首先，選 **[!UICONTROL Type of limit]** 取您要使用的：

   * **[!UICONTROL Random sampling]**:視需要隨機選取區段群組，並考量標籤的 **[!UICONTROL Filter]** 設定。
   * **[!UICONTROL Ordered sampling]**:區段人口是依順序選取。 因此，必須指定要考慮的列和要應用的排序類型。 例如，如果您在套用並設定限制為 ******[!UICONTROL Descending sort]** 100時，選取「年齡」欄位作為排序欄，則僅會保留前100名最老年人的個人檔案。
   現在指定區 **[!UICONTROL Limit]** 段的大小：

   * **[!UICONTROL Size (as a % of the initial population)]**:使用活動初始人口百分比來指定區段大小。
   * **[!UICONTROL Maximum size]**:指定區段人口的成員數上限。
   * **[!UICONTROL By data grouping]**:您可以根據傳入人口的特定欄位值限制區段人口。 選取要分組的欄位，然後指定要使用的值。
   * **[!UICONTROL By data grouping (as a %)]**:您可以使用百分比，根據特定傳入人口欄位的值限制區段人口。 選取要套用群組的欄位，然後指定要使用的值。

      >[!NOTE]
      >
      >可使用每個值的不同限制。 例如，您可以指定欄位的群組， **[!UICONTROL Gender]** 並將成員為10的人口 **[!UICONTROL Male]** ，以及成員為30的人 **[!UICONTROL Female]** 口限制。 如果您使用數個資料分組欄位，所有分組都必須有相同的大小。
   ![](assets/wkf_segment_limit_by_grouping.png)

1. 確認區段的設定。
1. 重複此程式的步驟6到10，以視需要新增區段。
1. 如有必要，請編輯頁籤中的 **[!UICONTROL Advanced options]** 參數：

   * 如果 **[!UICONTROL Enable overlapping of outbound populations]** 希望入站人口的成員同時屬於多個段，請選中該選項。 活動的出站人口可能超過入站人口。
   * 如果 **[!UICONTROL Concatenate the code of each segment]** 傳入人口已指派您要保留的區段代碼，請勾選此選項。 活動中指定的區段代碼將新增至初始區段代碼。
   * 如果 **[!UICONTROL Generate complement]** 要利用剩餘人口，請選中該選項。

1. 確認活動的設定並儲存工作流程。

## Example {#example}

下列範例顯示根據年齡組劃分資料庫描述檔的區段。 工作流程的目的是為每個年齡組傳送特定電子郵件。 考慮到此工作流程是測試促銷活動的一部分，每個區段最多只能包含100個隨機選取的設定檔，以便同時使用受限且具代表性的對象。

![](assets/wkf_segment_example_4.png)

工作流程由下列元素組成：

* 用 **[!UICONTROL Scheduler]** 於指定工作流執行日期的活動。 請參閱「 [Scheduler](../../automating/using/scheduler.md) 」部分。
* 定位 **[!UICONTROL Query]** 已輸入生日和電子郵件地址之人員的個人資料的活動。 請參閱「查 [詢](../../automating/using/query.md) 」部分。
* 建立 **[!UICONTROL Segmentation]** 3個區段的活動，分為不同的對外轉場：18-25歲，26-32歲，32歲以上。 區段是根據下列參數定義：

   ![](assets/wkf_segment_example_3.png)

   * 年齡篩選以定義區段的年齡群組

      ![](assets/wkf_segment_new_segment.png)

   * 連 **[!UICONTROL Random sampling]** 結至100上限的 **[!UICONTROL Maximum size]** 類型限制

      ![](assets/wkf_segment_example_1.png)

* 每個 **[!UICONTROL Email delivery]** 區段的活動。 請參閱「電子郵 [件傳送](../../automating/using/email-delivery.md) 」區段。

