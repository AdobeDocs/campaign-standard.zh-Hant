---
title: 關於目標定位活動
description: 可以從螢幕左側訪問目標活動。
audience: automating
content-type: reference
topic-tags: targeting-activities
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 1cd471e3-5332-4119-b342-2c3c8503fdd1
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 48%

---

# 關於目標定位活動{#about-targeting-activities}

從浮動視窗的畫面左側展開 **[!UICONTROL Targeting]** 區段。

這些活動專門針對、操縱人口資料和過濾活動。 它們允許您通過定義集和拆分或使用交集、並集或排除操作組合這些集來構建一個或多個目標。

![](assets/wkf_targeting_activities.png)

**[!UICONTROL Targeting]** 一節提供下列活動：

* [查詢](../../automating/using/query.md)
* [增量查詢](../../automating/using/incremental-query.md)
* [聯合](../../automating/using/union.md)
* [交集](../../automating/using/intersection.md)
* [排除](../../automating/using/exclusion.md)
* [細分](../../automating/using/segmentation.md)
* [讀取對象](../../automating/using/read-audience.md)
* [儲存對象](../../automating/using/save-audience.md)
* [去重複化](../../automating/using/deduplication.md)
* [擴充](../../automating/using/enrichment.md)

**[!UICONTROL Targeting]** 活動允許您定義 **段代碼** 他們的出境過渡。 然後，您可以根據這些區段代碼建立報表，以評估行銷行銷活動的效率。如需詳細資訊，請參閱[本區段](../../reporting/using/creating-a-report-workflow-segment.md)。

## 選擇資料 {#selecting-data}

您可以使用以下活動選擇資料：

* **[!UICONTROL Query]** 活動可讓您從 Adobe Campaign 資料庫中篩選及擷取元素總量。查看 [查詢](../../automating/using/query.md) 的子菜單。
* **[!UICONTROL Incremental query]** 活動可讓您從 Adobe Campaign 資料庫中篩選及擷取元素總量。每次執行此活動時，都會排除先前執行的結果。這允許您僅針對新元素。請參閱。 [增量查詢](../../automating/using/incremental-query.md) 的子菜單。
* 的 **[!UICONTROL Read audience]** 活動允許您檢索現有受眾並通過應用其他篩選條件來細化它。請參閱 [閱讀受眾](../../automating/using/read-audience.md) 的子菜單。

## 分割資料 {#segmenting-data}

Adobe Campaign允許您處理入站資料集。 因此，您可以合併多個總體，排除其一部分，或僅使資料對多個目標保持公用。

* **[!UICONTROL Union]** 活動可讓您將多個活動的結果重新群組至單一目標。查看 [聯合](../../automating/using/union.md) 的子菜單。
* **[!UICONTROL Intersection]**　活動可讓您僅保留活動中不同入站母體的共同元素。查看 [交集](../../automating/using/intersection.md) 的子菜單。
* **[!UICONTROL Exclusion]** 活動可讓您根據特定條件，從單一母體中排除元素。查看 [排除](../../automating/using/exclusion.md) 的子菜單。
* **[!UICONTROL Segmentation]** 活動可讓您從工作流程中先前放置之活動計算的母體中建立一或多個分段。在活動結束時，可以在單一轉變或不同轉變中處理這些轉變。查看 [分段](../../automating/using/segmentation.md) 的子菜單。

## 豐富資料 {#enriching-data}

所識別和收集的資料可以被富集、聚集和操縱以優化目標構造。 通過包括未在資料集市中建模的資料，您可以簡化和優化目標流程。

的 **[!UICONTROL Additional data]** 頁籤 **[!UICONTROL Query]** 和 **[!UICONTROL Incremental query]** 活動允許您豐富查詢所針對的資料，並將此資料傳輸到以下工作流活動中，以供使用。 您尤其可以新增：

* 簡單資料
* 彙總
* 集合

**相關主題：**

* [用例：個性化包含其他資料的電子郵件](../../automating/using/personalizing-email-with-additional-data.md)
