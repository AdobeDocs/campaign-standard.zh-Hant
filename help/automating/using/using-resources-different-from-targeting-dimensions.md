---
title: 使用與目標定位維度不同的資源
description: 瞭解如何使用與目標維度不同的資源。
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: query,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 5805bdfa-fb33-4a46-ba1e-7a10b067349b
source-git-commit: 9c14fc3de60d8e0304f8a7ebd46e7be34d2e0499
workflow-type: tm+mt
source-wordcount: '295'
ht-degree: 76%

---

# 使用與目標定位維度不同的資源 {#using-resources-different-from-targeting-dimensions}

此使用案例顯示如何使用與目標維度不同的資源，例如在遠端表格中尋找特定記錄。

如需目標維度和資源的詳細資訊，請參閱[本節](../../automating/using/query.md#targeting-dimensions-and-resources)

**範例　1：使用標籤「歡迎回來！」識別傳送所定位的設定檔**。

* 在此案例中，我們要定位設定檔。我們會將目標維度設為　**[!UICONTROL Profiles (profile)]**。
* 我們想要根據傳送標籤來篩選所選取的設定檔。因此，我們將資源設定為　**[!UICONTROL Delivery logs]**。如此一來，我們會直接在傳送記錄表中進行篩選，以提供更理想的效能。

![](assets/targeting_dimension6.png)

![](assets/targeting_dimension7.png)

**範例　2：識別傳送時未鎖定的設定檔，並標示為「歡迎返回！」**

在上個範例中，我們使用與目標維度不同的資源。只有當您尋找已&#x200B;**出現**&#x200B;在遠距表格（在此範例中為傳送記錄檔）中的記錄，才能進行此作業。

如果我們想要尋找&#x200B;**不存在**&#x200B;遠距表格（例如，未由特定傳送定位的設定檔）中的記錄，您必須使用相同的資源及目標為度，因為記錄將不會存在於遠距表格（傳送記錄檔）中。

* 在此案例中，我們要定位設定檔。我們會將目標維度設為　**[!UICONTROL Profiles (profile)]**。
* 我們想要根據傳送標籤來篩選所選取的設定檔。無法直接篩選傳送記錄，因為我們正在尋找不在傳送記錄表格中的記錄。因此，我們將資源設定為 **[!UICONTROL Profile (profile)]** 並在設定檔案表上建構查詢。

![](assets/targeting_dimension8.png)

![](assets/targeting_dimension9.png)
