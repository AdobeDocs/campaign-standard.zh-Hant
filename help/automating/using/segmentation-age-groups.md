---
title: 根據年齡群體細分
description: 本頁根據資料庫設定檔的年齡群組，呈現資料庫設定檔的分段。 工作流程的目的是為每個年齡群組傳送特定電子郵件。
page-status-flag: never-activated
uuid: 77796f18-cad5-4e7a-9d7b-4ed0dd8943bf
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 0ccd9d02-772e-406b-874a-5381dd0c8709
context-tags: segmentation,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 根據年齡群體細分 {#segmentation-age-groups}

下列範例會依據年齡群組區分資料庫設定檔。

工作流程的目的是為每個年齡群組傳送特定電子郵件。考慮到此工作流程屬於測式行銷活動的一部分，每個區段只能包含最多隨機選取的 100 個設定檔，以便同時使用受限制的對象和代表。

![](assets/wkf_segment_example_4.png)

工作流程由下列元素組成：

* A [Scheduler activity](../../automating/using/segmentation.md) to specify the workflow&#39;s execution date.
* A [Query](../../automating/using/query.md) activity to target profiles of people whose birthday and email address have been entered.
* A [Segmentation](../../automating/using/segmentation.md) activity to create 3 segments divided into different outbound transitions: 18-25-year old, 26-32-year old and profiles that are over 32 years old. 區段會依據下列參數定義：

   ![](assets/wkf_segment_example_3.png)

   * 年齡篩選器以定義區段的年齡群組

      ![](assets/wkf_segment_new_segment.png)

   * 已連接至 100 的 **[!UICONTROL Maximum size]** 限制的 **[!UICONTROL Random sampling]** 類型限制

      ![](assets/wkf_segment_example_1.png)

* 每個 [區段的電子郵件](../../automating/using/email-delivery.md) 傳送活動。
