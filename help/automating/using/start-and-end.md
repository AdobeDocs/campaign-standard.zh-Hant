---
solution: Campaign Standard
product: campaign
title: 開始和結束
description: 「開始」和「結束」活動可讓您清楚標示工作流程的開始和結束位置。
audience: automating
content-type: reference
topic-tags: execution-activities
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 100%

---


# 開始和結束{#start-and-end}

## 說明 {#description}

![](assets/start.png)

![](assets/end.png)

**[!UICONTROL Start]** 和 **[!UICONTROL End]** 活動可讓您清楚標示工作流程的開始和結束位置。

## 使用內容 {#context-of-use}

執行工作流程會從沒有入站轉變的活動開始進行，而且會在不再進行任何任務時停止。不過，您可以新增 **[!UICONTROL Start]** 及 **[!UICONTROL End]** 活動，以清楚標示工作流程的起點和終點。這對相對複雜的工作流程特別實用。

最佳實務是使用　**[!UICONTROL End]**　活動，而不是自行保留工作流程的最後轉變，以確保工作流程正常結束。

## 設定 {#configuration}

1. 將 **[!UICONTROL Start]** 或 **[!UICONTROL End]** 活動拖放置您的工作流程中。
1. 將 **[!UICONTROL Start]** 活動放在其他活動（例如查詢）前面，並在一系列活動後面放置 **[!UICONTROL End]** 活動。
1. 選取活動，然後使用所顯示快速操作中的 ![](assets/edit_darkgrey-24px.png) 按鈕將其開啟。
1. 您可以設定 **End** 物件，以中斷所有持續進行的工作流程任務，包括尚未完成的任務。若要這麼做，請選取相對應的選項。
1. 確認活動的設定並儲存工作流程。

## 觸發另一個工作流程 {#triggering-another-workflow}

使用 **[!UICONTROL External signal]** 活動的　**[!UICONTROL End]**　標籤，您可以觸發另一個工作流程。請參閱[外部訊號](../../automating/using/external-signal.md)區段。

## 範例 {#example}

以下範例說明如何使用　**[!UICONTROL Start]**　活動和數個　**[!UICONTROL End]**　活動執行複雜的工作流程。已針對第一個 **[!UICONTROL End]** 活動核取　**[!UICONTROL Stop all tasks in progress]**　方塊。完成相對應的任務之後，將會停止整個工作流程：其效果與已選取 ![](assets/stop_darkgrey-24px.png) 按鈕相同（請參閱[動作列](../../automating/using/workflow-interface.md#action-bar)區段）。

![](assets/wkf_start_end_example.png)

