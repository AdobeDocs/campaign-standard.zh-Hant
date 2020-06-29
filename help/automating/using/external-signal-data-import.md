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
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c3911232a3cce00c2b9a2e619f090a7520382dde
workflow-type: tm+mt
source-wordcount: '229'
ht-degree: 0%

---


# 外部信號和資料導入 {#external-signal-data-import}

以下示例說明了 **[!UICONTROL External signal]** 典型使用案例中的活動。 在源工作流中執行資料導入。 完成匯入並更新資料庫後，就會觸發第二個工作流程。 此第二個工作流程用於更新匯入資料的匯總。

源工作流如下所示：

* 載入 [檔案活動](../../automating/using/load-file.md) ，會上傳包含新購買資料的檔案。 請注意，由於 [在資料庫中預設不存在購買資料](../../developing/using/data-model-concepts.md) ，因此資料庫已相應擴展。

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

* 「協 [調](../../automating/using/reconciliation.md) 」活動會建立導入資料和資料庫之間的連結，以便事務資料正確連接到配置檔案和產品。
* 「更 [新資料](../../automating/using/update-data.md) 」活動將插入並更新帶有傳入資料的資料庫的「事務」資源。
* End [](../../automating/using/start-and-end.md) 活動會觸發目標工作流，用於更新聚合。

![](assets/signal_example_source1.png)

目標工作流程如下：

* External [signal](../../automating/using/external-signal.md) activity會等待源工作流成功完成。
* 查詢 [活動](../../automating/using/query.md#enriching-data) ，會定位描述檔，並以收集集來豐富描述檔，以擷取最後的購買日期。
* 「更 [新資料](../../automating/using/update-data.md) 」活動會將其他資料儲存在專用的自訂欄位中。 請注意，配置檔案資源已擴展到添加「上次購 **買日期** 」欄位。

![](assets/signal_example_source2.png)
