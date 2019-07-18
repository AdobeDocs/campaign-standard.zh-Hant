---
title: 開始和結束
seo-title: 開始和結束
description: 開始和結束
seo-description: 「開始」和「結束」活動可讓您清楚標示工作流程開始和結束的位置。
page-status-flag: 從未啓動
uuid: 146b6337-122c-453d-8ffd-5c157db29217
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: reference
topic-tags: 執行活動
discoiquuid: a0a8a725-8ede-4626-9798-b86924 b58 bb
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Start and end{#start-and-end}

## Description {#description}

![](assets/start.png)

![](assets/end.png)

The **[!UICONTROL Start]** and **[!UICONTROL End]** activities allow you to clearly mark where your workflow starts and ends.

## Context of use {#context-of-use}

執行工作流程是從沒有傳入過渡的活動開始，而在不再進行任何工作時停止。Nevertheless, you can add **[!UICONTROL Start]** and **[!UICONTROL End]** activities to clearly mark the starting and ending points of a workflow. 這對於相對複雜的工作流程特別有用。

It is a best practice to use an **[!UICONTROL End]** activity instead of leaving the last transition of a workflow on its own to ensure that the workflow properly ends.

## Configuration {#configuration}

1. Drag and drop a **[!UICONTROL Start]** or **[!UICONTROL End]** activity into your workflow.
1. Put the **[!UICONTROL Start]** activity in front of other activities such as queries, and the **[!UICONTROL End]** activity after a series of activities.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. You can configure the **End** object so that it interrupts all of the workflow's ongoing tasks, including those that have not finished. 若要這麼做，請選取對應的選項。
1. 確認活動的設定並儲存工作流程。

## Triggering another workflow {#triggering-another-workflow}

Using the **[!UICONTROL External signal]** tab of an **[!UICONTROL End]** activity, you can trigger another workflow. Refer to the [External signal](../../automating/using/external-signal.md) section.

## Example {#example}

The following example shows how a complex workflow is executed with a **[!UICONTROL Start]** activity and several **[!UICONTROL End]** activities. **[!UICONTROL Stop all tasks in progress]** 已檢查此方塊是否為第一 **[!UICONTROL End]** 個活動。Once the corresponding task is finished, the entire workflow will be stopped: it will have the same effect as if the ![](assets/stop_darkgrey-24px.png) button had been selected (refer to the [Action bar](../../automating/using/workflow-interface.md#action-bar) section)

![](assets/wkf_start_end_example.png)

