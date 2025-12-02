---
title: 排程工作流程的重疊執行
description: 瞭解如何防止排程工作流程的重複執行。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 8d9820a4-3c44-45f5-815e-4ed48a96276d
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '423'
ht-degree: 1%

---

# 排程工作流程的重疊執行{#preventing-overlapping-execution-of-scheduled-workflows}

## 關於排程的工作流程執行

在Campaign Standard中，工作流程引擎可確保工作流程例項僅由一個程式執行。 封鎖匯入、長時間執行查詢或寫入資料庫等活動會導致執行時無法執行任何其他工作。

另一方面，非封鎖活動不會封鎖其他工作的執行(通常是等待事件（例如&#x200B;**[!UICONTROL Scheduler]**&#x200B;活動）的活動)。

這可能會導致這樣一種情況：即使相同工作流程的上次執行尚未完成，排程型工作流程仍可以開始執行，可能會導致未預期的資料問題。

因此，在設計包含多個活動的已排程工作流程時，您需要確保工作流程在完成前不會重新排程。 若要這麼做，您需要設定工作流程，以防止其在先前執行的一或多個任務仍擱置時執行。

## 設定工作流程

若要檢查先前工作流程執行的一或多個任務是否仍在擱置中，您需要使用&#x200B;**[!UICONTROL Query]**&#x200B;和&#x200B;**[!UICONTROL Test]**&#x200B;活動。

1. 在&#x200B;**[!UICONTROL Query]**&#x200B;活動之後新增&#x200B;**[!UICONTROL Scheduler]**&#x200B;活動，然後如下所示設定。

1. 將活動的資源變更為&#x200B;**[!UICONTROL WorkflowTaskDetail]**，這表示它將以工作流程的目前任務為目標。

   ![](assets/scheduled-wkf-resource.png)

1. 使用下列規則設定查詢：

   ![](assets/scheduled-wkf-query.png)

   * 第一個規則會篩選出目前工作(query2)以及屬於目前工作流程的下一個排程工作(schedule2)。

     >[!NOTE]
     >
     >當&#x200B;**[!UICONTROL Scheduler]**&#x200B;活動啟動時，它會立即新增另一個排程工作，以便在下一個排程時間執行並啟動工作流程。 因此，在尋找先前執行的擱置任務時，請務必篩選查詢以及排程任務。

   * 第二個規則會判斷先前執行的工作流程是否有任何工作仍在進行中（擱置中），這與0執行狀態相對應。

1. 新增&#x200B;**[!UICONTROL Test]**&#x200B;活動，以檢查&#x200B;**[!UICONTROL Query]**&#x200B;活動傳回的擱置任務數目。 為此，請設定兩個出站轉變。

   ![](assets/scheduled-wkf-test.png)

   * 如果沒有擱置中的任務，則第一個轉變會繼續執行工作流程。
   * 如果有任何擱置中的任務，第二個轉變會取消工作流程執行。

   ![](assets/scheduled-wkf-workflow.png)

您現在可以根據需要設定工作流程的其餘部分。 如果工作流程執行因待定任務而取消，則當工作流程按排程再次執行時，它可以完成這些步驟。 這將確保只有在先前執行中沒有作用中（擱置）任務時，工作流程執行才會繼續。
