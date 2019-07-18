---
title: 排程器
seo-title: 排程器
description: 排程器
seo-description: 排程器活動可讓您在工作流程或活動開始時排程。
page-status-flag: 從未啓動
uuid: f5e50a11-8dc9-4d98-9531-024c0fb3f7da
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: reference
topic-tags: 執行活動
discoiquuid: 0fb16ca-3941-404f-899c-33f81ced4ed5
context-tags: 排程，主要
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e3a627376a91eb394aea90b1d94c7958ad77fd40

---


# Scheduler{#scheduler}

## Description {#description}

![](assets/scheduler.png)

**[!UICONTROL Scheduler]** 活動可讓您在工作流程或活動開始時排程。

## Context of use {#context-of-use}

**[!UICONTROL Scheduler]** 活動應視為排程開始。The activity positioning rules within the chart are the same as for the **[!UICONTROL Start]** activity. 此活動不得有傳入轉場。

When building your workflow, only use one **[!UICONTROL Scheduler]** activity per branch and remember to set a time zone. 它會設定為在伺服器時區執行。

>[!CAUTION]
>
>The **[!UICONTROL Repetition frequency]** of the activity cannot be less than 10 minutes. 這表示工作流程每10分鐘無法自動執行一次。

## Configuration {#configuration}

1. Drag and drop a **[!UICONTROL Scheduler]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. Specify the **[!UICONTROL Execution frequency]**:

   * **[!UICONTROL Once]**：工作流程會執行一次。
   * **[!UICONTROL Several times a day]**：工作流程會定期執行數次。您可以在特定時間或定期設定執行。
   * **[!UICONTROL Daily]**：工作流程會在特定時間執行一次。
   * **[!UICONTROL Weekly]**：工作流程會在指定時間的一或幾天執行。
   * **[!UICONTROL Monthly]**：工作流程會在指定的時間執行一次或數次。當您需要執行工作流程時，可以選取月份。您也可以在指定的工作日內設定執行，例如當月的第二個星期二。
   * **[!UICONTROL Yearly]**：工作流程會在指定的時間執行一次或數次。

1. 根據選取的頻率定義執行詳細資料。詳細資料欄位可能會視使用頻率(時間、重復頻率、指定日期等)而有所不同。

   >[!NOTE]
   >
   >**[!UICONTROL Repetition frequency]** 欄位可讓您將工作流程觸發的時間縮小。For example, if you select a daily execution period and the repetition frequency is set at **2** (days), the workflow will be triggered every two days. 不能少於10分鐘。If the repetition frequency is set at **0** (also the default value), this option is not taken into account and the workflow will run according to the execution frequency specified.

1. 指定何時執行過期：

   * **[!UICONTROL Never]**：工作流程會根據指定的頻率執行，而不會限制時間範圍或重復的次數。
   * **[!UICONTROL After a certain number of iterations]**：工作流程會根據指定的頻率執行，直到達到 **X** 的限制為止。**[!UICONTROL Number of iterations]** 因此必須指定此項目。
   * **[!UICONTROL On a specific date]**：工作流程會根據指定的頻率執行，直到特定日期為止。因此，必須指定執行期限。

1. Check the schedule of the next ten executions of your workflow by clicking **[!UICONTROL Preview next executions]**.

1. **[!UICONTROL Execution options]** 在標籤中，設定 **[!UICONTROL Time zone]** 欄位中排程器的時區。這可讓您在特定時區開始工作流程，否則工作流程預設會在伺服器時區中執行。

   For more information on sending delivery depending on the recipient's time zone, refer to this [section](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md) or this [example](../../automating/using/push-notification-delivery.md#sending-a-recurring-push-notification-with-a-workflow) of a recurring workflow.

1. 確認活動的設定並儲存工作流程。

## Example {#example}

在下列範例中，設定活動會在每周的基礎上開始工作流程，每周是早上7：00，而不是決定持續時間。

![](assets/wkf_scheduler_example.png)

