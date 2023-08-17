---
title: 工作流程生命週期
description: 進一步瞭解工作流程生命週期
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
role: Data Architect
level: Beginner
exl-id: ba968add-25a3-4962-9e90-f0a06d9b74a8
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 3%

---

# 工作流程生命週期 {#life-cycle}

工作流程的生命週期包括三個主要步驟，每個步驟都與狀態和顏色連結：

* **編輯** （灰色）

  這是工作流程的初始設計階段(請參閱 [建立工作流程](../../automating/using/building-a-workflow.md#creating-a-workflow))。 伺服器尚未處理工作流程，且修改工作流程沒有任何風險。

* **進行中** （藍色）

  完成初始設計階段後，即可啟動工作流程並由伺服器處理。

* **已完成** （綠色）

  一旦沒有任何正在進行的任務，或運運算元已明確停止執行個體，工作流程就會完成。

啟動之後，工作流程可能還會具有另外兩種狀態：

* **警告** （黃色）

  工作流程無法完成或已暫停使用 ![](assets/pause_darkgrey-24px.png) 或 ![](assets/check_pause_darkgrey-24px.png) 按鈕。

* **錯誤** （紅色）

  執行工作流程時發生錯誤。 工作流程已停止，使用者必須執行動作。 若要進一步瞭解此錯誤，請使用 ![](assets/printpreview_darkgrey-24px.png) 按鈕以存取工作流程記錄(請參閱 [監視](../../automating/using/monitoring-workflow-execution.md))。

行銷活動清單可讓您顯示所有工作流程及其狀態。 有關詳細資訊，請參閱 [管理行銷活動](../../start/using/marketing-activities.md#about-marketing-activities).

![](assets/wkf_execution_3.png)
