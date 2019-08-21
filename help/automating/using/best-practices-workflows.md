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
source-git-commit: fd44c6e6d0f6a4ca75b01c99fbae6d9072dd7736

---


# 工作流程最佳實務{#workflow-best-practices}

透過Adobe Campaign，您可以設定所有工作流程，以執行大型工作範圍。但是，在設計和執行工作流程時，您必須格外小心，因為錯誤實作可能導致不良效能、錯誤和平台問題。以下列出最佳實務和疑難排解提示的清單。

>[!NOTE]
>
>工作流程設計和執行必須由Adobe Campaign進階使用者執行。

## 命名命名{#naming}

為了簡化工作流程疑難排解，Adobe建議您明確命名工作流程並標示其標記。填寫工作流程的說明欄位，以摘要執行的程序，讓營運商輕鬆瞭解。
如果工作流程是涉及多個工作流程的程序的一部分，您可以在輸入標籤時使用數字來清楚排序。

例如：

* 001-匯入-匯入收件者
* 002-匯入-匯入銷售
* 003-匯入-匯入銷售詳細資料
* 010-出口-出口記錄檔
* 2011-匯出-匯出追蹤記錄

## 重復工作流程{#duplicating-workflows}

您可以複製工作流程。然後，將 **[!UICONTROL Marketing Activities]**&#x200B;滑鼠指標暫留在工作流程上，然後按一下 **[!UICONTROL Duplicate element]**。複製之後，工作流程的修改不會被帶入工作流程的副本。您可以編輯工作流程的復本。

![](assets/duplicating_workflow.png)

## 執行執行{#execution}

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

如需詳細資訊，請參閱 [執行工作流程](../../automating/using//executing-a-workflow.md)。

## 活動{#activity}

### 工作流程設計

若要確保工作流程正確結束 **[!UICONTROL End activity]**，請使用。避免離開工作流程的最後一個轉變。

若要存取轉場的詳細檢視，請查看工作流程屬性的「執行」區段 **[!UICONTROL Keep interim results]** 中的選項。

>[!CAUTION]
>
>此選項可耗用大量磁碟空間，並可協助您建立工作流程並確保正確的組態和行為。未勾選生產例項。

![](assets/keep_interim_best_practices.png)


### 積極的活動{#activity-labeling}

在開發工作流程時，會針對所有的Adobe Campaign物件產生每個活動的名稱。雖然活動的名稱是由工具產生而且無法編輯，但建議您在設定該活動時加上明確名稱。

### 重復活動{#activity-duplicating}

若要複製現有活動，您可以使用複製貼上。如此，您就可以保留原本定義的設定。如需詳細資訊，請參閱 [複製工作流程活動](../../automating/using/workflow-interface.md)。

### 排程器活動{#acheduler-activity}

建立工作流程時，只能使用每個分支一 **[!UICONTROL Scheduler activity]** 個。如果工作流程的相同分支有數個排程器(連結到彼此)，則要執行的任務數將會乘以指數，如此會大幅超載資料庫。

您可以按一下 **[!UICONTROL Preview next executions]**，預覽下十個工作流程的執行。

![](assets/preview_scheduler.png)

如需詳細資訊，請參閱 [排程器活動](../../automating/using/scheduler.md)。

## 使用參數來呼叫工作流程{#workflow-with-parameters}

請確定名稱和參數數目與呼叫工作流程時定義的參數相同(請參閱 [在呼叫工作流程時定義參數](../../automating/using/calling-a-workflow-with-external-parameters.md#defining-the-parameters-when-calling-the-workflow))。參數'類型'也必須與預期的值一致。

請確定已在此中宣告所有參數 **[!UICONTROL External signal activity]**。否則，執行活動時會發生錯誤。

如需詳細資訊，請參閱 [「呼叫使用外部參數的工作流程](../../automating/using/calling-a-workflow-with-external-parameters.md)」。

## 匯出套件{#exporting-packages}

若要匯出套件，匯出的資源不能包含預設ID。因此，必須使用Adobe Campaign Standard提供作為標準範本提供的範本，才能變更導出資源的ID。
如需詳細資訊，請參閱 [管理套件](../../automating/using/managing-packages.md)。

## 匯出清單{#exporting-lists}

匯出清單選項可讓您預設匯出100,000行，並由 **Nms_ exportListLimit選項定義**。此選項可由功能管理員管理，位於 **[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt; **[!UICONTROL Options]**。
如需詳細資訊，請參閱 [匯出清單](../../automating/using/exporting-lists.md)。

## 疑難排解{#workflow-troubleshooting}

Adobe Campaign提供多種記錄檔，以更好地瞭解您的工作流程問題。

### 使用工作流程記錄檔{#using-workflow-logs}

您可以存取工作流程記錄檔來監控活動的執行。它會依時間順序索引執行和執行錯誤。「記錄檔」索引標籤包含在執行所有或部分選取活動的歷史記錄中。
「任務」標籤會詳細說明活動的執行順序。若要取得活動的詳細資訊，請按一下工作。
如需詳細資訊，請參閱 [監控工作流程執行](../../automating/using/executing-a-workflow.md#monitoring)。

#### 資料管理活動疑難排解{#troubleshooting-data-management-activities}

您可以在「記錄檔」索引標籤中分析SQL查詢。

1. 在工作流程工作區中，按一下 **[!UICONTROL Edit properties]**。
1. In **[!UICONTROL General]** &gt; **[!UICONTROL Execution]**，check the **[!UICONTROL Save SQL queries in the log]** &amp; **[!UICONTROL Execute in the engine]** options and click **[!UICONTROL Confirm]**.

**若要在記錄檔中查看SQL查詢：**
1. Click **[!UICONTROL Log and Tasks]**.
1. **[!UICONTROL Logs]** 在標籤中開啓 **[!UICONTROL Search]** 面板。
1. Check **[!UICONTROL Display SQL logs only]**.

查詢會顯示在記錄 **[!UICONTROL Message]** 欄的欄中。

### 使用傳送記錄檔{#using-delivery-logs}

傳送記錄可監控傳送的成功程度。排除記錄會在準備傳送期間傳回排除的訊息。傳送記錄檔會提供每個描述檔的傳送狀態。
如需詳細資訊，請參閱 [瞭解傳送失敗](../../sending/using/understanding-delivery-failures.md)。

### 使用傳送警報{#delivery-alerting}

傳送警報功能是警報管理系統，可讓一組使用者自動接收通知，其中包含執行其傳送的資訊。
如需詳細資訊，請參閱 [傳送警告](../../sending/using/receiving-alerts-when-failures-happen.md)。

**相關主題：**

* [錯誤管理](../../automating/using/executing-a-workflow.md#error-management)
