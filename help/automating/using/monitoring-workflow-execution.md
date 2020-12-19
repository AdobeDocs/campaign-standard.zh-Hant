---
solution: Campaign Standard
product: campaign
title: 監控工作流程執行
description: 瞭解如何監控工作流程的執行。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '577'
ht-degree: 3%

---


# 監控工作流程執行 {#monitoring}

## 工作流日誌和任務{#workflow-log-and-tasks}

![](assets/printpreview_darkgrey-24px.png)圖示會開啟工作流程記錄和工作功能表。

工作流歷史記錄將保存在工作流執行選項中指定的持續時間內（請參閱[工作流屬性](../../automating/using/managing-execution-options.md)）。 因此，在此期間，即使在重新啟動後，也會保存所有消息。 如果不想保存先前執行中的消息，則必須按一下![](assets/delete_darkgrey-24px.png)按鈕來清除歷史記錄。

**[!UICONTROL Log]**&#x200B;標籤包含所有活動或任何選定活動的執行歷史記錄。 其會按時間順序，對執行的操作和執行錯誤進行索引。

![](assets/wkf_execution_4.png)

**[!UICONTROL Tasks]**&#x200B;標籤詳細說明活動的執行順序。 按一下工作以取得詳細資訊。

![](assets/wkf_execution_5.png)

在這兩個清單中：

* 按一下計數器，以根據套用的篩選條件查看活動總數。 如果清單中的元素數少於30，則預設會顯示計數器。
* **[!UICONTROL Configure list]**&#x200B;按鈕可讓您選擇顯示的資訊、定義欄順序，以及排序清單。
* 您可以使用篩選器更快找到所需資訊。 使用搜尋欄位在工作流程活動名稱中尋找特定文字(例如：&quot;query&quot;)和記錄檔。

## 錯誤管理{#error-management}

發生錯誤時，工作流程會暫停，當發生錯誤時正在執行的活動會閃爍紅色。

工作流狀態變為紅色，錯誤記錄在日誌中。

您可以設定工作流程，使其不會暫停並繼續執行，而不會出現錯誤。 要執行此操作，請通過![](assets/edit_darkgrey-24px.png)按鈕轉到工作流屬性，並在&#x200B;**[!UICONTROL Execution]**&#x200B;部分的&#x200B;**發生錯誤時，選擇**&#x200B;欄位中的&#x200B;**忽略**&#x200B;選項。

在這種情況下，錯誤任務將被中止。 此模式特別適用於設計為稍後重新嘗試操作（定期操作）的工作流。

>[!NOTE]
>
>您可以針對每個活動分別套用此設定。 若要這麼做，請選取活動，然後使用快速動作![](assets/edit_darkgrey-24px.png)將其開啟。 然後在&#x200B;**執行選項**&#x200B;頁籤中選擇錯誤管理模式。 請參閱[活動執行選項](../../automating/using/activity-properties.md)。

在[工作流的屬性](../../automating/using/managing-execution-options.md)中，提供了與錯誤管理相關的其他選項。

![](assets/wkf_execution_error.png)

可能的選項包括：

* **[!UICONTROL Supervisors]**:可讓您定義工作流程遇到錯誤時要通知的群組（電子郵件和應用程式內通知）。如果未定義任何群組，則不會通知任何人。 如需Adobe Campaign通知的詳細資訊，請參閱[Adobe Campaign通知](../../administration/using/sending-internal-notifications.md)。

* **[!UICONTROL In case of error]**:允許您指定在活動遇到錯誤時要執行的操作。有兩個選項可供使用：

   * **暫停流程**:工作流程會自動暫停。然後，工作流狀態為&#x200B;**錯誤**，相關顏色變為紅色。 問題解決後，請重新啟動工作流程。
   * **忽略**:不會執行活動，因此，後續的任何活動（位於同一個分支）也不會執行。這可能對循環性任務非常有用。 如果分支有調度程式放在上游，則應在下次執行日期觸發。

* **[!UICONTROL Consecutive errors]** :允許您定義在工作流執行自動暫停之前授權的連續錯誤。

   * 如果指定的數字為&#x200B;**[!UICONTROL 0]**，或者只要未達到指定的數字，就會忽略遇到錯誤的活動。 其他工作流程分支會正常執行。

   * 如果達到指定的數字，則整個工作流將暫停並變為&#x200B;**[!UICONTROL Erroneous]**。 如果已定義主管，則會自動透過電子郵件通知他們。 請參閱 [Adobe Campaign 通知](../../administration/using/sending-internal-notifications.md)。
