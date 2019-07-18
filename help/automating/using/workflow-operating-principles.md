---
title: 工作流程作業原則
seo-title: 工作流程作業原則
description: 工作流程作業原則
seo-description: 瞭解工作流程的主要層面。
page-status-flag: 從未啓動
uuid: 85755e85-617b-4a9b-bb30-96BA8333 f4 f0
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: reference
topic-tags: 關於工作流程與資料管理
discoiquuid: 3a13785d-1ef7-4043-9927-2d495b83709f
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Workflow operating principles{#workflow-operating-principles}

A workflow is a **sequence of configurable activities**. 每個活動在程序中都有特定角色。The result of each activity is forwarded to the following activity by a **transition**, represented by an arrow.

某個活動與另一個活動之間交換的資料類型會影響下列活動的設定方式。例如，如果訪客是在電子郵件傳送活動之前建立的，則可作為該電子郵件的目標。

您可以開啓活動來檢查或編輯工作流程之前或之後的參數。

您可以開啓轉場，檢查傳送的資料在執行工作流程期間或之後是否正確。To access the detail view of the transitions, you have to check the **[!UICONTROL Keep interim results]** option in the **[!UICONTROL Execution]** section of the workflow properties.

![](assets/workflow_overview.png)

