---
title: 外部訊號和資料匯入
description: 下列範例說明與資料匯入搭配使用的外部訊號活動。
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: signal,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: e2997cf5-861b-4202-aeb7-3a47c4d55bef
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '229'
ht-degree: 79%

---

# 外部訊號和資料匯入 {#external-signal-data-import}

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
* [End](../../automating/using/start-and-end.md)活動會觸發目標工作流程，用於更新匯總。

![](assets/signal_example_source1.png)

目標工作流程如下：

* [外部信號](../../automating/using/external-signal.md)活動等待源工作流成功完成。
* [查詢](../../automating/using/query.md#enriching-data)活動會定位設定檔，並以收集來擴充設定檔，以擷取最後的購買日期。
* [更新資料](../../automating/using/update-data.md)活動會將其他資料儲存在專用的自訂欄位中。請注意，設定檔資源已擴展到新增&#x200B;**上次購買日期**&#x200B;欄位。

![](assets/signal_example_source2.png)
