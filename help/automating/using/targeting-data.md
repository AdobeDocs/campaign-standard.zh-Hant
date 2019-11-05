---
title: 目標定位資料
description: 瞭解不同的定位方式，並選取所需的資料。
page-status-flag: 從未激活
uuid: 0645d6e5-6a7e-4917-874a-7e7725f06abd
contentOwner: 紹維亞
products: SG_CAMPAIGN/STANDARD
audience: 自動化
content-type: 參考
topic-tags: 工作流——一般操作
discoiquuid: 382ea74e-1662-4c64-96d7-676040586913
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 目標定位資料{#targeting-data}

## 選擇資料 {#selecting-data}

您可以使用下列活動來選取資料：

* 此活 **[!UICONTROL Query]** 動可讓您從Adobe Campaign資料庫中篩選及擷取一組元素。 請參閱 [查詢](../../automating/using/query.md) 節。
* 此活 **[!UICONTROL Incremental query]** 動可讓您從Adobe Campaign資料庫中篩選及擷取一組元素。 每次執行此活動時，都會排除先前執行的結果。 這可讓您只鎖定新元素請參閱。 [增量查詢](../../automating/using/incremental-query.md) 節。
* 此活 **[!UICONTROL Read audience]** 動可讓您擷取現有的觀眾，並套用其他篩選條件來調整觀眾。請參閱「讀取 [觀眾](../../automating/using/read-audience.md) 」區段。

## 劃分資料 {#segmenting-data}

Adobe Campaign可讓您處理傳入資料的集合。 因此，您可以合併多個群體、排除其中一部分，或僅讓資料與多個目標保持共通。

* 此活 **[!UICONTROL Union]** 動可讓您將多個活動的結果重新群組至單一目標。 請參閱 [Union](../../automating/using/union.md) 一節。
* 此活 **[!UICONTROL Intersection]** 動可讓您僅保留活動中不同傳入人口族群的共同元素。 請參閱「 [交叉點](../../automating/using/intersection.md) 」部分。
* 此活 **[!UICONTROL Exclusion]** 動可讓您根據特定條件，從單一人口中排除元素。 請參閱 [排除](../../automating/using/exclusion.md) 。
* 活 **[!UICONTROL Segmentation]** 動可讓您從工作流程中先前放置的活動計算的人口中建立一個或多個區段。 在活動結束時，可以在單個轉變或不同轉變中處理這些轉變。 請參閱 [區段](../../automating/using/segmentation.md) 。

## 豐富資料 {#enriching-data}

所識別和收集的資料可以被富集、聚集和操作以優化目標結構。 您可以透過納入資料集市中未建模的資料，簡化並最佳化目標鎖定程式。

使用 **[!UICONTROL Additional data]** 和活動 **[!UICONTROL Query]** 的選 **[!UICONTROL Incremental query]** 項卡，您可以豐富查詢所定位的資料，並將此資料傳輸到以下工作流活動中，以便在其中使用。 您尤其可以新增：

* 簡單資料
* 聚合
* 系列

**相關主題**

* [使用案例：建立每週一次的電子郵件傳送](../../automating/using/workflow-weekly-offer.md)
* [使用案例：建立依位置分段的傳送](../../automating/using/workflow-segmentation-location.md)
* [使用案例：建立具備輔助功能的傳送](../../automating/using/workflow-created-query-with-complement.md)
* [使用案例：重新定位傳送新傳送給非開啟者的工作流程](../../automating/using/workflow-cross-channel-retargeting.md)
