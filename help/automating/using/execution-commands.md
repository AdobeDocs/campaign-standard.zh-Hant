---
title: 執行命令
description: 瞭解如何使用工作流程執行命令。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
role: Data Architect
level: Beginner
exl-id: fddd88b1-603a-465b-b5e7-624632c0d5cd
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 1%

---

# 執行命令 {#execution-commands}

動作列中的圖示可讓您啟動、追蹤及修改工作流程的執行。 請參閱[動作列](../../automating/using/workflow-interface.md#action-bar)。

![](assets/wkf_execution_2.png)

可用的動作如下：

**開始**

![](assets/play_darkgrey-24px.png)按鈕開始執行工作流程，接著會呈現&#x200B;**進行中** （藍色）狀態。 如果工作流程已暫停，則會繼續進行，否則會啟動工作流程並啟動初始活動。

>[!NOTE]
>
>啟動為非同步流程：系統會儲存請求，並儘快由工作流程執行引擎處理。

**暫停**

![](assets/pause_darkgrey-24px.png)按鈕會暫停執行。 工作流程會採用&#x200B;**警告** （黃色）狀態。 在繼續之前，不會啟用任何新活動，但不會暫停進行中的作業。

**停止**

![](assets/stop_darkgrey-24px.png)按鈕會停止正在執行的工作流程，而工作流程則會呈現&#x200B;**已完成** （綠色）狀態。 如果可能的話，進行中的作業會中斷，而且會立即取消匯入或進行中的SQL查詢。 您無法從工作流程停止的同一位置繼續。

**重新啟動**

![](assets/pauseplay_darkgrey-24px.png)按鈕涉及停止然後重新啟動工作流程。 在大多數情況下，這可讓您更快速地重新啟動。 當停止需要一定的時間時，自動重新啟動也會很有用，因為![](assets/play_darkgrey-24px.png)按鈕只有在停止有效時才可用。

在選取工作流程中的一或多個活動時，您可以執行其他動作，例如：

**立即執行**

「![](assets/pending_darkgrey-24px.png)」按鈕會儘快啟動所有選取的擱置活動。

**正常執行**

![](assets/check_darkgrey-24px.png)按鈕可重新啟用任何暫停或停用的活動。

**執行已暫停**

![](assets/check_pause_darkgrey-24px.png)按鈕在選取的活動中暫停工作流程：此任務及其後面的所有任務（在相同分支中）都不會執行。

**沒有執行**

![](assets/checkdisable.png)按鈕會停用任何選取的活動。

>[!NOTE]
>
>快速動作可讓您存取與某個特定活動相關的不同動作，並在選取活動時顯示。
