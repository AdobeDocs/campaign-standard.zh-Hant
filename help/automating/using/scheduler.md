---
title: 排程器
description: 排程器活動可讓您在工作流程或活動啟動時進行排程。
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
ht-degree: 97%

---


# 排程器{#scheduler}

## 說明 {#description}

![](assets/scheduler.png)

**[!UICONTROL Scheduler]** 活動可讓您排程何時啟動工作流程或活動。

## 使用內容 {#context-of-use}

**[!UICONTROL Scheduler]** 活動應視為已排程的開始。圖表中的活動定位規則與活動 **[!UICONTROL Start]** 的定位規則相同。此活動不得具有入站轉變。

在建立工作流程時，每個分支只使用一個 **[!UICONTROL Scheduler]** 活動，並請記得設定時區。這可讓您在特定時區啟動工作流程，否則工作流程將在工作流程屬性中定義的時區中執行（請參閱[建立工作流程](../../automating/using/building-a-workflow.md)）。

>[!CAUTION]
>
>**[!UICONTROL Repetition frequency]** 活動的時間不能少於　10　分鐘。這表示工作流程無法每　10　分鐘自動執行多次。

**相關主題：**

* [使用案例： 在描述檔建立日期建立傳送](../../automating/using/workflow-creation-date-query.md)
* [使用案例： 建立每週二傳送的電子郵件](../../automating/using/workflow-weekly-offer.md)

## 設定 {#configuration}

1. 將 **[!UICONTROL Scheduler]** 活動拖放至工作流程中。
1. 選取活動，然後使用所顯示快速操作中的 ![](assets/edit_darkgrey-24px.png) 按鈕將其開啟。
1. 指定 **[!UICONTROL Execution frequency]**：

   * **[!UICONTROL Once]**：工作流程只需執行一次。
   * **[!UICONTROL Several times a day]**：工作流程會定期執行數次。您可以設定在特定時間或定期執行。
   * **[!UICONTROL Daily]**：工作流程會在指定的時間執行，一天一次。
   * **[!UICONTROL Weekly]**：工作流程會在指定的時間執行，每週執行一或數次。
   * **[!UICONTROL Monthly]**：工作流程會在指定的時間執行，每月執行一或數次。當您需要執行工作流程時，可以選取月份。您也可以在月份的指定工作日（例如，當月的第二個星期二）設定執行。
   * **[!UICONTROL Yearly]**：工作流程會在指定的時間執行，每年執行一次或數次。

1. 根據所選頻率定義執行詳細資訊。詳細欄位可能會依使用的頻率（時間、重複頻率、指定天數等）而有所不同。

   >[!NOTE]
   >
   >**[!UICONTROL Repetition frequency]** 欄位可讓您在觸發工作流程時省下時間。例如，如果您選取每日執行期間，而重複頻率設定為 **2**（天），則每兩天就會觸發工作流程一次。時間不能少於　10　分鐘。如果重複頻率設為 **0**（也是預設值），則不會考慮此選項，工作流程將根據指定的執行頻率運行。

1. 指定執行將於何時過期：

   * **[!UICONTROL Never]**：工作流程將根據指定的頻率執行，對時間範圍或迭代次數沒有任何限制。
   * **[!UICONTROL After a certain number of iterations]**：工作流程將根據指定的頻率執行，直到達到 **X**　限制為止。因此需要指定　**[!UICONTROL Number of iterations]**。
   * **[!UICONTROL On a specific date]**：工作流程將根據指定的頻率執行，直到特定日期為止。因此，必須指定執行期限。

1. 按一下　**[!UICONTROL Preview next executions]**，以檢查工作流程接下來十個執行的排程。

1. 在 **[!UICONTROL Execution options]** 索引標籤中，在　**[!UICONTROL Time zone]**　欄位中為排程器設定時區。

   如需根據收件者時區傳送傳送的詳細資訊，請參閱本[區段](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)或循環工作流程的[範例](../../automating/using/recurring-push-notifications.md)。

1. 確認活動的設定並儲存工作流程。

## 範例 {#example}

在在下列範例中，已將活動設定每週啟動工作流程，每隔一週的星期一上午　7:00 啟動工作流程，但持續時間不確定。

![](assets/wkf_scheduler_example.png)

