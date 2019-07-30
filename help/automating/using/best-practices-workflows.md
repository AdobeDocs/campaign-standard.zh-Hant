---
title: 工作流程最佳實務
seo-title: 工作流程最佳實務
description: 工作流程最佳實務
seo-description: 瞭解如何套用最佳實務以套用至您的工作流程。
page-status-flag: 從未啓動
uuid: ff02b74e-53e8-49c6-bc8 e-0c729 ea7 d25
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: reference
topic-tags: 工作流程一般運作
context-tags: 工作流程，概觀；工作流程，主要
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e02ca92032c298fe1b5dbc7094de201d0a106be5

---


# Workflow best practices{#workflow-best-practices}

透過Adobe Campaign，您可以設定所有工作流程，以執行大型工作範圍。但是，在設計和執行工作流程時，您必須格外小心，因為錯誤實作可能導致不良效能、錯誤和平台問題。以下列出最佳實務和疑難排解提示的清單。

>[!NOTE]
>
>工作流程設計和執行必須由Adobe Campaign進階使用者執行。

## Naming{#naming}

為了簡化工作流程疑難排解，Adobe建議您明確命名工作流程並標示其標記。填寫工作流程的說明欄位，以摘要執行的程序，讓營運商輕鬆瞭解。
如果工作流程是涉及多個工作流程的程序的一部分，您可以在輸入標籤時使用數字來清楚排序。

例如：

* 001-匯入-匯入收件者
* 002-匯入-匯入銷售
* 003-匯入-匯入銷售詳細資料
* 010-出口-出口記錄檔
* 2011-匯出-匯出追蹤記錄

## Duplicating workflows{#duplicating-workflows}

您可以複製工作流程。In the **[!UICONTROL Marketing Activities]**, hover over the workflow and click **[!UICONTROL Duplicate element]**. 複製之後，工作流程的修改不會被帶入工作流程的副本。您可以編輯工作流程的復本。

![](assets/duplicating_workflow.png)

## Execution{#execution}

### 工作流程數目

根據預設，我們建議不要同時執行超過20個作用中的工作流程。達到此限制後，工作流程將會佇列，以不影響效能。同樣地，Adobe建議您逐步擴展您的工作流程效能。
在特定內容中，您可能需要執行超過20個工作流程。它不適用於等待排程執行的工作流程。如果是，您需要查看促銷活動專家的使用案例，並聯絡Adobe客戶服務以增加限制。

### 頻率

工作流程不能每隔10分鐘自動執行一次。
活動的重復頻率不得少於10分鐘。如果重復頻率設定為(也是預設值)，則不會將此選項納入考量，工作流程會根據執行頻率執行。

### 已暫停的工作流程

已暫停超過天或失敗狀態的工作流程會停止，以佔用較少的磁碟空間。清理工作會顯示在工作流程記錄檔中。

### 轉場效果

仍可執行包含未結束轉場的工作流程：它會產生警告訊息，工作流程會在到達轉場時暫停，但不會產生錯誤。您也可以在沒有完成設計的情況下開始工作流程，並同時完成工作。

For more information, refer to [Executing workflows](../../automating/using//executing-a-workflow.md).

## Activity{#activity}

### 工作流程設計

To ensure that the workflow ends properly, use an **[!UICONTROL End activity]**. 避免離開工作流程的最後一個轉變。

To access the detail view of the transitions, check the **[!UICONTROL Keep interim results]** option in the Execution section of the workflow properties.

>[!CAUTION]
>
>此選項可耗用大量磁碟空間，並可協助您建立工作流程並確保正確的組態和行為。未勾選生產例項。

![](assets/keep_interim_best_practices.png)


### Labelling activities{#activity-labeling}

在開發工作流程時，會針對所有的Adobe Campaign物件產生每個活動的名稱。雖然活動的名稱是由工具產生而且無法編輯，但建議您在設定該活動時加上明確名稱。

### Duplicating activities{#activity-duplicating}

若要複製現有活動，您可以使用複製貼上。如此，您就可以保留原本定義的設定。For more information, refer to [Duplicating workflow activities](../../automating/using/workflow-interface.md).

### Scheduler activity{#acheduler-activity}

When building your workflow, only use one **[!UICONTROL Scheduler activity]** per branch. 如果工作流程的相同分支有數個排程器(連結到彼此)，則要執行的任務數將會乘以指數，如此會大幅超載資料庫。

You can preview the next ten executions of your workflows by clicking **[!UICONTROL Preview next executions]**.

![](assets/preview_scheduler.png)

For more information, refer to [Scheduler activity](../../automating/using/scheduler.md).

## Calling workflow with parameters{#workflow-with-parameters}

Make sure that the name and number of parameters are identical to what is defined when calling the workflow (see [Defining the parameters when calling the workflow](../../automating/using/calling-a-workflow-with-external-parameters.md#defining-the-parameters-when-calling-the-workflow)). 參數'類型'也必須與預期的值一致。

Make sure that all the parameters have been declared in the **[!UICONTROL External signal activity]**. 否則，執行活動時會發生錯誤。

For more information, see [Calling a workflow with external parameters](../../automating/using/calling-a-workflow-with-external-parameters.md).

## Exporting packages{#exporting-packages}

若要匯出套件，匯出的資源不能包含預設ID。因此，必須使用Adobe Campaign Standard提供作為標準範本提供的範本，才能變更導出資源的ID。
For more information, see [Managing packages](../../automating/using/managing-packages.md).

## Exporting lists{#exporting-lists}

The export list option allows you to export a maximum of 100,000 lines by default and defined by the **Nms_ExportListLimit option**. This option can be managed by the functional administrator, under **Administration** &gt; **Application settings** &gt; **Options**.
For more information, see [Exporting lists](../../automating/using/exporting-lists.md).

## Troubleshooting{#workflow-troubleshooting}

Adobe Campaign提供多種記錄檔，以更好地瞭解您的工作流程問題。

### Using workflow logs{#using-workflow-logs}

您可以存取工作流程記錄檔來監控活動的執行。它會依時間順序索引執行和執行錯誤。
For more information, refer to [Monitoring workflow execution](../../automating/using/executing-a-workflow.md#monitoring).

### Using delivery logs{#using-delivery-logs}

傳送記錄可監控傳送的成功程度。排除記錄會在準備傳送期間傳回排除的訊息。傳送記錄檔會提供每個描述檔的傳送狀態。
For more information, refer to [Understanding delivery failures](../../sending/using/understanding-delivery-failures.md).

### Using delivery alerting{#delivery-alerting}

傳送警報功能是警報管理系統，可讓一組使用者自動接收通知，其中包含執行其傳送的資訊。
For more information, refer to [Delivery alerting](../../sending/using/receiving-alerts-when-failures-happen.md).
