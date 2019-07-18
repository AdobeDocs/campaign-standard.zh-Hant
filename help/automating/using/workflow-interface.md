---
title: 工作流程介面
seo-title: 工作流程介面
description: 工作流程介面
seo-description: 瞭解建立、編輯和執行工作流程的介面和選項。
page-status-flag: 從未啓動
uuid: aafe33ed-fa07-4dd9-825e-24209334f1 a
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: reference
topic-tags: 關於工作流程與資料管理
discoiquuid: 147fb0d-17d2-444b-a215-9ad14179 c549
context-tags: workflow，main；工作流程，概觀
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: ff0b995533f34dd8eab7a9a82feaab3ceed4ff29

---


# Workflow interface{#workflow-interface}

您可以建立工作流程來管理促銷活動和計劃中的整個流程。

工作流程編輯畫面由下列元素組成：

* The [Palette](../../automating/using/workflow-interface.md#palette), which references the available activities
* [The Workspace](../../automating/using/workflow-interface.md#workspace)，which the activity are configured and organized
* [動作列](../../automating/using/workflow-interface.md#action-bar)由按鈕組成，可讓您與工作流程及/或其元件互動。
* [快速動作](../../automating/using/workflow-interface.md#quick-actions)會出現在選取活動周圍，可讓您與其互動。

![](assets/wkf_overview.png)

## Palette {#palette}

浮動視窗位於畫面的左側。所有可用活動可排序為幾個類別：

* [定位](../../automating/using/about-targeting-activities.md)：特定於定位、控制人口資料和篩選活動的活動
* [執行](../../automating/using/about-execution-activities.md)：組織和執行工作流程的特定活動
* [頻道](../../automating/using/about-channel-activities.md)：代表不同可用通訊管道的活動
* [資料管理(ETL)](../../automating/using/about-data-management-activities.md)：控制資料的特定活動

若要從工作流程中的浮動視窗使用活動，請將其拖放至工作區中。

您必須先設定浮動視窗中新增的每個活動，然後再啓動工作流程。

![](assets/workflow_palette.png)

## Workspace {#workspace}

工作區是工作流程編輯器中的中央區域。您可以在此區域中放下活動、使用轉場連結它們，並進行設定。

若要連結兩個活動，請將箭頭從第一個活動移至下列活動，直到他們連線為止。您也可以將活動移至後面箭頭的點，以便將其連結至先前的活動。如果您移動任何活動，他們將保持連結。

處理資料的後續活動包含中間人口族群。You can access them if you check the **[!UICONTROL Keep interim results]** option in the **[!UICONTROL Execution]** section of the workflow properties.

選取活動時，快速動作會出現在活動周圍，讓您與其互動。For example, to configure an activity, select it then open it using the ![](assets/edit_darkgrey-24px_table.png) button in the quick actions.

某些函數僅在工作區中啓用：

* 在周圍繪制一個區域，以選取多個活動和轉場。
* Press **Ctrl** + left click to select several activities and/or transitions.
* Press **Enter** to view the detail of the currently selected activity or transition.
* Press **Delete** to delete the currently selected activity.
* Press **Ctrl + C** to copy the selected activities, and **Ctrl + V** to paste them into the workspace.

![](assets/workflow_workspace.png)

## Action bar {#action-bar}

視工作區中選取的元素或工作流程的執行狀態而定，動作列中可用的按鈕可能會有所不同。

<img height="21px" src="assets/edit_darkgrey-24px.png" /> **[!UICONTROL Open activity]**<br/>可讓您編輯工作流程的屬性。

<img height="21px" src="assets/play_darkgrey-24px_table.png" /> **[!UICONTROL Start]**<br/>啓動工作流程。

<img height="21px" src="assets/pause_darkgrey-24px_table.png" /> **[!UICONTROL Pause]**<br/>暫停工作流程。

<img height="21px" src="assets/stop_darkgrey-24px_table.png" /> **[!UICONTROL Stop]**<br/>中斷工作流程執行。無法從其停止處繼續。

<img height="21px" src="assets/pauseplay_darkgrey-24px_table.png" /> **[!UICONTROL Restart]**<br/>重新啓動工作流程。

<img height="21px" src="assets/printpreview_darkgrey-24px_table.png" /> **[!UICONTROL Log and tasks]**<br/>開啓工作流程的執行記錄檔。

<img height="21px" src="assets/checkcircle_darkgrey-24px_table.png" /> **[!UICONTROL Enable multi-selection]**<br/>啓用多重選擇模式。工作流程至少必須由兩個活動組成。

<img height="21px" src="assets/closecircle_darkgrey-24px_table.png" /> **[!UICONTROL Disable multi-selection]**<br/>停用多重選擇模式。<br />

<img height="21px" src="assets/targeted.png" /> **[!UICONTROL Open transition]**<br/>開啓選取的轉變。<br />

<img height="21px" src="assets/check_darkgrey-24px_table.png" />  **[!UICONTROL Normal execution]**<br/>如果先前已停用或標示為暫停，則重新啓用選取範圍。<br />

<img height="21px" src="assets/check_pause_darkgrey-24px_table.png" /> **[!UICONTROL Execution suspended]**<br/>暫停選取活動的工作流程。<br />

<img height="21px" src="assets/checkdisable.png" /> **[!UICONTROL No execution]**<br/>停用活動。<br />

<img height="21px" src="assets/delete_darkgrey-24px_table.png" /> **[!UICONTROL Delete selection]**<br/>刪除已選取的活動。<br />

<img height="21px" src="assets/copy_24px.png" /> **[!UICONTROL Copy selection]**<br/>複製已選取的活動。

<img height="21px" src="assets/paste_24px.png" /> **[!UICONTROL Paste]**<br/>貼上已複製的活動。

## Quick actions {#quick-actions}

選取活動時，快速動作按鈕會出現在活動周圍，讓您與其互動。

<img height="21px" src="assets/edit_darkgrey-24px.png" /> **[!UICONTROL Open activity]**<br/>開啓選取的活動。

<img height="21px" src="assets/copy_24px.png" /> **[!UICONTROL Copy selection]**<br/>複製選取的活動。

<img height="21px" src="assets/wkf_dlv_act_params_icon.png" /> **[!UICONTROL Open the activity's advanced options]**<br/>開啓選取的電子郵件或簡訊傳送活動的進階選項。

<img height="21px" src="assets/check_darkgrey-24px_table.png" /> **[!UICONTROL Normal execution]**<br/>如果先前已停用或標示為暫停，則重新啓用選取範圍。

<img height="21px" src="assets/check_pause_darkgrey-24px_table.png" /> **[!UICONTROL Execution suspended]**<br/>暫停選取活動的工作流程。

<img height="21px" src="assets/checkdisable.png" /> **[!UICONTROL No execution]**<br/>停用活動。

<img height="21px" src="assets/pending_darkgrey-24px_table.png" /> **[!UICONTROL Immediate execution]**<br/>強制立即處理選取範圍。This button is only available for the <span class="uicontrol">Scheduler</span> and <span class="uicontrol">Wait</span> activities.

<img height="21px" src="assets/delete_darkgrey-24px_table.png" /> **[!UICONTROL Delete selection]**<br/>刪除已選取的活動。

## Duplicating workflow activities {#duplicating-workflow-activities}

工作區可讓您複製工作流程活動，將它們複製到相同工作流程中，或從相同促銷活動例項中的另一個工作流程複製。

一旦複製活動後，就會保留其完整設定。針對傳送活動(電子郵件、簡訊、推播通知…)，會複製活動的傳送物件。

>[!NOTE]
>
>工作流程活動無法從例項複製到另一個。技術工作流程中的活動無法重復。

若要複製活動，請遵循下列步驟：

1. Select the activity, then click the **[!UICONTROL Copy selection]** button from the quick actions.

   You can also use the **Ctrl + C** keyboard shortcut.

   ![](assets/wkf_copypaste1.png)

1. Right-click in the target workflow workspace, then click the **[!UICONTROL Paste]** button.

   You can also use the **CTRL + V** keyboard shortcut.

   ![](assets/wkf_copypaste2.png)

1. 活動會重復，並包含最初設定的所有設定。

此外，也可以複製多個啓動，讓您複製整個音效。

若要這麼做，請在周圍繪制一個區域，以選取活動。then click the **[!UICONTROL Copy selection]** button from the action bar (or press **Ctrl + C**). 然後您可以貼到所要的位置。

![](assets/wkf_copypaste3.png)

