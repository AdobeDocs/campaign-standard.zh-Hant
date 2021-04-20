---
solution: Campaign Standard
product: campaign
title: 管理執行選項
description: 瞭解如何管理工作流程執行選項。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
role: Data Architect
level: Beginner
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 13%

---


# 管理執行選項 {#managing-execution-options}

要修改工作流的執行選項，請使用![](assets/edit_darkgrey-24px.png)按鈕訪問工作流屬性並選擇&#x200B;**[!UICONTROL Execution]**&#x200B;部分。

![](assets/wkf_execution_6.png)

可能的選項包括：

* **[!UICONTROL Default affinity]**:此欄位允許您強制在特定電腦上執行工作流或工作流活動。

* **[!UICONTROL History in days]**:指定必須清除歷史記錄的天數。歷史記錄包含與工作流相關的元素：日誌、任務、事件（連結至工作流操作的技術對象）以及由&#x200B;**[!UICONTROL Transfer file]**&#x200B;活動下載的檔案。 現成可用的工作流程範本的預設值為30天。

   清除歷史記錄由資料庫清理技術工作流執行，預設每天執行該工作流（請參閱[技術工作流清單](../../administration/using/technical-workflows.md)）。

   >[!IMPORTANT]
   >
   >如果&#x200B;**[!UICONTROL History in days]**&#x200B;欄位留空，其值將視為&quot;1&quot;，表示歷史記錄將在1天後清除。

* **[!UICONTROL Save SQL queries in the log]**:允許您將工作流中的SQL查詢保存到日誌中。

* **[!UICONTROL Keep interim results]**:如果您想要檢視轉場的詳細資訊，請勾選此選項。

   >[!CAUTION]
   >
   >此選項佔用了大量磁碟空間，設計旨在幫助您建構工作流程並確保正確的設定和行為。在生產執行個體中保留未核取的狀態。

* **[!UICONTROL Execute in the engine (do not use in production)]**:可讓您在本端執行工作流程，以用於開發環境測試。

* **[!UICONTROL Severity]**:允許您指定在Adobe Campaign實例中執行工作流的優先順序。此欄位僅供Adobe團隊用於監控用途。

**[!UICONTROL Error management]**&#x200B;區段提供其他選項，可讓您管理工作流程在發生錯誤時的行為。 這些選項在[錯誤管理](../../automating/using/monitoring-workflow-execution.md#error-management)部分中有詳細說明。
