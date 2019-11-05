---
title: 開始和結束
description: 「開始」和「結束」活動可讓您清楚標示工作流程的開始和結束位置。
page-status-flag: 從未激活
uuid: 146b6337-122c-453d-8ffd-5c157db29217
contentOwner: 紹維亞
products: SG_CAMPAIGN/STANDARD
audience: 自動化
content-type: 參考
topic-tags: 執行活動
discoiquuid: a0a8a725-8ede-4626-9798-b86924b58beb
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 開始和結束{#start-and-end}

## 說明 {#description}

![](assets/start.png)

![](assets/end.png)

這些 **[!UICONTROL Start]** 和 **[!UICONTROL End]** 活動可讓您清楚標示工作流程的開始和結束位置。

## 使用內容 {#context-of-use}

執行工作流程會從沒有傳入轉移的活動開始，並在不再進行任何工作時停止。 不過，您可以新增 **[!UICONTROL Start]** 和活 **[!UICONTROL End]** 動，以清楚標示工作流程的起點和終點。 這對相對複雜的工作流程特別有用。

最好使用活動，而不 **[!UICONTROL End]** 是自行保留工作流程的最後轉場，以確保工作流程正常結束。

## 配置 {#configuration}

1. 將或活動拖 **[!UICONTROL Start]** 放至 **[!UICONTROL End]** 您的工作流程。
1. 將活 **[!UICONTROL Start]** 動放在其他活動（例如查詢）前面，並 **[!UICONTROL End]** 將活動放在一系列活動後面。
1. 選擇活動，然後使用顯示的快 ![](assets/edit_darkgrey-24px.png) 速操作中的按鈕將其開啟。
1. 您可以設定 **End** 物件，以中斷工作流程的所有持續工作，包括尚未完成的工作。 若要這麼做，請選取對應的選項。
1. 確認活動的設定並儲存工作流程。

## 觸發另一個工作流 {#triggering-another-workflow}

使用活 **[!UICONTROL External signal]** 動的標籤，您可 **[!UICONTROL End]** 以觸發另一個工作流程。 請參閱「 [External signal](../../automating/using/external-signal.md) （外部信號）」部分。

## Example {#example}

以下示例說明如何使用活動和多個活動執行 **[!UICONTROL Start]** 複雜的工 **[!UICONTROL End]** 作流。 該 **[!UICONTROL Stop all tasks in progress]** 框已檢查第一個活 **[!UICONTROL End]** 動。 對應的任務完成後，將停止整個工作流：它的效果與已選取按鈕 ![](assets/stop_darkgrey-24px.png) 相同(請參閱「動作 [列](../../automating/using/workflow-interface.md#action-bar) 」區段)。

![](assets/wkf_start_end_example.png)

