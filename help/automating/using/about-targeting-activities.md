---
solution: Campaign Standard
product: campaign
title: 關於目標定位活動
description: 您可從螢幕左側存取定位活動。
audience: automating
content-type: reference
topic-tags: targeting-activities
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 48%

---


# 關於目標定位活動{#about-targeting-activities}

從浮動視窗的畫面左側展開 **[!UICONTROL Targeting]** 區段。

這些活動是針對目標、控制人口資料及篩選活動而進行的。 它們可讓您定義集合，並使用交叉點、合併或排除運算來分割或組合這些集合，以建立一或多個目標。

![](assets/wkf_targeting_activities.png)

**[!UICONTROL Targeting]** 一節提供下列活動：

* [查詢](../../automating/using/query.md)
* [增量查詢](../../automating/using/incremental-query.md)
* [聯集](../../automating/using/union.md)
* [交集](../../automating/using/intersection.md)
* [排除](../../automating/using/exclusion.md)
* [細分](../../automating/using/segmentation.md)
* [讀取閱聽眾](../../automating/using/read-audience.md)
* [儲存閱聽眾](../../automating/using/save-audience.md)
* [重複資料刪除](../../automating/using/deduplication.md)
* [擴充](../../automating/using/enrichment.md)

**[!UICONTROL Targeting]** 活動可讓您定義 **其出站轉** 換的區段代碼。 然後，您可以根據這些區段代碼建立報表，以評估行銷行銷活動的效率。如需詳細資訊，請參閱[本區段](../../reporting/using/creating-a-report-workflow-segment.md)。

## 選擇資料 {#selecting-data}

您可以使用下列活動來選取資料：

* **[!UICONTROL Query]** 活動可讓您從 Adobe Campaign 資料庫中篩選及擷取元素總量。請參閱 [查詢](../../automating/using/query.md) 節。
* **[!UICONTROL Incremental query]** 活動可讓您從 Adobe Campaign 資料庫中篩選及擷取元素總量。每次執行此活動時，都會排除先前執行的結果。這可讓您只鎖定新元素請參閱。 [增量查詢](../../automating/using/incremental-query.md) 節。
* The **[!UICONTROL Read audience]** activity allows you to retrieve an existing audience and to refine it by applying additional filtering conditions.See the [Read audience](../../automating/using/read-audience.md) section.

## 劃分資料 {#segmenting-data}

Adobe Campaign可讓您處理傳入資料的集合。 因此，您可以合併多個群體、排除其中一部分，或僅讓資料與多個目標保持共通。

* **[!UICONTROL Union]** 活動可讓您將多個活動的結果重新群組至單一目標。請參閱 [Union](../../automating/using/union.md) 一節。
* **[!UICONTROL Intersection]**　活動可讓您僅保留活動中不同入站母體的共同元素。請參閱「 [交叉點](../../automating/using/intersection.md) 」部分。
* **[!UICONTROL Exclusion]** 活動可讓您根據特定條件，從單一母體中排除元素。請參閱 [排除](../../automating/using/exclusion.md) 。
* **[!UICONTROL Segmentation]** 活動可讓您從工作流程中先前放置之活動計算的母體中建立一或多個分段。在活動結束時，可以在單一轉變或不同轉變中處理這些轉變。請參閱 [區段](../../automating/using/segmentation.md) 。

## 擴充資料 {#enriching-data}

所識別和收集的資料可以被富集、聚集和操作以優化目標結構。 您可以透過納入資料集市中未建模的資料，簡化並最佳化目標鎖定程式。

The **[!UICONTROL Additional data]** tab of the **[!UICONTROL Query]** and **[!UICONTROL Incremental query]** activities allows you to enrich the data targeted by the query and transfer this data to the following workflow activities, where it can be utilized. 您尤其可以新增：

* 簡單資料
* 彙總
* 集合

**相關主題：**

* [使用案例：使用其他資料個人化電子郵件](../../automating/using/personalizing-email-with-additional-data.md)
