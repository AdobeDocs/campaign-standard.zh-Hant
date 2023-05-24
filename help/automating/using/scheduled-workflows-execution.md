---
title: 排程工作流程的重疊執行
description: 瞭解如何防止重疊執行計畫的工作流。
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

## 關於計畫的工作流執行

在Campaign Standard中，工作流引擎保證只由一個進程執行工作流實例。 阻止導入、長時間運行的查詢或寫入資料庫等活動會阻止在運行時執行任何其他任務。

另一方面，非阻塞活動不會阻止其他任務的執行(通常是等待事件的活動，如 **[!UICONTROL Scheduler]** )。

這可能會導致一種情況，即使同一工作流的上一次運行尚未完成，基於計畫的工作流也可以開始執行，這可能會導致意外的資料問題。

因此，在設計包含多個活動的計畫工作流時，您需要確保在工作流完成之前不會重新計畫該工作流。 為此，您需要配置工作流，以便在先前執行中的一個或多個任務仍處於掛起狀態時防止執行該工作流。

## 配置工作流

要檢查上一工作流執行中的一個或多個任務是否仍處於掛起狀態，您需要使用 **[!UICONTROL Query]** 和 **[!UICONTROL Test]** 的子菜單。

1. 添加 **[!UICONTROL Query]** 活動 **[!UICONTROL Scheduler]** 活動，然後按如下方式配置。

1. 將活動的資源更改為 **[!UICONTROL WorkflowTaskDetail]**，這意味著它將針對工作流的當前任務。

   ![](assets/scheduled-wkf-resource.png)

1. 使用以下規則配置查詢：

   ![](assets/scheduled-wkf-query.png)

   * 第一個規則過濾掉當前任務(query2)以及屬於當前工作流的下一個計畫任務(schedule2)。

      >[!NOTE]
      >
      >當 **[!UICONTROL Scheduler]** 活動啟動後，它立即添加另一個計畫任務以在下一個計畫時間運行並啟動工作流。 因此，在從上一執行中查找待執行任務時，必須同時篩選查詢和計畫任務。

   * 第二規則確定工作流上一運行中的任何任務是否仍然處於活動狀態（掛起），這對應於0執行狀態。

1. 添加 **[!UICONTROL Test]** 活動，以檢查 **[!UICONTROL Query]** 的子菜單。 為此，請配置兩個出站過渡。

   ![](assets/scheduled-wkf-test.png)

   * 如果沒有掛起的任務，則第一個轉換將繼續執行工作流。
   * 如果存在任何掛起任務，則第二個轉換將取消工作流執行。

   ![](assets/scheduled-wkf-workflow.png)

現在，您可以根據需要配置工作流的其餘部分。 如果由於掛起任務而取消工作流執行，則當工作流按照計畫再次運行時，它可以完成這些步驟。 這將確保只有在先前執行中沒有活動（掛起）任務時，工作流執行才會繼續。
