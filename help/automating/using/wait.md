---
title: 等待
description: 「等待」活動會暫時暫停執行工作流的一部分。
page-status-flag: 從未激活
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: 紹維亞
products: SG_CAMPAIGN/STANDARD
audience: 自動化
content-type: 參考
topic-tags: 執行活動
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: 等待，主
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 等待{#wait}

## 說明 {#description}

![](assets/wait.png)

活 **[!UICONTROL Wait]** 動暫時暫停執行工作流的一部分。 它會在延遲後啟動其出站轉移，延遲範圍可能在幾秒到幾個月之間，然後執行之後放置的活動。

## 使用內容 {#context-of-use}

活動 **[!UICONTROL Wait]** 用於允許在正在執行的兩個活動之間傳遞一定時間。 例如，若要在電子郵件傳送活動後等候數天，請先分析此期間產生的開啟次數和點按次數，再執行任何後續操作（提醒電子郵件、建立對象等）。

## 配置 {#configuration}

1. 將活動拖放 **[!UICONTROL Wait]** 至工作流程。
1. 選擇活動，然後使用顯示的快 ![](assets/edit_darkgrey-24px.png) 速操作中的按鈕將其開啟。
1. 指定 **[!UICONTROL Duration]** 活動的入站和出站轉換何時啟動的等待。

   您可以手動輸入持續時間或使用欄位中可用的選擇器。

   ![](assets/wait_duration.png)

1. 確認活動的設定並儲存工作流程。

## Example {#example}

以下示例說明了 **[!UICONTROL Wait]** 典型使用案例中的活動。 系統會傳送電子郵件邀請至事件。 在傳送電子郵件後24小時，會分析電子郵件傳送記錄，並傳送提醒電子郵件給收到第一封電子郵件但未註冊的人。

工作流程如下：

![](assets/wait_example_workflow.png)

* 第一個 **[!UICONTROL Query]** 目標是將會傳送電子郵件邀請的設定檔。
* 第 **[!UICONTROL Email delivery]** 一次將邀請發送到選定的配置檔案。
* 24 **[!UICONTROL Wait]** 小時的活動會在傳送邀請與工作流程的其餘時間之間暫停。
* 第二個 **[!UICONTROL Query]** 目標是收到第一封電子郵件但未點按內部訂閱連結的描述檔。
* 第二 **[!UICONTROL Email delivery]** 個將邀請的提醒發送給選定的人。

