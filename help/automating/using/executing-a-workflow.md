---
title: 執行工作流程
seo-title: 執行工作流程
description: 執行工作流程
seo-description: 瞭解如何執行和監控工作流程。
page-status-flag: 從未啓動
uuid: ff02b74e-53e8-49c6-bc8 e-0c729 ea7 d25
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: reference
topic-tags: 工作流程一般運作
discoiquuid: 906c85ea-83b7-4268-86da-cd353 f1 dc591
context-tags: 工作流程，概觀；工作流程，主要
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e33cbfbf6376dabfe81b9bd6f7cce817f35d1b75

---


# Executing a workflow{#executing-a-workflow}

## About workflow execution {#about-workflow-execution}

一律會手動啓動工作流程。However, once started, it can remain inactive, depending on the information specified in a [Scheduler](../../automating/using/scheduler.md) activity.

>[!CAUTION]
>
> Adobe建議客戶優先排序工作流程執行，並執行最多20個並行工作流程執行，以便在執行個體間一致地達到最大效能。可能會規劃有超過20個並行工作流程執行，並依預設執行。您可以提交票證給客戶服務，以調整並行工作流程執行次數的預設設定。

執行相關動作(開始、停止、暫停等)are **asynchronous** processes: the command is saved and will become effective once the server is available to apply it.

在工作流程中，每個活動的結果通常會透過轉場來傳送至下列活動，以箭頭表示。

如果轉場未連結至目的地活動，轉場會未結束。

![](assets/wkf_execution_1.png)

>[!NOTE]
>
>仍可執行包含未結束轉場的工作流程：會產生警告訊息，工作流程將會暫停後暫停，但這不會產生錯誤。您也可以開始工作流程，而不需完整完成設計工作，而且您也可以同時完成工作。

執行活動後，轉場中傳送的記錄數會顯示在其上。

![](assets/wkf_transition_count.png)

您可以開啓轉場，檢查傳送的資料在執行工作流程期間或之後是否正確。您可以檢視資料和資料結構。

依預設，只能存取上次轉換的詳細資訊。To be able to access the results of the preceding activities, you need to check the **[!UICONTROL Keep interim results]** option in the **[!UICONTROL Execution]** section of the workflow properties, before starting the workflow.

>[!NOTE]
>
>此選項可耗用大量記憶體，並可協助建立工作流程並確保已正確設定和執行。未勾選生產例項。

When a transition is open, you can edit its **[!UICONTROL Label]** or link a **[!UICONTROL Segment code]** to it. 若要這麼做，請編輯對應的欄位並確認您的修改。

## Controlling a workflow from the REST API {#controlling-a-workflow-from-the-rest-api}

Using the REST API, you can **start**, **pause**, **resume** and **stop** a workflow.

