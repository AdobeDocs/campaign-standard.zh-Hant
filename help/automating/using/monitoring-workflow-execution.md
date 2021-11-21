---
title: 監控工作流程執行
description: 了解如何監控工作流程的執行。
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
ht-degree: 3%

---

# 監控工作流程執行 {#monitoring}

## 工作流程記錄和任務 {#workflow-log-and-tasks}

此 ![](assets/printpreview_darkgrey-24px.png) 表徵圖開啟工作流日誌和任務菜單。

工作流歷史記錄將保存為在工作流執行選項中指定的持續時間(請參閱 [工作流程屬性](../../automating/using/managing-execution-options.md))。 因此，在此期間，即使重新啟動後，也會儲存所有訊息。 如果您不想儲存先前執行的訊息，必須按一下 ![](assets/delete_darkgrey-24px.png) 按鈕。

此 **[!UICONTROL Log]** 索引標籤包含所有活動或任何選定活動的執行歷史記錄。 其會按時間順序，對執行的操作和執行錯誤進行索引。

![](assets/wkf_execution_4.png)

此 **[!UICONTROL Tasks]** 索引標籤會詳細說明活動的執行順序。 按一下任務以取得詳細資訊。

![](assets/wkf_execution_5.png)

在這兩份清單中：

* 按一下計數器，根據套用的篩選器查看活動總數。 如果清單中的元素數小於30，則預設會顯示計數器。
* 此 **[!UICONTROL Configure list]** 按鈕可讓您選擇顯示的資訊、定義欄順序和排序清單。
* 您可以使用篩選器更快找到您需要的資訊。 使用搜尋欄位來尋找工作流程活動名稱中的特定文字(例如：&quot;query&quot;)和記錄檔。

## 錯誤管理 {#error-management}

發生錯誤時，工作流程會暫停，而發生錯誤時正在執行的活動會閃爍紅色。

工作流程狀態會變成紅色，錯誤會記錄在記錄中。

您可以設定工作流程，使其不會暫停並繼續執行，而不會發生任何錯誤。 要執行此操作，請透過 ![](assets/edit_darkgrey-24px.png) 按鈕和 **[!UICONTROL Execution]** 區段，選取 **忽略** 選項 **發生錯誤時** 欄位。

在此情況下，會中止錯誤的工作。 此模式特別適用於設計為稍後重新嘗試操作（定期操作）的工作流。

>[!NOTE]
>
>您可以針對每個活動個別套用此設定。 若要這麼做，請選取活動，然後使用快速動作將其開啟 ![](assets/edit_darkgrey-24px.png). 然後，在 **執行選項** 標籤。 請參閱 [活動執行選項](../../automating/using/activity-properties.md).

在 [工作流的屬性](../../automating/using/managing-execution-options.md)，則可使用與錯誤管理相關的其他選項。

![](assets/wkf_execution_error.png)

可能的選項包括：

* **[!UICONTROL Supervisors]**:可讓您定義工作流程發生錯誤時要通知的人員群組（電子郵件和應用程式內通知）。 如果未定義組，則不會通知任何人。 如需Adobe Campaign通知的詳細資訊，請參閱 [Adobe Campaign通知](../../administration/using/sending-internal-notifications.md).

* **[!UICONTROL In case of error]**:可讓您指定當活動發生錯誤時要執行的動作。 有兩個選項可供使用：

   * **暫停進程**:工作流程會自動暫停。 然後，工作流狀態為 **錯誤** 而相關的顏色則變成紅色。 問題解決後，重新啟動工作流程。
   * **忽略**:活動不會執行，因此後續的任何活動（在相同分支中）也不會執行。 這可能對循環任務很有用。 如果分支有排程器放在上游，則應在下一個執行日期觸發。

* **[!UICONTROL Consecutive errors]** :可讓您定義在工作流程執行自動暫停之前已授權的多個連續錯誤。

   * 如果指定的數字為 **[!UICONTROL 0]**，或只要未達到指定的數字，則會忽略遇到錯誤的活動。 其他工作流程分支會正常執行。

   * 如果達到指定的數字，則會暫停整個工作流，並變為 **[!UICONTROL Erroneous]**. 如果已定義監事，則會透過電子郵件自動通知他們。 請參閱 [Adobe Campaign 通知](../../administration/using/sending-internal-notifications.md)。
