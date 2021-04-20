---
solution: Campaign Standard
product: campaign
title: 工作流程生命週期
description: 進一步瞭解工作流程生命週期
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
role: Data Architect
level: Beginner
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '204'
ht-degree: 3%

---


# 工作流程生命週期 {#life-cycle}

工作流的生命週期包括三個主要步驟，每個步驟都連結到狀態和顏色：

* **編輯** （灰色）

   這是工作流的初始設計階段（請參閱[建立工作流](../../automating/using/building-a-workflow.md#creating-a-workflow)）。 伺服器尚未處理工作流程，因此可以修改工作流程，而不會造成任何風險。

* **進行中** （藍色）

   在初始設計階段完成後，工作流程便可由伺服器啟動並處理。

* **完成** （綠色）

   當不再進行任何工作或操作員明確停止實例時，工作流即完成。

工作流程一旦啟動後，可能還會有兩個其他狀態：

* **警告** （黃色）

   工作流無法完成或使用![](assets/pause_darkgrey-24px.png)或![](assets/check_pause_darkgrey-24px.png)按鈕暫停。

* **錯誤** （紅色）

   執行工作流時發生錯誤。 工作流已停止，用戶必須執行操作。 若要進一步瞭解此錯誤，請使用![](assets/printpreview_darkgrey-24px.png)按鈕來存取工作流程記錄檔（請參閱[Monitoring](../../automating/using/monitoring-workflow-execution.md)）。

行銷活動清單可讓您顯示所有工作流程及其狀態。 如需詳細資訊，請參閱[管理行銷活動](../../start/using/marketing-activities.md#about-marketing-activities)。

![](assets/wkf_execution_3.png)
