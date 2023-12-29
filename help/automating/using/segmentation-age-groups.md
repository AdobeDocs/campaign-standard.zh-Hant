---
title: 根據年齡群體細分
description: 此頁面會根據年齡群組區分資料庫設定檔。 工作流程的目的是為每個年齡群組傳送特定電子郵件。
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: segmentation,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: dab7ef86-4776-48f4-be9a-37de316e0dd9
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '204'
ht-degree: 51%

---

# 根據年齡群體細分 {#segmentation-age-groups}

下列範例會根據年齡群組區分資料庫設定檔。

工作流程的目的是為每個年齡群組傳送特定電子郵件。考慮到此工作流程屬於測式行銷活動的一部分，每個區段只能包含最多隨機選取的 100 個設定檔，以便同時使用受限制的對象和代表。

![](assets/wkf_segment_example_4.png)

工作流程由下列元素組成：

* A [排程器活動](../../automating/using/segmentation.md) 以指定工作流程的執行日期。
* A [查詢](../../automating/using/query.md) 已輸入其生日及電子郵件地址之人們的目標設定檔的活動。
* A [細分](../../automating/using/segmentation.md) 建立分為不同出站轉變的3個區段的活動：18-25歲、26-32歲及超過32歲的設定檔。 區段會依據下列參數定義：

  ![](assets/wkf_segment_example_3.png)

   * 年齡篩選器以定義區段的年齡群組

     ![](assets/wkf_segment_new_segment.png)

   * 已連接至 100 的 **[!UICONTROL Maximum size]** 限制的 **[!UICONTROL Random sampling]** 類型限制

     ![](assets/wkf_segment_example_1.png)

* 一個 [電子郵件傳遞](../../automating/using/email-delivery.md) 每個區段的活動。
