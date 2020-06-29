---
title: 排程器
description: Scheduler活動允許您在工作流或活動啟動時進行調度。
page-status-flag: never-activated
uuid: f5e50a11-8dc9-4d98-9531-024c0fb3f7da
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 0fb16cea-3941-404f-899c-33f81ced4ed5
context-tags: schedule,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2d994d85f126951215f1227301599c554c1f12c8
workflow-type: tm+mt
source-wordcount: '555'
ht-degree: 0%

---


# 排程器{#scheduler}

## 說明 {#description}

![](assets/scheduler.png)

此活 **[!UICONTROL Scheduler]** 動可讓您排程何時啟動工作流程或活動。

## 使用內容 {#context-of-use}

活 **[!UICONTROL Scheduler]** 動應視為已排程的開始。 圖表中的活動定位規則與活動的定位規則相 **[!UICONTROL Start]** 同。 此活動不得具有入站轉換。

在建立工作流程時，每個分支只 **[!UICONTROL Scheduler]** 使用一個活動，並記得設定時區。 這可讓您在特定時區啟動工作流程，否則工作流程將在工作流屬性中定義的時區中執行(請參 [閱建立工作流](../../automating/using/building-a-workflow.md))。

>[!CAUTION]
>
>活 **[!UICONTROL Repetition frequency]** 動的時間不能少於10分鐘。 這表示工作流程無法每10分鐘自動執行一次以上。

**相關主題：**

* [使用案例： 在描述檔建立日期建立傳送](../../automating/using/workflow-creation-date-query.md)
* [使用案例： 建立每週二傳送的電子郵件](../../automating/using/workflow-weekly-offer.md)

## 配置 {#configuration}

1. 將活動拖放 **[!UICONTROL Scheduler]** 到工作流程中。
1. 選擇活動，然後使用顯示的快 ![](assets/edit_darkgrey-24px.png) 速操作中的按鈕將其開啟。
1. 指定 **[!UICONTROL Execution frequency]**:

   * **[!UICONTROL Once]**: 工作流只需執行一次。
   * **[!UICONTROL Several times a day]**: 工作流程會定期執行數次。 您可以在特定時間或定期設定執行。
   * **[!UICONTROL Daily]**: 工作流程會在一天中執行一次的特定時間執行。
   * **[!UICONTROL Weekly]**: 工作流程會在指定的時間執行，每週執行一次或多次。
   * **[!UICONTROL Monthly]**: 工作流程會在指定的時間執行，每月執行一次或數次。 當您需要執行工作流程時，可以選取月份。 您也可以在月份的指定工作日（例如月份的第二個星期二）設定執行。
   * **[!UICONTROL Yearly]**: 工作流程會在指定的時間執行，每年執行一次或數次。

1. 根據所選頻率定義執行詳細資訊。 詳細欄位可能會依使用的頻率（時間、重複頻率、指定天數等）而有所不同。

   >[!NOTE]
   >
   >此欄 **[!UICONTROL Repetition frequency]** 位可讓您在觸發工作流程時省下時間。 例如，如果您選取每日執行期間，而重複頻率設定為 **2** （天），則每兩天就會觸發工作流程。 不能少於10分鐘。 如果重複頻率設為 **0** （也是預設值），則不會考慮此選項，工作流將根據指定的執行頻率運行。

1. 指定執行將於何時過期：

   * **[!UICONTROL Never]**: 工作流將根據指定的頻率執行，對時間範圍或迭代次數沒有任何限制。
   * **[!UICONTROL After a certain number of iterations]**: 工作流將根據指定的頻率執行，直到達到 **X限制** 。 因此 **[!UICONTROL Number of iterations]** 需要指定。
   * **[!UICONTROL On a specific date]**: 工作流程將根據指定的頻率執行，直到特定日期為止。 因此，必須指定執行期限。

1. 按一下以檢查工作流程接下來十個執行的排程 **[!UICONTROL Preview next executions]**。

1. 在頁籤 **[!UICONTROL Execution options]** 中，在欄位中為調度程式設定時 **[!UICONTROL Time zone]** 區。

   如需依收件者時區傳送傳送的詳細資訊，請參閱本節 [或循](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md) 環工 [作流程](../../automating/using/recurring-push-notifications.md) 的範例。

1. 確認活動的設定並儲存工作流程。

## Example {#example}

在下例中，活動已配置為每週啟動工作流，每隔週一早上7點啟動工作流，但持續時間不確定。

![](assets/wkf_scheduler_example.png)

