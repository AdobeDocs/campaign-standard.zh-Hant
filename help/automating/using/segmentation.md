---
title: 分段
seo-title: 分段
description: 分段
seo-description: 「分段」活動可讓您從工作流程先前放置的活動計算的人口族群中建立一或數個區段。
page-status-flag: 從未啓動
uuid: 77796f18-cadp5-4e7 a-9d7 b-4d0 d8943 BF
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: reference
topic-tags: 定位活動
discoiquuid: 0cd9d02-772e-406b-874a-5381dd0c8709
context-tags: 區段，主要
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Segmentation{#segmentation}

## Description {#description}

![](assets/segmentation.png)

**[!UICONTROL Segmentation]** 活動可讓您從工作流程先前放置的活動計算的人口族群建立一或數個區段。活動結束時，可在單一轉場或不同轉場中處理。

>[!NOTE]
>
>依預設，傳入人口的成員只能屬於單一區段。篩選器會根據活動中區段的順序來套用。

## Context of use {#context-of-use}

**[!UICONTROL Segmentation]** 一般定位在定位活動(查詢、相交、聯合、排除等)之後。以定義區段所依據的標準人口。

## Configuration {#configuration}

1. Drag and drop a **[!UICONTROL Segmentation]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. Select the **[!UICONTROL Resource type]** on which the segmentation has to be carried out:

   * **[!UICONTROL Database resource]** 如果對資料庫中已存在的資料進行分段。Select the **[!UICONTROL Filtering dimension]** depending on the data that you want to segment. By default, segmentation is carried out on the **profiles**.
   * **[!UICONTROL Temporary resource]** 如果區段是在工作流程的暫存資料上執行：選取 **[!UICONTROL Targeted set]** 包含要區段的資料。匯入檔案或資料庫中的資料時，可能會發生此使用案例。

1. 選擇您要使用的傳出轉換類型：

   * **[!UICONTROL Generate one transition per segment]**：在活動結束時，會針對每個已設定的區段新增一個對外轉場。
   * **[!UICONTROL Generate all segments in one transition]**：所有設定的區段都會重新分組為單一對外轉場。指定轉場標籤。每個區段的成員都會保留已指派給他們的區段代碼。

1. Add a segment by using the ![](assets/add_darkgrey-24px.png) or **[!UICONTROL Add an element]** button and specify the standard properties:

   * **[!UICONTROL Do not activate the transition if the population is empty]**：只有在擷取資料時，才會啓用區段。
   * **[!UICONTROL Filter initial population (query)]**：可讓您篩選此區段的人口族群。
   * **[!UICONTROL Limit segment population]**：可讓您限制區段大小。
   * **[!UICONTROL Filter and limit segment population]**：可讓您篩選區段人口並限制其大小。
   * **[!UICONTROL Label]**：區段標籤。
   * **[!UICONTROL Segment code]**：代碼指派給區段人口。區段代碼可使用標準運算式和事件變數加以個人化(請參閱 [自訂活動變數](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables)的活動)。
   * **[!UICONTROL Exclude segment from population]**：可讓您排除活動對外人口的指定區段。This option can only be used if the **[!UICONTROL Generate all segments in the same transition]** option is selected.
   ![](assets/wkf_segment_new_segment.png)

1. 開啓區段的詳細資料檢視，以存取後者的設定選項。To do this, check the relevant box in the activity's segment list, then select ![](assets/wkf_segment_parameters_24px.png).
1. If the option to filter the initial population is checked, open the **[!UICONTROL Filter]** tab and specify your segment's population. 篩選是根據步驟中選取的篩選維度而定。Consult the [Query editing](../../automating/using/editing-queries.md) section for further information on population filtering.

   如果對暫存資源進行分段，則無法在此索引標籤中使用計數和預覽。

1. If the option to limit the segment size is checked, open the **[!UICONTROL Limitation]** tab.

   First, select the **[!UICONTROL Type of limit]** that you would like to use:

   * **[!UICONTROL Random sampling]**：選取區段人口時，會根據需要隨機考量 **[!UICONTROL Filter]** 標籤的設定。
   * **[!UICONTROL Ordered sampling]**：區段人口會以順序方式選取。因此，您必須指定要納入的欄以及要套用的排序類型。For example, if you select the **Age** field as the sort column while applying a **[!UICONTROL Descending sort]** and setting a limit of 100, only the profiles of the top 100 oldest people will be kept.
   Now specify the size **[!UICONTROL Limit]** of the segment:

   * **[!UICONTROL Size (as a % of the initial population)]**：使用活動初始人口百分比來指定區段大小。
   * **[!UICONTROL Maximum size]**：指定區段人口的最大成員數。
   * **[!UICONTROL By data grouping]**：您可以根據傳入人口的特定欄位值來限制區段人口族群。選取群組的欄位，然後指定要使用的值。
   * **[!UICONTROL By data grouping (as a %)]**：您可以根據特定傳入人口欄位的值，使用百分比來限制群體人口族群。選取要套用群組的欄位，然後指定要使用的值。

      >[!NOTE]
      >
      >可使用每個值的不同限制。For example, you can specify a grouping for the **[!UICONTROL Gender]** field and limit the population with **[!UICONTROL Male]** members to 10 and the population with **[!UICONTROL Female]** members to 30 people. 如果您使用數個資料分組欄位，所有群組都必須具有相同大小。
   ![](assets/wkf_segment_limit_by_grouping.png)

1. 確認區段的設定。
1. 重復步驟到10的步驟，視需要新增多個區段。
1. If necessary, edit the parameters in the **[!UICONTROL Advanced options]** tab:

   * Check the **[!UICONTROL Enable overlapping of outbound populations]** option if you want a member of the inbound population to belong to several segments at the same time. 活動的對外人口可能超過傳入的人口族群。
   * Check the **[!UICONTROL Concatenate the code of each segment]** option if the inbound population has already been assigned a segment code that you want to keep. 活動中指定的區段代碼將新增至初始區段代碼。
   * Check the **[!UICONTROL Generate complement]** option if you would like to exploit the remaining population.

1. 確認活動的設定並儲存工作流程。

## Example {#example}

以下範例顯示資料庫設定檔根據其年齡群組的分段。工作流程的目的是要傳送每個年齡群組的特定電子郵件。由於此工作流程是測試促銷活動的一部分，每個區段最多只能包含100個設定檔，以隨機使用，以便同時使用有限和代表的對象。

![](assets/wkf_segment_example_4.png)

工作流程由下列元素組成：

* A **[!UICONTROL Scheduler]** activity to specify the workflow's execution date. Refer to the [Scheduler](../../automating/using/scheduler.md) section.
* **[!UICONTROL Query]** 活動來定位已輸入生日和電子郵件地址之人員的個人檔案。Refer to the [Query](../../automating/using/query.md) section.
* **[!UICONTROL Segmentation]** 建立個區段，分為不同對外轉場的活動：18-25歲、26-32歲及超過32歲的個人檔案。區段是根據下列參數定義：

   ![](assets/wkf_segment_example_3.png)

   * 要定義區段年齡組的年齡篩選

      ![](assets/wkf_segment_new_segment.png)

   * **[!UICONTROL Random sampling]** 連結至 **[!UICONTROL Maximum size]** 限制的類型限制

      ![](assets/wkf_segment_example_1.png)

* An **[!UICONTROL Email delivery]** activity per segment. Refer to the [Email delivery](../../automating/using/email-delivery.md) section.

