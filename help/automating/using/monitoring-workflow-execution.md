---
title: 監控工作流程執行
description: 瞭解如何監視工作流的執行。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: d2ce702b-92d1-4b94-bd47-34ef46a8bd9f
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '577'
ht-degree: 6%

---

# 監控工作流程執行 {#monitoring}

## 工作流日誌和任務 {#workflow-log-and-tasks}

的 ![](assets/printpreview_darkgrey-24px.png) 表徵圖開啟工作流日誌和任務菜單。

工作流歷史記錄將保存為在工作流執行選項中指定的持續時間(請參閱 [工作流屬性](../../automating/using/managing-execution-options.md))。 因此，即使在重新啟動後，也會保存所有消息。 如果不想保存上次執行中的消息，則必須按一下 ![](assets/delete_darkgrey-24px.png) 按鈕

的 **[!UICONTROL Log]** 頁籤包含所有活動或任何選定活動的執行歷史記錄。 其會按時間順序，對執行的操作和執行錯誤進行索引。

![](assets/wkf_execution_4.png)

的 **[!UICONTROL Tasks]** 頁籤詳細列出活動的執行順序。 按一下任務以獲取詳細資訊。

![](assets/wkf_execution_5.png)

在以下兩個清單中：

* 按一下計數器，根據應用的篩選器查看活動總數。 如果清單中的元素數小於30，則預設顯示計數器。
* 的 **[!UICONTROL Configure list]** 按鈕，您可以選擇顯示的資訊、定義列順序和對清單進行排序。
* 您可以使用篩選器更快地查找所需資訊。 使用搜索欄位可查找工作流活動名稱中的特定文本(例如：&quot;query&quot;)和日誌。

## 錯誤管理 {#error-management}

出現錯誤時，工作流暫停，遇到錯誤時正在執行的活動閃爍紅色。

工作流狀態變為紅色，錯誤記錄在日誌中。

您可以配置工作流，使其不會暫停並繼續執行而不會出現任何錯誤。 為此，請通過 ![](assets/edit_darkgrey-24px.png) 按鈕 **[!UICONTROL Execution]** 的 **忽略** 的上界 **出錯時** 的子菜單。

在這種情況下，錯誤任務被中止。 此模式特別適用於設計為稍後重新嘗試該操作（定期操作）的工作流。

>[!NOTE]
>
>您可以針對每個活動單獨應用此配置。 要執行此操作，請選擇一個活動並使用快速操作將其開啟 ![](assets/edit_darkgrey-24px.png)。 然後，在 **執行選項** 頁籤。 請參閱 [活動執行選項](../../automating/using/activity-properties.md)。

在 [工作流的屬性](../../automating/using/managing-execution-options.md)中，提供了與錯誤管理相關的其他選項。

![](assets/wkf_execution_error.png)

可能的選項包括：

* **[!UICONTROL Supervisors]**:允許您定義工作流遇到錯誤時要通知的人員組（電子郵件和應用內通知）。 如果未定義組，則不會通知任何人。 如需 Adobe Campaign 通知的詳細資訊，請參閱 [Adobe Campaign 通知](../../administration/using/sending-internal-notifications.md)。

* **[!UICONTROL In case of error]**:允許您指定在活動遇到錯誤時要執行的操作。 有兩個選項可供選擇：

   * **暫停進程**:工作流自動掛起。 然後，工作流狀態為 **錯誤** 關聯的顏色變成紅色。 問題解決後，重新啟動工作流。
   * **忽略**:未執行該活動，因此也不執行其後的任何活動（在同一分支中）。 這可能對循環任務有用。 如果分支有調度程式置於上游，則應在下一執行日期觸發該調度程式。

* **[!UICONTROL Consecutive errors]** :允許您定義在工作流執行自動掛起之前已授權的連續錯誤。

   * 如果指定的編號為 **[!UICONTROL 0]**，或只要未達到指定的編號，則忽略遇到錯誤的活動。 其他工作流分支正常執行。

   * 如果達到指定的編號，則整個工作流將掛起並變為 **[!UICONTROL Erroneous]**。 如果已定義了主管，則自動通過電子郵件通知他們。 請參閱 [Adobe Campaign 通知](../../administration/using/sending-internal-notifications.md)。
