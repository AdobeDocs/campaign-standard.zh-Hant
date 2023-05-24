---
title: 工作流程生命週期
description: 瞭解有關工作流生命週期的詳細資訊
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

   這是工作流的初始設計階段(請參閱 [建立工作流](../../automating/using/building-a-workflow.md#creating-a-workflow))。 伺服器尚未處理工作流，因此可以在不帶任何風險的情況下進行修改。

* **正在進行** （藍色）

   初始設計階段完成後，可以啟動工作流並由伺服器處理。

* **已完成** （綠色）

   當不再執行任何任務或操作員明確停止實例時，工作流即完成。

一旦啟動，工作流還可能具有以下兩種狀態：

* **警告** （黃色）

   工作流無法完成或已使用 ![](assets/pause_darkgrey-24px.png) 或 ![](assets/check_pause_darkgrey-24px.png) 按鈕。

* **錯誤** （紅色）

   執行工作流時出錯。 工作流已停止，用戶必須執行操作。 要瞭解有關此錯誤的詳細資訊，請使用 ![](assets/printpreview_darkgrey-24px.png) 按鈕訪問工作流日誌(請參閱 [監視](../../automating/using/monitoring-workflow-execution.md))。

市場營銷活動清單允許您顯示所有工作流及其狀態。 有關此的詳細資訊，請參閱 [管理市場營銷活動](../../start/using/marketing-activities.md#about-marketing-activities)。

![](assets/wkf_execution_3.png)
