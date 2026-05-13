---
title: 關於目標定位活動
description: 您可以從熒幕左側存取目標定位活動。
audience: automating
content-type: reference
topic-tags: targeting-activities
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 1cd471e3-5332-4119-b342-2c3c8503fdd1
TQID: https://experienceleague.adobe.com/PPDlvoeHKNpeLfYe4qYFq7mzQUb3oR7XkrMK-jQFpmY
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 437
ht-degree: 54%

---

# 關於目標定位活動{#about-targeting-activities}

從浮動視窗的畫面左側展開 **[!UICONTROL Targeting]** 區段。

這些活動特定於定位、操縱人口資料和篩選活動。 它們可讓您藉由定義集合，並使用交集、等位或排除作業來分割或組合這些集合，以建立一或多個目標。

![](assets/wkf_targeting_activities.png)

**[!UICONTROL Targeting]** 一節提供下列活動：

* [查詢](../../automating/using/query.md)
* [增量查詢](../../automating/using/incremental-query.md)
* [聯合](../../automating/using/union.md)
* [交集](../../automating/using/intersection.md)
* [排除](../../automating/using/exclusion.md)
* [細分](../../automating/using/segmentation.md)
* [讀取客群](../../automating/using/read-audience.md)
* [儲存客群](../../automating/using/save-audience.md)
* [重複資料刪除](../../automating/using/deduplication.md)
* [擴充](../../automating/using/enrichment.md)

**[!UICONTROL Targeting]**&#x200B;活動可讓您為其對外轉變定義&#x200B;**區段代碼**。 然後，您可以根據這些區段代碼建立報表，以評估行銷行銷活動的效率。 如需詳細資訊，請參閱[本章節](../../reporting/using/creating-a-report-workflow-segment.md)。

## 選取資料 {#selecting-data}

您可以使用以下活動選取資料：

* **[!UICONTROL Query]** 活動可讓您從 Adobe Campaign 資料庫中篩選及擷取元素總量。 請參閱[查詢](../../automating/using/query.md)區段。
* **[!UICONTROL Incremental query]** 活動可讓您從 Adobe Campaign 資料庫中篩選及擷取元素總量。 每次執行此活動時，都會排除先前執行的結果。 這可讓您僅鎖定新元素。請參閱。 [增量查詢](../../automating/using/incremental-query.md)區段。
* **[!UICONTROL Read audience]** 活動可讓您擷取現有的客群，並套用其他篩選條件來調整客群。請參閱[讀取對象](../../automating/using/read-audience.md)區段。

## 將資料分段 {#segmenting-data}

Adobe Campaign可讓您處理傳入資料的集合。 因此，您可以合併多個母體、排除部分母體，或僅保留多個目標通用的資料。

* **[!UICONTROL Union]** 活動可讓您將多個活動的結果重新群組至單一目標。 請參閱[聯合](../../automating/using/union.md)一節。
* **[!UICONTROL Intersection]**　活動可讓您僅保留活動中不同入站群體的共同元素。 請參閱[交集](../../automating/using/intersection.md)一節。
* **[!UICONTROL Exclusion]** 活動可讓您根據特定條件，從單一群體中排除元素。 請參閱[排除](../../automating/using/exclusion.md)區段。
* **[!UICONTROL Segmentation]** 活動可讓您從工作流程中先前放置之活動計算的群體中建立一或多個分段。 在活動結束時，可以在單一轉變或不同轉變中處理這些轉變。 請參閱[分段](../../automating/using/segmentation.md)區段。

## 豐富資料 {#enriching-data}

已識別和收集的資料可以擴充、彙總和操作，以最佳化目標建構。 您可以透過包含未在資料超市中模型化的資料，來簡化及最佳化鎖定過程。

**[!UICONTROL Query]**&#x200B;和&#x200B;**[!UICONTROL Incremental query]**&#x200B;活動的&#x200B;**[!UICONTROL Additional data]**&#x200B;索引標籤可讓您擴充查詢所定位的資料，並將此資料傳輸至下列工作流程活動，以便在其中使用。 您尤其可以新增：

* 簡單資料
* 彙總
* 集合

**相關主題：**

* [使用案例：使用其他資料個人化電子郵件](../../automating/using/personalizing-email-with-additional-data.md)
