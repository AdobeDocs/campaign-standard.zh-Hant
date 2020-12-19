---
solution: Campaign Standard
product: campaign
title: 根據年齡群體細分
description: 本頁根據資料庫設定檔的年齡群組，呈現資料庫設定檔的分段。 工作流程的目的是為每個年齡群組傳送特定電子郵件。
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: segmentation,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 66%

---


# 根據年齡群體細分 {#segmentation-age-groups}

下列範例會依據年齡群組區分資料庫設定檔。

工作流程的目的是為每個年齡群組傳送特定電子郵件。考慮到此工作流程屬於測式行銷活動的一部分，每個區段只能包含最多隨機選取的 100 個設定檔，以便同時使用受限制的對象和代表。

![](assets/wkf_segment_example_4.png)

工作流程由下列元素組成：

* [調度程式活動](../../automating/using/segmentation.md)以指定工作流的執行日期。
* [Query](../../automating/using/query.md)活動，用於定位已輸入生日和電子郵件地址的人員的配置檔案。
* [分段](../../automating/using/segmentation.md)活動，以建立3個分成不同對外轉場的區段：18-25歲，26-32歲，32歲以上。 區段會依據下列參數定義：

   ![](assets/wkf_segment_example_3.png)

   * 年齡篩選器以定義區段的年齡群組

      ![](assets/wkf_segment_new_segment.png)

   * 已連接至 100 的 **[!UICONTROL Maximum size]** 限制的 **[!UICONTROL Random sampling]** 類型限制

      ![](assets/wkf_segment_example_1.png)

* 每個區段的[電子郵件傳送](../../automating/using/email-delivery.md)活動。
