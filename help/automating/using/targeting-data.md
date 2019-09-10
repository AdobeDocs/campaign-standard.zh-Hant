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
source-git-commit: bb65cbf808a95e8b42b2a682b7c0a9cc6225d920

---


# 定位資料{#targeting-data}

## 選取資料 {#selecting-data}

您可以使用下列活動來選取資料：

* **[!UICONTROL Query]** 此活動可讓您從Adobe Campaign資料庫篩選並提取元素族群。請參閱 [查詢](../../automating/using/query.md) 區段。
* **[!UICONTROL Incremental query]** 此活動可讓您從Adobe Campaign資料庫篩選並提取元素族群。每次執行此活動時，會排除先前執行的結果。這可讓您僅定位新元素，請參閱。[遞增查詢](../../automating/using/incremental-query.md) 區段。
* **[!UICONTROL Read audience]** 此活動可讓您擷取現有對象，並套用其他篩選條件來加以修飾。請參閱 [閱讀對象](../../automating/using/read-audience.md) 區段。

## 分段資料 {#segmenting-data}

Adobe Campaign可讓您處理傳入資料的集合。因此，您可以結合數個人口族群、排除部分人口，或僅保留數個目標的通用資料。

* **[!UICONTROL Union]** 活動可讓您將多個活動的結果重新群組為單一目標。請參閱 [Union](../../automating/using/union.md) 章節。
* **[!UICONTROL Intersection]** 活動可讓您僅保留活動中不同傳入人口族群常用的元素。請參閱 [「相交](../../automating/using/intersection.md) 」區段。
* **[!UICONTROL Exclusion]** 活動可讓您根據特定條件從一個人口族群排除元素。請參閱 [排除](../../automating/using/exclusion.md) 區段。
* **[!UICONTROL Segmentation]** 活動可讓您從工作流程先前放置的活動計算的人口族群建立一或數個區段。活動結束時，可在單一轉場或不同轉場中處理。請參閱 [區段](../../automating/using/segmentation.md) 區段。

## 豐富資料 {#enriching-data}

所識別和收集的資料可加以富集、匯總和控制，以最佳化目標結構。您可以透過納入資料集市中非模型的資料，簡化並最佳化鎖定程序。

此 **[!UICONTROL Additional data]** 和 **[!UICONTROL Query]****[!UICONTROL Incremental query]** 活動的索引標籤可讓您豐富查詢目標資料，並將此資料傳輸至下列工作流程活動，以便在其中使用。您尤其可以新增：

* 簡單資料
* 整合
* 系列

**相關主題**

* [使用案例：建立一次一次的電子郵件傳送](../../automating/using/workflow-weekly-offer.md)
* [使用案例：建立在位置上分段的傳送](../../automating/using/workflow-segmentation-location.md)
* [使用案例：建立具有輔助功能的傳送](../../automating/using/workflow-created-query-with-complement.md)
* [使用案例：重新定位工作流程，將新傳送傳送至非opervers](../../automating/using/workflow-cross-channel-retargeting.md)
