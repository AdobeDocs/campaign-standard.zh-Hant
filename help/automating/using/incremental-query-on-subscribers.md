---
title: 對服務訂閱者的增量查詢
description: 以下範例顯示如何設定增量查詢活動，以篩選服務的訂閱者。
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: incremental,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: c80ed1f6-ad8a-4448-a6df-b9881327228a
TQID: 'https://experienceleague.adobe.com/MHB1ETCecN9gQq51bSii-keTyFaYof0JtAyckFSCKQE'
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
topic_v2:
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 61%
---
# 對服務訂閱者的增量查詢 {#example--incremental-query-on-subscribers-to-a-service}

下列範例顯示 **[!UICONTROL Incremental query]** 活動的設定，該活動會篩選訂閱 **Running Newsletter** 服務之 Adobe Campaign 資料庫中的輪廓，以傳送包含促銷代碼的歡迎電子郵件給他們。

工作流程由下列元素組成：

![](assets/incremental_query_example1.png)

* [排程器](../../automating/using/scheduler.md)活動，每週一早上6:00執行工作流程。

  ![](assets/incremental_query_example2.png)

* [增量查詢](../../automating/using/incremental-query.md)活動，在第一次執行期間鎖定所有目前訂閱者，然後在下列執行期間只鎖定該周的新訂閱者。

  ![](assets/incremental_query_example3.png)

* [電子郵件傳遞](../../automating/using/email-delivery.md)活動。 工作流程每週執行一次，但您可以彙總所傳送的電子郵件和每月結果，例如產生整個月（而不只是一週）的報表。

  要執行此操作，請選取在這裡建立 **[!UICONTROL Recurring email]** 重新分組電子郵件和結果 **[!UICONTROL By month]**。

  定義電子郵件的內容並插入歡迎促銷代碼。 如需詳細資訊，請參閱[定義電子郵件內容](../../designing/using/personalization.md)區段。

然後開始執行工作流程。 每週新訂閱者都會收到包含促銷代碼的歡迎電子郵件。
