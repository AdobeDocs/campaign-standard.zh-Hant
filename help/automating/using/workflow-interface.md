---
title: 工作流程介面
description: 了解建立、編輯及執行工作流程的介面和選項。
audience: automating
content-type: reference
topic-tags: about-workflows-and-data-management
context-tags: workflow,main;workflow,overview
feature: Workflows
role: Data Architect
level: Beginner
exl-id: a3f35bb9-e61e-4f3f-b855-1d677422f75a
source-git-commit: 13d419c5fc51845ee14f8a3b288f4c467e0a60d9
workflow-type: tm+mt
source-wordcount: '802'
ht-degree: 4%

---

# 工作流程介面{#workflow-interface}

您可以建立工作流程來管理行銷活動和方案中的整個程式。

工作流程編輯畫面由下列元素組成：

* 參考可用活動的[浮動視窗](#palette)。
* [工作區](#workspace)，在此設定和組織活動。
* [動作列](#action-bar)，由按鈕組成，可讓您與工作流程及/或其元件互動。
* [快速動作](#quick-actions)會出現在選取的活動周圍，可讓您與其互動。

![](assets/wkf_overview.png)

## 浮動視窗 {#palette}

浮動視窗位於畫面的左側。 所有可用活動皆分為數個類別：

* [目標定位](../../automating/using/about-targeting-activities.md):目標定位、操控人口資料和篩選活動的特定活動
* [執行](../../automating/using/about-execution-activities.md):組織和執行工作流程的特定活動
* [管道](../../automating/using/about-channel-activities.md):代表不同可用通訊通道的活動
* [資料管理(ETL)](../../automating/using/about-data-management-activities.md):操作資料的特定活動

若要從工作流程的浮動視窗使用活動，請將其拖放至工作區中。

您必須先設定從浮動視窗新增的每個活動，才能開始工作流程。

![](assets/workflow_palette.png)

## 工作區 {#workspace}

工作區是工作流程編輯器中的中央區域。 您可以在此區域放置活動、使用轉變將活動連結在一起並進行設定。

若要連結兩個活動，請將箭頭的結尾從第一個活動移至下列活動，直到它們連線為止。 您也可以將活動移至其後面的箭頭點，以將其連結至上一個活動。 如果您移動任何活動，則它們將保持連結。

處理資料之活動後的轉變包含中間人口。 如果您勾選工作流程屬性的&#x200B;**[!UICONTROL Execution]**&#x200B;區段中的&#x200B;**[!UICONTROL Keep interim results]**&#x200B;選項，則可以存取它們。

>[!CAUTION]
>
>此選項佔用了大量磁碟空間，設計旨在幫助您建構工作流程並確保正確的設定和行為。在生產執行個體中保留未核取的狀態。


選取活動時，快速動作會出現在活動周圍，讓您與活動互動。 例如，要配置活動，請選擇該活動，然後使用快速操作中的![](assets/edit_darkgrey-24px_table.png)按鈕將其開啟。

某些功能僅在工作區中啟用：

* 通過繪製周圍區域來選取多個活動和轉變。
* 按&#x200B;**Ctrl** +按一下左鍵以選取數個活動和/或轉變。
* 按下&#x200B;**Enter**&#x200B;以檢視目前所選活動或轉變的詳細資訊。
* 按下&#x200B;**Delete**&#x200B;以刪除目前選取的活動。
* 按下&#x200B;**Ctrl + C**&#x200B;以複製選取的活動，並按下&#x200B;**Ctrl + V**&#x200B;以將其貼入工作區。

![](assets/workflow_workspace.png)

## 動作列 {#action-bar}

根據工作區中選取的元素或工作流程的執行狀態，動作列中可用的按鈕可能會有所不同。

<img height="21px" src="assets/edit_darkgrey-24px.png" /> **[!UICONTROL Open activity]**<br/>可讓您編輯工作流程的屬性。

<img height="21px" src="assets/play_darkgrey-24px_table.png" /> **[!UICONTROL Start]**<br/>啟動工作流程。

<img height="21px" src="assets/pause_darkgrey-24px_table.png" /> **[!UICONTROL Pause]**<br/>暫停工作流。

<img height="21px" src="assets/stop_darkgrey-24px_table.png" /> **[!UICONTROL Stop]**<br/>中斷工作流程執行。無法從停止的位置恢復。

<img height="21px" src="assets/pauseplay_darkgrey-24px_table.png" /> **[!UICONTROL Restart]**<br/>重新啟動工作流程。

<img height="21px" src="assets/printpreview_darkgrey-24px_table.png" /> **[!UICONTROL Log and tasks]**<br/>開啟工作流程的執行記錄檔。

<img height="21px" src="assets/checkcircle_darkgrey-24px_table.png" /> **[!UICONTROL Enable multi-selection]**<br/>啟用多選模式。工作流程必須至少由兩個活動組成。

<img height="21px" src="assets/closecircle_darkgrey-24px_table.png" /> **[!UICONTROL Disable multi-selection]**<br/>禁用多選模式。<br />

<img height="21px" src="assets/targeted.png" /> **[!UICONTROL Open transition]**<br/>開啟所選過渡。<br />

<img height="21px" src="assets/check_darkgrey-24px_table.png" />  **[!UICONTROL Normal execution]**<br/>如果先前已禁用或標籤為暫停，則重新啟用選擇。<br />

<img height="21px" src="assets/check_pause_darkgrey-24px_table.png" /> **[!UICONTROL Execution suspended]**<br/>在選取的活動上暫停工作流程。<br />

<img height="21px" src="assets/checkdisable.png" /> **[!UICONTROL No execution]**<br/>停用活動。<br />

<img height="21px" src="assets/delete_darkgrey-24px_table.png" /> **[!UICONTROL Delete selection]**<br/>刪除選取的活動。<br />

<img height="21px" src="assets/copy_24px.png" /> **[!UICONTROL Copy selection]**<br/>複製選取的活動。

<img height="21px" src="assets/paste_24px.png" /> **[!UICONTROL Paste]**<br/>貼上已複製的活動。

## 快速動作 {#quick-actions}

選取活動時，快速動作按鈕會出現在活動周圍，讓您與活動互動。

<img height="21px" src="assets/edit_darkgrey-24px.png" /> **[!UICONTROL Open activity]**<br/>開啟選取的活動。

<img height="21px" src="assets/copy_24px.png" /> **[!UICONTROL Copy selection]**<br/>複製所選活動。

<img height="21px" src="assets/wkf_dlv_act_params_icon.png" /> **[!UICONTROL Open the activity's advanced options]**<br/>開啟所選電子郵件或簡訊傳送活動的進階選項。

<img height="21px" src="assets/check_darkgrey-24px_table.png" /> **[!UICONTROL Normal execution]**<br/>如果先前已禁用或標籤為暫停，則重新啟用選擇。

<img height="21px" src="assets/check_pause_darkgrey-24px_table.png" /> **[!UICONTROL Execution suspended]**<br/>在選取的活動上暫停工作流程。

<img height="21px" src="assets/checkdisable.png" /> **[!UICONTROL No execution]**<br/>停用活動。

<img height="21px" src="assets/pending_darkgrey-24px_table.png" /> **[!UICONTROL Immediate execution]**<br/>強制立即處理選取。此按鈕僅適用於<span class="uicontrol">調度程式</span>和<span class="uicontrol">等待</span>活動。

<img height="21px" src="assets/delete_darkgrey-24px_table.png" /> **[!UICONTROL Delete selection]**<br/>刪除選取的活動。

## 複製工作流程活動 {#duplicating-workflow-activities}

工作區可讓您將工作流程活動複製貼到相同的工作流程，或從相同的促銷活動例項複製到其他工作流程，以複製工作流程活動。

活動重複後，會保留其整個設定。 對於傳送活動（電子郵件、簡訊、推播通知……），附加至活動的傳送物件會重複。

>[!NOTE]
>
>工作流程活動無法從例項複製到另一個例項。 無法複製技術工作流程中的活動。

若要複製活動，請遵循下列步驟：

1. 選取活動，然後按一下快速動作中的&#x200B;**[!UICONTROL Copy selection]**&#x200B;按鈕。

   您也可以使用&#x200B;**Ctrl + C**&#x200B;鍵盤快速鍵。

   ![](assets/wkf_copypaste1.png)

1. 在目標工作流程工作區中按一下右鍵，然後按一下&#x200B;**[!UICONTROL Paste]**&#x200B;按鈕。

   您也可以使用&#x200B;**CTRL + V**&#x200B;鍵盤快速鍵。

   ![](assets/wkf_copypaste2.png)

1. 活動會重複，並包含最初已設定的所有設定。

您也可以複製並貼上多個活動，以複製整個工作流程。

要執行此操作，請通過繪製周圍區域來選取活動。 然後按一下動作列中的&#x200B;**[!UICONTROL Copy selection]**&#x200B;按鈕（或按&#x200B;**Ctrl + C**）。 然後，您可以將它們貼到所需的位置。

![](assets/wkf_copypaste3.png)
