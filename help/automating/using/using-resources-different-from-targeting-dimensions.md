---
title: 使用與目標定位維度不同的資源
description: 瞭解如何使用與目標維度不同的資源。
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: query,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 5805bdfa-fb33-4a46-ba1e-7a10b067349b
TQID: 'https://experienceleague.adobe.com/tGVP20eQpo7EuB1xluX2AQHHMZ-IM-q6JmgFGp6Iwk4'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '295'
ht-degree: 76%
---
# 使用與目標定位維度不同的資源 {#using-resources-different-from-targeting-dimensions}

此使用案例顯示如何使用與目標維度不同的資源，例如在遠端表格中尋找特定記錄。

如需目標維度和資源的詳細資訊，請參閱[本節](../../automating/using/query.md#targeting-dimensions-and-resources)

**範例　1：使用標籤「歡迎回來！」識別傳送所定位的輪廓**。

* 在此案例中，我們要選擇目標輪廓。 我們會將目標維度設為　**[!UICONTROL Profiles (profile)]**。
* 我們想要根據傳送標籤來篩選所選取的輪廓。 因此，我們將資源設定為　**[!UICONTROL Delivery logs]**。 如此一來，我們會直接在傳送記錄表中進行篩選，以提供更理想的效能。

![](assets/targeting_dimension6.png)

![](assets/targeting_dimension7.png)

**範例　2：識別傳送時未鎖定的輪廓，並標示為「歡迎返回！」**

在上個範例中，我們使用與目標維度不同的資源。 只有當您尋找已&#x200B;**出現**&#x200B;在遠距表格（在此範例中為傳送記錄檔）中的記錄，才能進行此作業。

如果我們想要尋找&#x200B;**不存在**&#x200B;遠距表格（例如，未由特定傳送定位的輪廓）中的記錄，您必須使用相同的資源及目標為度，因為記錄將不會存在於遠距表格（傳送記錄檔）中。

* 在此案例中，我們要選擇目標輪廓。 我們會將目標維度設為　**[!UICONTROL Profiles (profile)]**。
* 我們想要根據傳送標籤來篩選所選取的輪廓。 無法直接篩選傳送記錄，因為我們正在尋找不在傳送記錄表格中的記錄。 因此，我們將資源設定為 **[!UICONTROL Profile (profile)]** 並在輪廓案表上建構查詢。

![](assets/targeting_dimension8.png)

![](assets/targeting_dimension9.png)
