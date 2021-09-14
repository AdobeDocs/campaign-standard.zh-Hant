---
title: 工作流程生命週期
description: 深入了解工作流程生命週期
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

工作流的生命週期包括三個主要步驟，每個步驟都連結到狀態和顏色：

* **編輯** （灰色）

   這是工作流的初始設計階段（請參閱[建立工作流](../../automating/using/building-a-workflow.md#creating-a-workflow)）。 伺服器尚未處理工作流程，可以修改而無任何風險。

* **進行中** （藍色）

   完成初始設計階段後，即可啟動工作流程並由伺服器處理。

* **已完成** （綠色）

   當不再進行任何工作或運算子明確停止執行個體時，工作流程就會完成。

工作流程一旦啟動後，可能還會有其他兩種狀態：

* **警告** （黃色）

   無法使用![](assets/pause_darkgrey-24px.png)或![](assets/check_pause_darkgrey-24px.png)按鈕完成或暫停工作流。

* **錯誤** （紅色）

   執行工作流時出錯。 工作流程已停止，使用者必須執行動作。 要了解有關此錯誤的詳細資訊，請使用![](assets/printpreview_darkgrey-24px.png)按鈕訪問工作流日誌（請參閱[監視](../../automating/using/monitoring-workflow-execution.md)）。

行銷活動清單可讓您顯示所有工作流程及其狀態。 如需詳細資訊，請參閱[管理行銷活動](../../start/using/marketing-activities.md#about-marketing-activities)。

![](assets/wkf_execution_3.png)
