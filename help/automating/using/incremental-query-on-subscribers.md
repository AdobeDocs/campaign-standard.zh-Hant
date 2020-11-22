---
solution: Campaign Standard
product: campaign
title: 對服務訂閱者的增量查詢
description: 以下示例說明如何配置增量查詢活動以篩選服務的訂戶。
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: incremental,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '211'
ht-degree: 67%

---


# 對服務訂閱者的增量查詢 {#example--incremental-query-on-subscribers-to-a-service}

下列範例顯示 **[!UICONTROL Incremental query]** 活動的設定，該活動會篩選訂閱 **Running Newsletter** 服務之 Adobe Campaign 資料庫中的設定檔，以傳送包含促銷代碼的歡迎電子郵件給他們。

工作流程由下列元素組成：

![](assets/incremental_query_example1.png)

* A [Scheduler](../../automating/using/scheduler.md) activity, to execute the workflow every Monday at 6 am.

   ![](assets/incremental_query_example2.png)

* An [Incremental query](../../automating/using/incremental-query.md) activity, which targets all of the current subscribers during the first execution, then only the new subscribers of that week during the following executions.

   ![](assets/incremental_query_example3.png)

* 電子 [郵件傳送](../../automating/using/email-delivery.md) 活動。 工作流程每週執行一次，但您可以彙總所傳送的電子郵件和每月結果，例如產生整個月（而不只是一週）的報表。

   要執行此操作，請選取在這裡建立 **[!UICONTROL Recurring email]** 重新分組電子郵件和結果 **[!UICONTROL By month]**。

   定義電子郵件內容並插入歡迎促銷代碼。如需詳細資訊，請參閱「定 [義電子郵件內容](../../designing/using/personalization.md) 」區段。

然後開始執行工作流程。每週新訂閱者都會收到包含促銷代碼的歡迎電子郵件。
