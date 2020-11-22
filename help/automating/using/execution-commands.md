---
solution: Campaign Standard
product: campaign
title: 執行命令
description: 瞭解如何使用工作流程執行命令。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 2%

---


# 執行命令 {#execution-commands}

動作列中的圖示可讓您啟動、追蹤和修改工作流程的執行。 請參閱 [動作列](../../automating/using/workflow-interface.md#action-bar)。

![](assets/wkf_execution_2.png)

可用操作如下：

**開始**

按 ![](assets/play_darkgrey-24px.png) 鈕會開始執行工作流程，然後進入 **「進行中** （藍色）」狀態。 如果暫停了工作流，則會繼續它，否則會啟動它，然後啟動初始活動。

>[!NOTE]
>
>啟動是非同步程式：請求會儲存，並會由工作流程執行引擎盡快處理。

**暫停**

按 ![](assets/pause_darkgrey-24px.png) 鈕會暫停執行。 工作流程會顯示 **警告** （黃色）狀態。 新活動在恢復之前不會激活，但正在進行的操作不會暫停。

**停止**

按 ![](assets/stop_darkgrey-24px.png) 鈕會停止正在執行的工作流程，然後會進入「完 **成** （綠色）」狀態。 如果可能，將中斷正在進行的操作，並立即取消正在進行的導入或SQL查詢。 您無法從停止的工作流程所在位置繼續。

**重新啟動**

此按 ![](assets/pauseplay_darkgrey-24px.png) 鈕包括停止，然後重新啟動工作流。 在大多數情況下，這可讓您更快速地重新啟動。 當停止需要一定時間時，自動重新啟動也會很有用，因為只有在停止有效時， ![](assets/play_darkgrey-24px.png) 按鈕才可用。

在選擇工作流中的一個或多個活動時，您可以執行其他操作，例如：

**立即執行**

此按 ![](assets/pending_darkgrey-24px.png) 鈕會盡快啟動所有選取的待定活動。

**正常執行**

按鈕 ![](assets/check_darkgrey-24px.png) 會重新啟動任何暫停或停用的活動。

**已暫停執行**

按鈕 ![](assets/check_pause_darkgrey-24px.png) 會暫停所選活動的工作流：不會執行此任務以及隨後執行的所有任務（位於同一個分支中）。

**無執行**

按鈕 ![](assets/checkdisable.png) 會停用任何選取的活動。

>[!NOTE]
>
>快速動作可讓您存取與某個特定活動相關的不同動作，並在選取活動時顯示。
