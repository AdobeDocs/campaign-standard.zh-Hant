---
title: 執行命令
description: 了解如何使用工作流程執行命令。
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
ht-degree: 2%

---

# 執行命令 {#execution-commands}

動作列中的圖示可讓您啟動、追蹤及修改工作流程的執行。 請參閱[動作列](../../automating/using/workflow-interface.md#action-bar)。

![](assets/wkf_execution_2.png)

可用的動作如下：

**開始**

![](assets/play_darkgrey-24px.png)按鈕開始執行工作流，然後進入&#x200B;**進行中**（藍色）狀態。 如果工作流程已暫停，則會繼續，否則會啟動，然後啟動初始活動。

>[!NOTE]
>
>啟動是非同步程式：系統會儲存要求，並盡快由工作流程執行引擎處理。

**暫停**

![](assets/pause_darkgrey-24px.png)按鈕暫停執行。 工作流程會進入&#x200B;**警告**（黃色）狀態。 新活動在恢復之前不會激活，但正在進行的操作不會暫停。

**停止**

![](assets/stop_darkgrey-24px.png)按鈕會停止正在執行的工作流程，然後進行&#x200B;**已完成**（綠色）狀態。 正在進行的操作會被中斷（如果可能），並且正在進行的導入或SQL查詢會立即取消。 您無法從停止的同一位置繼續工作流程。

**重新啟動**

![](assets/pauseplay_darkgrey-24px.png)按鈕涉及停止，然後重新啟動工作流。 在大多數情況下，這可讓您更快地重新啟動。 在停止後自動重新啟動需要一定的時間，這也很有用，因為![](assets/play_darkgrey-24px.png)按鈕僅在停止有效時才可用。

選取工作流程中的一或多個活動時，您可以執行其他動作，例如：

**立即執行**

![](assets/pending_darkgrey-24px.png)按鈕會盡快啟動所有選取的待定活動。

**正常執行**

![](assets/check_darkgrey-24px.png)按鈕會重新啟用任何已暫停或已停用的活動。

**已暫停執行**

![](assets/check_pause_darkgrey-24px.png)按鈕會在選取的活動上暫停工作流程：不會執行此任務以及其後面的所有任務（在同一分支中）。

**未執行**

![](assets/checkdisable.png)按鈕會停用所有選取的活動。

>[!NOTE]
>
>快速動作可讓您存取有關某個特定活動的不同動作，並在選取活動時顯示。
