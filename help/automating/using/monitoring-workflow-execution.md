---
title: 監控工作流程執行
description: 瞭解如何監視工作流程的執行。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: d2ce702b-92d1-4b94-bd47-34ef46a8bd9f
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '578'
ht-degree: 4%

---

# 監控工作流程執行 {#monitoring}

## 工作流程記錄檔與任務 {#workflow-log-and-tasks}

![](assets/printpreview_darkgrey-24px.png)圖示會開啟工作流程記錄與工作功能表。

工作流程歷史記錄會儲存至工作流程執行選項中指定的期間（請參閱[工作流程屬性](../../automating/using/managing-execution-options.md)）。 因此，在此期間會儲存所有訊息，即使在重新啟動後亦然。 如果您不想儲存先前執行的訊息，則必須按一下![](assets/delete_darkgrey-24px.png)按鈕以清除歷史記錄。

**[!UICONTROL Log]**&#x200B;索引標籤包含所有活動或任何選定活動的執行歷史記錄。 其會按時間順序，對執行的操作和執行錯誤進行索引。

![](assets/wkf_execution_4.png)

**[!UICONTROL Tasks]**&#x200B;索引標籤詳細說明活動的執行順序。 按一下工作以取得詳細資訊。

![](assets/wkf_execution_5.png)

在以下兩個清單中：

* 按一下計數器，即可根據套用的篩選器檢視活動總數。 如果清單中的元素數量少於30，則預設會顯示計數器。
* **[!UICONTROL Configure list]**&#x200B;按鈕可讓您選擇顯示的資訊、定義欄順序，以及排序清單。
* 您可以使用篩選器來更快找到所需的資訊。 使用搜尋欄位在工作流程活動名稱（例如：&quot;query&quot;）和記錄檔中尋找特定文字。

## 錯誤管理 {#error-management}

發生錯誤時，工作流程會暫停，而且發生錯誤時所執行的活動會以紅色閃爍。

工作流程狀態會變成紅色，而錯誤會記錄在紀錄中。

您可以設定工作流程，使其不會暫停並繼續執行，而不會發生任何錯誤。 若要這麼做，請透過![](assets/edit_darkgrey-24px.png)按鈕移至工作流程屬性，並在&#x200B;**[!UICONTROL Execution]**&#x200B;區段中，選取&#x200B;**發生錯誤時忽略**&#x200B;欄位中的&#x200B;**忽略**&#x200B;選項。

在這種情況下，會中止錯誤的工作。 此模式特別適合用於設計為在稍後重新嘗試操作（週期性動作）的工作流程。

>[!NOTE]
>
>您可以對每個活動個別套用此設定。 若要這麼做，請選取活動並使用快速動作![](assets/edit_darkgrey-24px.png)將其開啟。 然後在&#x200B;**執行選項**&#x200B;索引標籤中選取錯誤管理模式。 請參閱[活動執行選項](../../automating/using/activity-properties.md)。

在[工作流程的屬性](../../automating/using/managing-execution-options.md)中，可以使用與錯誤管理相關的其他選項。

![](assets/wkf_execution_error.png)

可能的選項包括：

* **[!UICONTROL Supervisors]**：可讓您定義工作流程發生錯誤時要通知的人員群組（電子郵件和應用程式內通知）。 如果未定義群組，則不會通知任何人。 如需 Adobe Campaign 通知的詳細資訊，請參閱 [Adobe Campaign 通知](../../administration/using/sending-internal-notifications.md)。

* **[!UICONTROL In case of error]**：可讓您指定當活動發生錯誤時要執行的動作。 對此有兩個可用選項：

   * **暫停處理序**：工作流程已自動暫停。 工作流程狀態為&#x200B;**錯誤**，關聯的顏色會變成紅色。 問題解決後，請重新啟動工作流程。
   * **忽略**：活動未執行，因此它後面沒有任何活動（在相同分支中）。 事實證明，這對週期性任務很有用。 如果分支有放置在上游的排程器，這應在下一個執行日期觸發。

* **[!UICONTROL Consecutive errors]** ：可讓您定義在自動暫停工作流程執行之前獲授權的連續錯誤數。

   * 如果指定的數字為&#x200B;**[!UICONTROL 0]**，或只要未達到指定的數字，則會忽略發生錯誤的活動。 其他工作流程分支會正常執行。

   * 如果達到指定的數目，則整個工作流程會暫停，並變成&#x200B;**[!UICONTROL Erroneous]**。 若已定義主管，則會自動透過電子郵件通知他們。 請參閱 [Adobe Campaign 通知](../../administration/using/sending-internal-notifications.md)。
