---
title: 執行命令
description: 瞭解如何使用工作流執行命令。
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
ht-degree: 3%

---

# 執行命令 {#execution-commands}

操作欄中的表徵圖允許您啟動、跟蹤和修改工作流的執行。 請參閱 [操作欄](../../automating/using/workflow-interface.md#action-bar)。

![](assets/wkf_execution_2.png)

可用操作如下：

**開始**

的 ![](assets/play_darkgrey-24px.png) 按鈕開始執行工作流，然後 **正在進行** （藍色）狀態。 如果工作流已暫停，則它將繼續，否則它將啟動，初始活動將被激活。

>[!NOTE]
>
>啟動是一個非同步進程：該請求將被保存，並將盡快由工作流執行引擎處理。

**暫停**

的 ![](assets/pause_darkgrey-24px.png) 按鈕暫停執行。 工作流將 **警告** （黃色）狀態。 在恢復新活動之前，不會激活新活動，但不會暫停正在進行的操作。

**停止**

的 ![](assets/stop_darkgrey-24px.png) 按鈕將停止正在執行的工作流，然後該工作流將 **已完成** （綠色）狀態。 如果可能，將中斷正在進行的操作，並立即取消導入或正在進行的SQL查詢。 無法從工作流停止的位置恢復。

**重新啟動**

的 ![](assets/pauseplay_darkgrey-24px.png) 按鈕涉及停止，然後重新啟動工作流。 在大多數情況下，這允許您更快地重新啟動。 在停止後自動重新啟動也會很有用，因為 ![](assets/play_darkgrey-24px.png) 按鈕僅在停止生效時可用。

選擇工作流中的一個或多個活動後，您可以執行其他操作，例如：

**立即執行**

的 ![](assets/pending_darkgrey-24px.png) 按鈕將盡快啟動所有選定的掛起活動。

**正常執行**

的 ![](assets/check_darkgrey-24px.png) 按鈕將重新激活任何已暫停或已停用的活動。

**已暫停執行**

的 ![](assets/check_pause_darkgrey-24px.png) 按鈕將工作流暫停到選定的活動：不執行此任務以及其後面的所有任務（在同一分支中）。

**無執行**

的 ![](assets/checkdisable.png) 按鈕將停用所有選定的活動。

>[!NOTE]
>
>快速操作允許您訪問與某個特定活動有關的不同操作，並在選定活動時顯示。
