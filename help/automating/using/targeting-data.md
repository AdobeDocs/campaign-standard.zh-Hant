---
title: 定位資料
seo-title: 定位資料
description: 定位資料
seo-description: 瞭解不同的定位方式，並選擇您所需的資料。
page-status-flag: 從未啓動
uuid: 0645d6e5-6a7e-4917-874a-7e7725f06ABd
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: reference
topic-tags: 工作流程一般運作
discoiquuid: 382ea74e-1662-4c64-96d7-676040586913
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Targeting data{#targeting-data}

## Selecting data {#selecting-data}

您可以使用下列活動來選取資料：

* **[!UICONTROL Query]** 此活動可讓您從Adobe Campaign資料庫篩選並提取元素族群。See the [Query](../../automating/using/query.md) section.
* **[!UICONTROL Incremental query]** 此活動可讓您從Adobe Campaign資料庫篩選並提取元素族群。每次執行此活動時，會排除先前執行的結果。這可讓您僅定位新元素，請參閱。[遞增查詢](../../automating/using/incremental-query.md) 區段。
* **[!UICONTROL Read audience]** 此活動可讓您擷取現有對象，並套用其他篩選條件來加以修飾。請參閱 [閱讀對象](../../automating/using/read-audience.md) 區段。

## Segmenting data {#segmenting-data}

Adobe Campaign可讓您處理傳入資料的集合。因此，您可以結合數個人口族群、排除部分人口，或僅保留數個目標的通用資料。

* **[!UICONTROL Union]** 活動可讓您將多個活動的結果重新群組為單一目標。See the [Union](../../automating/using/union.md) section.
* **[!UICONTROL Intersection]** 活動可讓您僅保留活動中不同傳入人口族群常用的元素。See the [Intersection](../../automating/using/intersection.md) section.
* **[!UICONTROL Exclusion]** 活動可讓您根據特定條件從一個人口族群排除元素。See the [Exclusion](../../automating/using/exclusion.md) section.
* **[!UICONTROL Segmentation]** 活動可讓您從工作流程先前放置的活動計算的人口族群建立一或數個區段。活動結束時，可在單一轉場或不同轉場中處理。See the [Segmentation](../../automating/using/segmentation.md) section.

## Enriching data {#enriching-data}

所識別和收集的資料可加以富集、匯總和控制，以最佳化目標結構。您可以透過納入資料集市中非模型的資料，簡化並最佳化鎖定程序。

The **[!UICONTROL Additional data]** tab of the **[!UICONTROL Query]** and **[!UICONTROL Incremental query]** activities allows you to enrich the data targeted by the query and transfer this data to the following workflow activities, where it can be utilized. 您尤其可以新增：

* 簡單資料
* 整合
* 系列

