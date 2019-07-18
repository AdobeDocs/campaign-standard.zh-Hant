---
title: 等候等
seo-title: 等候等
description: 等候等
seo-description: 「等候」活動會在工作流程中停止執行部分動作。
page-status-flag: 從未啓動
uuid: 396a3de1-6ffa-4385-ac9 f-15fdeae5 a366
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: reference
topic-tags: 執行活動
discoiquuid: 377821e6-69f8-41cc-a1 ad-8a2 f5 ed4 d409
context-tags: 等候，主要
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e384a0cef325bc01eb5ea050b0f3d926aea9a88f

---


# Wait{#wait}

## Description {#description}

![](assets/wait.png)

**[!UICONTROL Wait]** 活動偶爾會停止執行工作流程的部分。它會在延遲後的幾秒鐘內啓動其傳出轉場，此延遲可能會在數秒到數個月後執行。

## Context of use {#context-of-use}

**[!UICONTROL Wait]** 活動用於允許執行兩個活動之間的特定時間長度。例如，在發送電子郵件活動後等候數天，接著分析在此期間產生的開啓和點擊次數，然後執行任何後續操作(提醒電子郵件、建立觀眾等)。

## Configuration {#configuration}

1. Drag and drop a **[!UICONTROL Wait]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. Specify the **[!UICONTROL Duration]** of the wait between when the inbound and outbound transitions of the activity are activated.

   您可以手動輸入持續時間，或使用欄位中可用的選擇器。

   ![](assets/wait_duration.png)

1. 確認活動的設定並儲存工作流程。

## Example {#example}

The following example illustrates the **[!UICONTROL Wait]** activity in a typical use case. 傳送活動的電子郵件邀請。傳送後24小時內，會分析電子郵件傳送記錄，並傳送提醒電子郵件給收到第一封電子郵件但未註冊的人員。

工作流程的呈現方式如下：

![](assets/wait_example_workflow.png)

* A first **[!UICONTROL Query]** targets the profiles that will be sent the email invitation.
* An **[!UICONTROL Email delivery]** sends the invitation for the first time to the profiles selected.
* A **[!UICONTROL Wait]** activity of 24h places a pause between when the invitation was sent and the rest of the workflow.
* A second **[!UICONTROL Query]** targets the profiles that received the first email but did not click on the subscription link inside.
* A second **[!UICONTROL Email delivery]** sends a reminder of the invitation to the people selected.

