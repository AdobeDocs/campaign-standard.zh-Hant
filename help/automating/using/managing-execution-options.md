---
title: 管理執行選項
description: 瞭解如何管理工作流程執行選項。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
role: Data Architect
level: Beginner
exl-id: b0cc38fe-cf71-4350-8b4e-7daf0bf94066
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 8%

---

# 管理執行選項 {#managing-execution-options}

若要修改工作流程的執行選項，請使用![](assets/edit_darkgrey-24px.png)按鈕來存取工作流程屬性，並選取&#x200B;**[!UICONTROL Execution]**&#x200B;區段。

![](assets/wkf_execution_6.png)

可能的選項包括：

* **[!UICONTROL Default affinity]**：此欄位可讓您強制在特定電腦上執行工作流程或工作流程活動。

* **[!UICONTROL History in days]**：指定必須清除歷程記錄的天數。 歷程記錄包含與工作流程相關的元素：記錄、工作、事件（連結至工作流程作業的技術物件），以及&#x200B;**[!UICONTROL Transfer file]**&#x200B;活動下載的檔案。 立即可用工作流程範本的預設值為 30 天。

  清除記錄是由資料庫清理技術工作流程執行，預設每天執行（請參閱[技術工作流程清單](../../administration/using/technical-workflows.md)）。

  >[!IMPORTANT]
  >
  >如果&#x200B;**[!UICONTROL History in days]**&#x200B;欄位留空，其值將視為「1」，這表示歷史記錄將在1天後清除。

* **[!UICONTROL Save SQL queries in the log]**：可讓您從工作流程將SQL查詢儲存到記錄檔中。

* **[!UICONTROL Diagnostic mode (Log execution plan of long running queries and give recommendations)]**：如果您想要記錄整個執行計畫，請核取此選項。 預設為停用。

  如需此選項的詳細資訊，請參閱此[區段](#diagnostic-mode)。

* **[!UICONTROL Keep interim results]**：如果您想要檢視轉換的詳細資訊，請核取此選項。

  >[!CAUTION]
  >
  >此選項佔用了大量磁碟空間，設計旨在幫助您建構工作流程並確保正確的設定和行為。在生產執行個體中保留未核取的狀態。

* **[!UICONTROL Execute in the engine (do not use in production)]**：可讓您在本機執行工作流程，以進行開發環境測試。

* **[!UICONTROL Severity]**：可讓您指定在Adobe Campaign執行個體中執行工作流程的優先順序等級。 此欄位僅供Adobe團隊用於監視目的。

**[!UICONTROL Error management]**&#x200B;區段提供其他選項，可讓您管理工作流程在發生錯誤時的行為方式。 這些選項在[錯誤管理](../../automating/using/monitoring-workflow-execution.md#error-management)區段中詳細說明。

## 診斷模式 {#diagnostic-mode}

>[!CAUTION]
>
>此選項可能會大幅影響您的工作流程效能，應謹慎使用。

啟用時，如果查詢超過一分鐘，工作流程屬性&#x200B;**[!UICONTROL Execution]**&#x200B;區段中的&#x200B;**[!UICONTROL Diagnostic mode (Log execution plan of long running queries and give recommendations)]**&#x200B;選項會記錄整個執行計畫。

![](assets/wkf_diagnostic.png)

在啟用此選項並啟動工作流程後，如果您的查詢需要超過一分鐘的時間，則會記錄執行計畫。 接著，您可以使用EXPLAIN ANALYZE擷取執行計畫。

如需詳細資訊，請參閱[PostgreSQL檔案](https://www.postgresql.org/docs/9.4/using-explain.html)。

如果您在此查詢中進行序列掃描，**[!UICONTROL Diagnostic mode]**&#x200B;也會提供建議，以便在篩選運算式的協助下建立索引。

>[!NOTE]
>
> 這些建議僅供參考，應根據您的使用案例謹慎使用。

![](assets/wkf_diagnostic_4.png)

在工作流程執行期間，必須符合下列兩個條件才能觸發建議：

* 序列掃描需要超過40%的查詢時間。

* 序列掃描後產生的列數少於表格中出現之總列數的1%。

您可以選取&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]**，從進階功能表管理選項：

* **[!UICONTROL Time of query execution (in milliseconds)(DiagnosticModeQueryTime)]**：您可以從&#x200B;**[!UICONTROL Value]**&#x200B;欄位設定新的查詢執行時間。 如果您的查詢執行超過此值，則會記錄執行計畫。

  ![](assets/wkf_diagnostic_2.png)

* **[!UICONTROL Percentage of seq scan time (DiagnosticModeSeqScanPercentage)]**：從&#x200B;**[!UICONTROL Value]**&#x200B;欄位，您可以變更序列掃描必須花費的查詢時間百分比，才能產生建議。

  ![](assets/wkf_diagnostic_3.png)
