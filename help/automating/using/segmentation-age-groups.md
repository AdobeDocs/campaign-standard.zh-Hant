---
title: 根據年齡組劃分
description: 本頁根據資料庫設定檔的年齡群組，呈現資料庫設定檔的分段。 工作流程的目的是為每個年齡組傳送特定電子郵件。
page-status-flag: never-activated
uuid: 77796f18-cad5-4e7a-9d7b-4ed0dd8943bf
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 0ccd9d02-772e-406b-874a-5381dd0c8709
context-tags: segmentation,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7ffa48365875883a98904d6b344ac005afe26e18
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 0%

---


# 根據年齡組劃分 {#segmentation-age-groups}

下列範例顯示根據年齡組劃分資料庫描述檔的區段。

工作流程的目的是為每個年齡組傳送特定電子郵件。 考慮到此工作流程是測試促銷活動的一部分，每個區段最多只能包含100個隨機選取的設定檔，以便同時使用受限且具代表性的對象。

![](assets/wkf_segment_example_4.png)

工作流程由下列元素組成：

* A [Scheduler活動](../../automating/using/segmentation.md) ，用於指定工作流的執行日期。
* A [Query](../../automating/using/query.md) activity to target profiles of the peoples have been expered and email address.
* 「區 [段](../../automating/using/segmentation.md) 」活動，可建立3個區段，分為不同的對外轉場： 18-25歲，26-32歲，32歲以上。 區段是根據下列參數定義：

   ![](assets/wkf_segment_example_3.png)

   * 年齡篩選以定義區段的年齡群組

      ![](assets/wkf_segment_new_segment.png)

   * 連 **[!UICONTROL Random sampling]** 結至100上限的 **[!UICONTROL Maximum size]** 類型限制

      ![](assets/wkf_segment_example_1.png)

* 每個 [區段的電子郵件](../../automating/using/email-delivery.md) 傳送活動。
