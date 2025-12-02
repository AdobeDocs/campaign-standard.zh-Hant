---
title: 工作流程介面
description: 瞭解建立、編輯及執行工作流程的介面和選項。
audience: automating
content-type: reference
topic-tags: about-workflows-and-data-management
context-tags: workflow,main;workflow,overview
feature: Workflows
old-role: Data Architect
role: Developer
level: Beginner
exl-id: a3f35bb9-e61e-4f3f-b855-1d677422f75a
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '829'
ht-degree: 4%

---

# 工作流程介面{#workflow-interface}

您可以建立工作流程，以管理行銷活動和方案中的整個流程。

工作流程編輯畫面由下列元素組成：

* 參考可用活動的[浮動視窗](#palette)。
* 設定並組織活動的[Workspace](#workspace)。
* [動作列](#action-bar)是由按鈕所組成，可讓您與工作流程及/或其元件互動。
* 所選活動週圍出現的[快速動作](#quick-actions)可讓您與其互動。

![](assets/wkf_overview.png)

![](assets/do-not-localize/how-to-video.png) [探索如何在視訊中建立工作流程](#video)

## 調色盤 {#palette}

浮動視窗位於熒幕的左側。 所有可用的活動都會分類為數個類別：

* [目標定位](../../automating/using/about-targeting-activities.md)：目標定位、操控母體資料和篩選活動的特定活動
* [執行](../../automating/using/about-execution-activities.md)：組織和執行工作流程的特定活動
* [管道](../../automating/using/about-channel-activities.md)：代表不同可用通訊管道的活動
* [資料管理(ETL)](../../automating/using/about-data-management-activities.md)：操控資料的特定活動

若要在工作流程中使用浮動視窗中的活動，請將其拖放至您的工作區中。

在啟動工作流程之前，您必須先設定從浮動視窗新增的每個活動。

![](assets/workflow_palette.png)

## 工作區 {#workspace}

工作區是工作流程編輯器中的中央區域。 您可以在此區域中拖放活動、使用轉變將它們連結在一起，以及進行設定。

若要連結兩個活動，請將箭頭的結尾從第一個活動上移至下一個活動，直到它們連線為止。 您也可以將活動往後箭頭的點移動，以便將其連結至前一個活動。 如果您移動任何活動，它們將會維持連結。

處理資料的活動之後的轉變包含中介母體。 如果您核取工作流程屬性的&#x200B;**[!UICONTROL Keep interim results]**&#x200B;區段中的&#x200B;**[!UICONTROL Execution]**&#x200B;選項，便可存取它們。

>[!CAUTION]
>
>此選項佔用了大量磁碟空間，設計旨在幫助您建構工作流程並確保正確的設定和行為。在生產執行個體中保留未核取的狀態。


選取活動時，快速動作會出現在活動週圍，允許您與其互動。 例如，若要設定活動，請選取該活動，然後使用快速動作中的![](assets/edit_darkgrey-24px_table.png)按鈕將其開啟。

某些功能只能在工作區中啟用：

* 透過在活動與轉接周圍繪製區域來選取它們。
* 按下&#x200B;**Ctrl** +按一下滑鼠左鍵以選取數個活動和/或轉變。
* 按下&#x200B;**Enter**&#x200B;以檢視目前所選活動或轉變的詳細資料。
* 按&#x200B;**Delete**&#x200B;刪除目前選取的活動。
* 按下&#x200B;**Ctrl + C**&#x200B;以複製選取的活動，並按下&#x200B;**Ctrl + V**&#x200B;以將其貼到工作區中。

![](assets/workflow_workspace.png)

## 動作列 {#action-bar}

根據在工作區中選取的元素或工作流程的執行狀態，動作列中的可用按鈕可能會有所不同。

<img height="21px" src="assets/edit_darkgrey-24px.png" /> **[!UICONTROL Open activity]**<br/>可讓您編輯工作流程的內容。

<img height="21px" src="assets/play_darkgrey-24px_table.png" /> **[!UICONTROL Start]**<br/>啟動工作流程。

<img height="21px" src="assets/pause_darkgrey-24px_table.png" /> **[!UICONTROL Pause]**<br/>暫停工作流程。

<img height="21px" src="assets/stop_darkgrey-24px_table.png" /> **[!UICONTROL Stop]**<br/>中斷工作流程執行。 無法從停止的地方繼續。

<img height="21px" src="assets/pauseplay_darkgrey-24px_table.png" /> **[!UICONTROL Restart]**<br/>重新啟動工作流程。

<img height="21px" src="assets/printpreview_darkgrey-24px_table.png" /> **[!UICONTROL Log and tasks]**<br/>開啟工作流程的執行記錄。

<img height="21px" src="assets/checkcircle_darkgrey-24px_table.png" /> **[!UICONTROL Enable multi-selection]**<br/>啟用多重選取模式。 工作流程必須至少由兩個活動組成。

<img height="21px" src="assets/closecircle_darkgrey-24px_table.png" /> **[!UICONTROL Disable multi-selection]**<br/>停用多重選取模式。<br />

<img height="21px" src="assets/targeted.png" /> **[!UICONTROL Open transition]**<br/>開啟選取的轉變。<br />

<img height="21px" src="assets/check_darkgrey-24px_table.png" />  **[!UICONTROL Normal execution]**<br/>如果選取專案先前已停用或標籤為已暫停，則重新啟用選取專案。<br />

<img height="21px" src="assets/check_pause_darkgrey-24px_table.png" /> **[!UICONTROL Execution suspended]**<br/>在選取的活動暫停工作流程。<br />

<img height="21px" src="assets/checkdisable.png" /> **[!UICONTROL No execution]**<br/>停用活動。<br />

<img height="21px" src="assets/delete_darkgrey-24px_table.png" /> **[!UICONTROL Delete selection]**<br/>刪除選取的活動。<br />

<img height="21px" src="assets/copy_24px.png" /> **[!UICONTROL Copy selection]**<br/>複製選取的活動。

<img height="21px" src="assets/paste_24px.png" /> **[!UICONTROL Paste]**<br/>貼上已複製的活動。

## 快速動作 {#quick-actions}

選取活動時，快速動作按鈕會出現在活動週圍，可讓您與活動互動。

<img height="21px" src="assets/edit_darkgrey-24px.png" /> **[!UICONTROL Open activity]**<br/>開啟選取的活動。

<img height="21px" src="assets/copy_24px.png" /> **[!UICONTROL Copy selection]**<br/>複製選取的活動。

<img height="21px" src="assets/wkf_dlv_act_params_icon.png" /> **[!UICONTROL Open the activity's advanced options]**<br/>開啟所選電子郵件或簡訊傳送活動的進階選項。

<img height="21px" src="assets/check_darkgrey-24px_table.png" /> **[!UICONTROL Normal execution]**<br/>如果選取專案先前已停用或標籤為已暫停，則重新啟用選取專案。

<img height="21px" src="assets/check_pause_darkgrey-24px_table.png" /> **[!UICONTROL Execution suspended]**<br/>在選取的活動暫停工作流程。

<img height="21px" src="assets/checkdisable.png" /> **[!UICONTROL No execution]**<br/>停用活動。

<img height="21px" src="assets/pending_darkgrey-24px_table.png" /> **[!UICONTROL Immediate execution]**<br/>強制立即處理選取專案。 此按鈕僅適用於<span class="uicontrol">排程器</span>和<span class="uicontrol">等待</span>活動。

<img height="21px" src="assets/delete_darkgrey-24px_table.png" /> **[!UICONTROL Delete selection]**<br/>刪除選取的活動。

## 複製工作流程活動 {#duplicating-workflow-activities}

工作區可讓您複製工作流程活動，將其貼到相同的工作流程中，或貼到來自相同Campaign執行個體的另一個工作流程中。

活動複製後，會保留其整個設定。 對於傳送活動（電子郵件、簡訊、推播通知……），附加至活動的傳送物件會重複。

>[!NOTE]
>
>無法將工作流程活動從一個執行個體複製到另一個執行個體。 來自技術工作流程的活動不能重複。

若要複製活動，請遵循下列步驟：

1. 選取活動，然後按一下快速動作中的&#x200B;**[!UICONTROL Copy selection]**&#x200B;按鈕。

   您也可以使用&#x200B;**Ctrl + C**&#x200B;鍵盤快速鍵。

   ![](assets/wkf_copypaste1.png)

1. 在目標工作流程工作區中按一下滑鼠右鍵，然後按一下&#x200B;**[!UICONTROL Paste]**&#x200B;按鈕。

   您也可以使用&#x200B;**CTRL + V**&#x200B;鍵盤快速鍵。

   ![](assets/wkf_copypaste2.png)

1. 活動會重複，其中包含最初設定的所有設定。

您也可以複製並貼上多個活動，讓您複製整個工作流程。

要執行此操作，請透過在活動週圍繪製區域來選取活動。 然後按一下動作列中的&#x200B;**[!UICONTROL Copy selection]**&#x200B;按鈕（或按&#x200B;**Ctrl + C**）。 然後，您就可以將它們貼到所需的位置。

![](assets/wkf_copypaste3.png)

## 教學課程影片 {#video}

本影片說明如何建立工作流程。

>[!VIDEO](https://video.tv.adobe.com/v/23937?quality=12)

[此處](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=zh-Hant)提供其他Campaign Standard操作說明影片。
