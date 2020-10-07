---
title: 外部信號和資料導入
description: 以下示例說明與資料導入一起使用的外部信號活動。
page-status-flag: never-activated
uuid: 884b6daf-bfd9-440b-8336-004b80c76def
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 911c71b5-da8b-4916-b645-13bba6d21715
context-tags: signal,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# External signal and data import {#external-signal-data-import}

以下範例說明典型使用案例中的 **[!UICONTROL External signal]** 活動。在來源工作流程中執行資料匯入。完成匯入並更新資料庫後，就會觸發第二個工作流程。此第二個工作流程用於更新匯入資料的彙總。

來源工作流程如下所示：

* [載入檔案](../../automating/using/load-file.md)活動會上傳包含新購買資料的檔案。請注意，由於資料庫中預設沒有購買資料，因此[資料庫已相應擴展](../../developing/using/data-model-concepts.md)。

   例如：

   ```
   tcode;tdate;customer;product;tamount
   aze123;21/05/2015;dannymars@example.com;A2;799
   aze124;28/05/2015;dannymars@example.com;A7;8
   aze125;31/07/2015;john.smith@example.com;A7;8
   aze126;14/12/2015;john.smith@example.com;A10;4
   aze127;02/01/2016;dannymars@example.com;A3;79
   aze128;04/03/2016;clara.smith@example.com;A8;149
   ```

* [調解](../../automating/using/reconciliation.md)活動會建立匯入資料和資料庫之間的連結，以便交易資料正確連接到設定檔和產品。
* [更新資料](../../automating/using/update-data.md)活動將插入並更新帶有傳入資料的資料庫的「交易」資源。
* An [End](../../automating/using/start-and-end.md) activity triggers the destination workflow, which is used to update aggregates.

![](assets/signal_example_source1.png)

目標工作流程如下：

* An [External signal](../../automating/using/external-signal.md) activity waits for the source workflow to be successfully finished.
* [查詢](../../automating/using/query.md#enriching-data)活動會定位設定檔，並以收集來擴充設定檔，以擷取最後的購買日期。
* [更新資料](../../automating/using/update-data.md)活動會將其他資料儲存在專用的自訂欄位中。請注意，設定檔資源已擴展到新增&#x200B;**上次購買日期**&#x200B;欄位。

![](assets/signal_example_source2.png)