You can find more details and examples of REST calls in the [API documentation.](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#controlling-a-workflow)

## Life cycle {#life-cycle}

工作流程的生命週期包含三個主要步驟，每個步驟都連結至狀態和顏色：

* **編輯(** 灰色)

   This is the initial design phase of a workflow (refer to [Creating a workflow](../../automating/using/building-a-workflow.md#creating-a-workflow)). 工作流程尚未由伺服器處理，而且可以修改而不會有任何風險。

* **進行中** (藍色)

   在初始設計階段完成後，工作流程就可以開始並由伺服器處理。

* **已完成(** 綠色)

   當工作中不再進行任何工作或操作員明確停止執行個體時，工作流程就會完成。

啓動後，工作流程也可能有兩個其他狀態：

* **警告** (黃色)

   The workflow could not finish or was paused using the ![](assets/pause_darkgrey-24px.png) or ![](assets/check_pause_darkgrey-24px.png) buttons.

* **不尋常** (紅色)

   執行工作流程時發生錯誤。工作流程已停止，使用者必須執行動作。To find out more about this error, use the ![](assets/printpreview_darkgrey-24px.png) button to access the workflow log (refer to [Monitoring](../../automating/using/executing-a-workflow.md#monitoring)).

行銷活動清單可讓您顯示所有工作流程及其狀態。For more on this, see [Managing marketing activities](../../start/using/marketing-activities.md#about-marketing-activities).

![](assets/wkf_execution_3.png)

## Execution commands {#execution-commands}

動作列中的圖示可讓您開始、追蹤和修改工作流程的執行。See [Action bar](../../automating/using/workflow-interface.md#action-bar).

![](assets/wkf_execution_2.png)

可用的動作如下：

**開始**

![](assets/play_darkgrey-24px.png) 按鈕會開始執行工作流程，工作流程接著會執行 **(** 藍色)狀態。如果已暫停工作流程，則會繼續此工作流程，否則會啓動，然後啓動初始活動。

>[!NOTE]
>
>啓動是非同步程序：請求會儲存，並由工作流程執行引擎盡快處理。

**暫停**

![](assets/pause_darkgrey-24px.png) 按鈕會暫停執行。The workflow takes on the **Warning** (yellow) status. 在繼續進行新活動之前，不會啓動新活動，但不會暫停進行中的作業。

**Stop**

![](assets/stop_darkgrey-24px.png) 此按鈕會停止執行的工作流程，接著會執行 **「完成」** (綠色)狀態。如果可能的作業中斷，會立即中斷，並且會立即取消進行中的匯入或SQL查詢。您無法從工作流程中繼續的工作流程繼續。

**重新啓動**

![](assets/pauseplay_darkgrey-24px.png) 按鈕包括停止，然後重新啓動工作流程。在大多數情況下，這可讓您加快重啓速度。It can also be useful to automate restarting once stopping takes a certain amount of time, because the ![](assets/play_darkgrey-24px.png) button is only available when the stop is effective.

選取工作流程中的一個或多個活動時，您可以執行其他動作，例如：

**立即執行**

![](assets/pending_darkgrey-24px.png) 按鈕會盡快開始選取任何待定活動。

**一般執行**

![](assets/check_darkgrey-24px.png) 按鈕會重新啓動任何暫停或停用的活動。

**執行暫停**

![](assets/check_pause_darkgrey-24px.png) 按鈕會暫停所選活動的工作流程：此任務以及所有追隨(位於同一分支)的工作都不會執行。

**無執行**

![](assets/checkdisable.png) 此按鈕會停用任何選取的活動。

>[!NOTE]
>
>快速動作可讓您存取特定活動的不同動作，並在選取活動時顯示。

## Monitoring {#monitoring}

![](assets/printpreview_darkgrey-24px.png) 圖示會開啓工作流程記錄檔和工作選單。

The workflow history is saved for the duration specified in the workflow execution options (refer to [Workflow properties](../../automating/using/executing-a-workflow.md#workflow-properties)). 因此，即使在重新啓動後，也會儲存所有訊息。If you do not want to save the messages from a previous execution, you have to purge the history by clicking the ![](assets/delete_darkgrey-24px.png) button.

**[!UICONTROL Log]** 此標籤包含所有活動或任何選取活動的執行歷史記錄。它會依時間順序索引執行和執行錯誤。

![](assets/wkf_execution_4.png)

**[!UICONTROL Tasks]** 此標籤會詳細說明活動的執行順序。按一下工作以取得更多資訊。

![](assets/wkf_execution_5.png)

在這兩份清單中：

* 按一下計數器，根據套用的篩選查看活動總數。如果清單中的元素數少於30，則預設會顯示計數器。
* **[!UICONTROL Configure list]** 按鈕可讓您選擇顯示的資訊、定義欄順序，以及排序清單。
* 您可以使用篩選器來尋找更快速的資訊。使用搜尋欄位尋找工作流程活動名稱中的特定文字(例如：「查詢」)和記錄檔。

## Error management {#error-management}

發生錯誤時，會暫停工作流程，而發生錯誤時所執行的活動會閃爍紅色。

工作流程狀態會變成紅色，而錯誤會記錄在記錄檔中。

您可以設定工作流程，使它不會暫停並繼續執行，而不會發生任何錯誤。To do this, go to the workflow properties via the ![](assets/edit_darkgrey-24px.png) button and, in the **[!UICONTROL Execution]** section, select the **Ignore** option in the **In case of error** field.

在這種情況下，會中止錯誤的工作。此模式特別適合用來稍後重新嘗試操作(定期動作)的工作流程。

>[!NOTE]
>
>您可以個別對每個活動套用此設定。To do this, select an activity and open it using the quick action ![](assets/edit_darkgrey-24px.png). Then select the error management mode in the **Execution options** tab. See [Activity execution options](../../automating/using/executing-a-workflow.md#activity-execution-options).

The **[!UICONTROL Execution]** section of the workflow properties also allows you to define a number of **[!UICONTROL Consecutive errors]** that are authorized before the workflow execution is automatically suspended. 只要未達到此數目，就會忽略錯誤的元素，並正常執行其他工作流程分支。如果達到此數目，工作流程會暫停，工作流程管理員會自動收到通知(電子郵件和應用程式內通知)。See [Workflow properties](../../automating/using/executing-a-workflow.md#workflow-properties) and [Adobe Campaign notifications](../../administration/using/sending-internal-notifications.md).

也可以在工作流程的執行屬性中定義管理員。

## Workflow properties {#workflow-properties}

To modify a workflow's execution options, use the ![](assets/edit_darkgrey-24px.png) button to access the workflow properties and select the **[!UICONTROL Execution]** section.

**[!UICONTROL Default affinity]** 欄位可讓您強制工作流程或工作流程活動在特定機器上執行。

**[!UICONTROL History in days]** 在欄位中指定必須清除歷史記錄的時間長度。

You can choose to check the **[!UICONTROL Save SQL queries in the log]** and **[!UICONTROL Execute in the engine (do not use in production)]** options if necessary.

Check the **[!UICONTROL Keep interim results]** option if you would like to be able to view the detail of transitions. 警告：勾選此選項可能會大幅減慢工作流程執行速度。

**[!UICONTROL Severity]** 欄位可讓您指定在Adobe Campaign例項中執行工作流程的優先順序層級。關鍵工作流程將先執行。

**[!UICONTROL Supervisors]** 如果工作流程遇到錯誤，您可以在欄位中定義要通知的人員群組(電子郵件和應用程式內通知)。如果未定義任何群組，則不會通知任何人。For more on Adobe Campaign notifications, refer to [Adobe Campaign notifications](../../administration/using/sending-internal-notifications.md).

**[!UICONTROL In case of error]** 欄位可讓您指定在活動遇到錯誤時要執行的動作。有兩個可用選項：

* **暫停程序**：工作流程會自動暫停。The workflow status is then **Erroneous** and the color associated turns red. 問題解決後，重新啓動工作流程。
* **忽略**：活動未執行，因此不會執行任何後續的活動(在同一個分支中)。這對循環工作可能很有用。如果分支程式將排程器置於上游，則應在下一個執行日期中觸發。

   By selecting this option, you can also define a number of **[!UICONTROL Consecutive errors]** that are authorized:

   * If the number specified is **[!UICONTROL 0]**, or as long as the number specified is not reached, activities that encounter errors are ignored. 其他工作流程分支會正常執行。
   * If the number specified is reached, the whole of the workflow is suspended and becomes **[!UICONTROL Erroneous]**. 如果已定義主管，則會自動收到電子郵件通知。

![](assets/wkf_execution_6.png)

## Activity properties {#activity-properties}

### General properties of an activity {#general-properties-of-an-activity}

Each activity has a **[!UICONTROL Properties]** tab. 此標籤可讓您修改活動的一般參數，尤其是標籤和ID。設定此標籤是選擇性的。

### Managing an activity's outbound transitions {#managing-an-activity-s-outbound-transitions}

依預設，某些活動沒有對外轉場。You can add one from the **[!UICONTROL Transitions]** tab or from the activity's **[!UICONTROL Properties]** tab to apply other processes to your population in the same workflow.

視活動而定，您可以新增幾種傳出轉場類型：

* 標準轉換：活動計算的人口族群
* 無人口轉換：可新增這種傳出轉場，以繼續工作流程，並不包含任何人口，以不佔用系統上不必要的空間。
* 拒絕：遭到拒絕。例如，如果活動傳入的資料不正確或不完整，則無法加以處理。
* 補充：訪客在執行活動後剩餘時間。例如，如果劃分活動設定為只儲存傳入人口的百分比。

If applicable, specify a **[!UICONTROL Segment code]** for the activity's outbound transition. 此區段程式碼可讓您識別來自目標人群的子集來自何處，並稍後可能用於訊息個人化用途。

### Activity execution options {#activity-execution-options}

In the activity's properties screen, there is an **[!UICONTROL Advanced options]** tab that lets you define the activity's execution mode and behavior in case of errors.

To access these options, select an activity in a workflow, then open it using the ![](assets/edit_darkgrey-24px.png) button from the action bar.

![](assets/wkf_advanced_parameters.png)

**[!UICONTROL Execution]** 欄位可讓您定義在工作開始時要執行的動作。有三個選項：

* **一般**：活動會正常執行。
* **啓用但未執行**：活動會暫停，因此後續的程序也會跟著進行。如果您想要在工作開始時顯示，這可能會很有用。
* **請勿啓用**：活動並未執行，因此後續的所有活動都不會發生(在同一個分支中)。

**[!UICONTROL In case of error]** 欄位可讓您指定在活動遇到錯誤時要執行的動作。有兩個可用選項：

* **暫停程序**：工作流程會自動暫停。The workflow status is then **Erroneous** and the color associated turns red. 問題解決後，重新啓動工作流程。
* **忽略**：活動未執行，因此不會執行任何後續的活動(在同一個分支中)。這對循環工作可能很有用。如果分支程式將排程器置於上游，則應在下一個執行日期中觸發。

**[!UICONTROL Behavior]** 此欄位可讓您定義如果使用非同步任務，應遵循的程序。有兩個可用選項：

* **授權多項工作**：可同時執行多個工作，即使第一個工作未完成。
* **目前的工作具有優先順序**：當工作進行中時，這會優先。只要某個工作仍在進行中，就不會執行其他工作。

**[!UICONTROL Max. execution duration]** 欄位可讓您指定「30s」或「1h」之類的持續時間。如果活動在指定的持續時間之後尚未完成，則會觸發警報。這對工作流程的運作方式沒有影響。

**[!UICONTROL Affinity]** 欄位可讓您強制工作流程或工作流程活動在特定機器上執行。若要這麼做，您必須為工作流程或相關活動指定一或多個相關性。

**[!UICONTROL Time zone]** 欄位可讓您選取活動的時區。Adobe Campaign可讓您管理同一例項上多個國家之間的時間差異。當建立例項時，會設定套用的設定。

**「注釋** 」欄位是可讓您新增附註的免費欄位。
