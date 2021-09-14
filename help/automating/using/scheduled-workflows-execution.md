---
title: 排程工作流程的重疊執行
description: 了解如何防止排程工作流程的重疊執行。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 8d9820a4-3c44-45f5-815e-4ed48a96276d
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 1%

---

# 排程工作流程的重疊執行{#preventing-overlapping-execution-of-scheduled-workflows}

## 關於排程的工作流程執行

在Campaign Standard中，工作流引擎保證只有一個進程執行工作流實例。 封鎖活動（如匯入、長時間執行的查詢或寫入資料庫）會在執行時防止執行任何其他任務。

另一方面，非封鎖活動不會封鎖其他工作的執行（通常是等候事件的活動，例如&#x200B;**[!UICONTROL Scheduler]**&#x200B;活動）。

這可能會導致一種情況，即使上次執行相同的工作流程尚未完成，基於排程的工作流程也可能開始執行，這可能導致非預期的資料問題。

因此，在設計包括多個活動的排程工作流程時，您必須確定在工作流程完成之前不會重新排程工作流程。 若要這麼做，您必須設定工作流程，以在先前執行的一或多個任務仍擱置時防止其執行。

## 設定工作流程

若要檢查上一個工作流程執行中的一或多個任務是否仍待執行，您需要使用&#x200B;**[!UICONTROL Query]**&#x200B;和&#x200B;**[!UICONTROL Test]**&#x200B;活動。

1. 在&#x200B;**[!UICONTROL Scheduler]**&#x200B;活動後新增&#x200B;**[!UICONTROL Query]**&#x200B;活動，然後依照下列方式進行設定。

1. 將活動的資源變更為&#x200B;**[!UICONTROL WorkflowTaskDetail]**，這表示它將定位工作流程的目前任務。

   ![](assets/scheduled-wkf-resource.png)

1. 使用下列規則設定查詢：

   ![](assets/scheduled-wkf-query.png)

   * 第一個規則會篩選掉當前任務(query2)以及屬於當前工作流的下一個計畫任務(schedule2)。

      >[!NOTE]
      >
      >當&#x200B;**[!UICONTROL Scheduler]**&#x200B;活動啟動時，它會立即添加另一個計畫任務以在下一個計畫時間運行，並啟動工作流。 因此，從先前的執行中尋找待定任務時，請務必篩選查詢和排程任務。

   * 第二個規則確定來自工作流先前運行的任何任務是否仍處於活動狀態（掛起），該狀態對應於0執行狀態。

1. 新增&#x200B;**[!UICONTROL Test]**&#x200B;活動，以檢查&#x200B;**[!UICONTROL Query]**&#x200B;活動傳回的待定任務數。 若要這麼做，請設定兩個出站轉變。

   ![](assets/scheduled-wkf-test.png)

   * 如果沒有待定任務，則第一個轉變會繼續執行工作流程，
   * 如果有任何待定任務，第二個轉變會取消工作流執行。

   ![](assets/scheduled-wkf-workflow.png)

您現在可以視需要設定其餘的工作流程。 如果工作流程執行因待定任務而取消，當工作流程依排程再次執行時，可以執行這些步驟。 這將確保只有在上一個執行沒有作用中（擱置中）任務時，工作流程執行才會繼續。
