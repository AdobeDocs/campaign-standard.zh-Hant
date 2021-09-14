---
title: 根據年齡群體細分
description: 此頁面會根據年齡群組呈現資料庫設定檔的分段。 工作流程的目的是為每個年齡群組傳送特定電子郵件。
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
source-wordcount: '198'
ht-degree: 66%

---

# 根據年齡群體細分 {#segmentation-age-groups}

下列範例會依據年齡群組區分資料庫設定檔。

工作流程的目的是為每個年齡群組傳送特定電子郵件。考慮到此工作流程屬於測式行銷活動的一部分，每個區段只能包含最多隨機選取的 100 個設定檔，以便同時使用受限制的對象和代表。

![](assets/wkf_segment_example_4.png)

工作流程由下列元素組成：

* [排程器活動](../../automating/using/segmentation.md)以指定工作流的執行日期。
* [Query](../../automating/using/query.md)活動，用於定位已輸入其生日和電子郵件地址的人員的設定檔。
* [分段](../../automating/using/segmentation.md)活動，用於建立分為不同出站轉變的3個區段：18-25-year年、26-32-year年和超過32歲的設定檔。 區段會依據下列參數定義：

   ![](assets/wkf_segment_example_3.png)

   * 年齡篩選器以定義區段的年齡群組

      ![](assets/wkf_segment_new_segment.png)

   * 已連接至 100 的 **[!UICONTROL Maximum size]** 限制的 **[!UICONTROL Random sampling]** 類型限制

      ![](assets/wkf_segment_example_1.png)

* 每個區段的[電子郵件傳送](../../automating/using/email-delivery.md)活動。
