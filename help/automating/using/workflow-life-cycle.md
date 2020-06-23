---
title: 工作流程生命週期
description: 進一步瞭解工作流程生命週期
page-status-flag: never-activated
uuid: ff02b74e-53e8-49c6-bf8e-0c729eaa7d25
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
discoiquuid: 906c85ea-83b7-4268-86da-cd353f1dc591
context-tags: workflow,overview;workflow,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b4d0aa1a9f116f022890d5eccd87730a7a513103
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 0%

---


# 工作流程生命週期 {#life-cycle}

工作流的生命週期包括三個主要步驟，每個步驟都連結到狀態和顏色：

* **編輯** （灰色）

   這是工作流的初始設計階段(請參閱「建 [立工作流](../../automating/using/building-a-workflow.md#creating-a-workflow)」)。 伺服器尚未處理工作流程，因此可以修改工作流程，而不會造成任何風險。

* **進行中** （藍色）

   在初始設計階段完成後，工作流程便可由伺服器啟動並處理。

* **完成** （綠色）

   當不再進行任何工作或操作員明確停止實例時，工作流即完成。

工作流程一旦啟動後，可能還會有兩個其他狀態：

* **警告** （黃色）

   工作流無法完成或使用或按鈕 ![](assets/pause_darkgrey-24px.png) 暫停 ![](assets/check_pause_darkgrey-24px.png) 。

* **錯誤** （紅色）

   執行工作流時發生錯誤。 工作流已停止，用戶必須執行操作。 若要進一步瞭解此錯誤，請使用 ![](assets/printpreview_darkgrey-24px.png) 按鈕存取工作流程記錄檔(請參 [閱Monitoring](../../automating/using/monitoring-workflow-execution.md))。

行銷活動清單可讓您顯示所有工作流程及其狀態。 如需詳細資訊，請參閱管 [理行銷活動](../../start/using/marketing-activities.md#about-marketing-activities)。

![](assets/wkf_execution_3.png)
