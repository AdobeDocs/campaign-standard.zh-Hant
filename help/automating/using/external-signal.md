---
title: 外部訊號
description: 當某些條件在另一個工作流程中成功符合時，外部訊號活動會觸發工作流。
page-status-flag: never-activated
uuid: 884b6daf-bfd9-440b-8336-004b80c76def
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 911c71b5-da8b-4916-b645-13bba6d21715
context-tags: signal,main
translation-type: tm+mt
source-git-commit: 121b36056317cc89909607220f988c02ae470f08
workflow-type: tm+mt
source-wordcount: '600'
ht-degree: 96%

---


# 外部訊號{#external-signal}

## 說明 {#description}

![](assets/signal.png)

某些條件在另一個工作流程或 REST API 呼叫中成功符合時，**[!UICONTROL External signal]** 活動會觸發工作流程。

## 使用內容 {#context-of-use}

**[!UICONTROL External signal]** 活動可用來組織和協調不同的流程，這些流程是同一客戶歷程中不同工作流程的一部分。它允許從另一個工作流程開始，以支援更複雜的客戶歷程，同時更能監控和回應問題。

**[!UICONTROL External signal]** 活動設計作為工作流程的第一個活動。可從其他工作流程 **[!UICONTROL End]** 的活動或REST API呼叫（如需詳細資訊，請參閱 [API檔案](../../api/using/triggering-a-signal-activity.md)）觸發。

觸發時，可定義外部參數，並可在工作流程事件變數中使用。使用外部參數呼叫工作流程的過程在[本區段](../../automating/using/calling-a-workflow-with-external-parameters.md)進行詳細說明。

>[!NOTE]
>
>活動觸發頻率不得超過每　10 分鐘一次。

請注意，活動 **[!UICONTROL External signal]** 可從數個不同的事件觸發。在這種情況下，當 **[!UICONTROL External signal]** 執行其中一個來源工作流程或 API 呼叫時，就會立即觸發。它不需要完成所有來源工作流程。

**相關主題**

* [使用案例：外部信號活動和資料導入](../../automating/using/external-signal-data-import.md)。
* [使用案例：呼叫工作流程，以使用外部參數從檔案建立觀眾](../../automating/using/use-case-calling-workflow.md)

## 設定 {#configuration}

設定外部訊號時，首先必須在目標工作流程中設定 **[!UICONTROL External signal]** 活動。完成此設定後，此工作流程的 **[!UICONTROL External signal]** 活動將可用於設定來源工作流程的 **[!UICONTROL End]** 活動。

1. 將　**[!UICONTROL External signal]**　活動拖放至您的目標工作流程。
1. 選取活動，然後使用所顯示快速操作中的 ![](assets/edit_darkgrey-24px.png) 按鈕將其開啟。
1. 編輯活動的標籤。設定觸發 **[!UICONTROL External signal]** 的來源工作流程時需要此標籤。

   如果要使用參數呼叫工作流程，請使用 **[!UICONTROL Parameters]** 區域來進行宣告。有關詳細資訊，請參見[此頁面](../../automating/using/declaring-parameters-external-signal.md)。

   ![](assets/external_signal_configuration.png)

1. 確認活動的設定、新增您需要的任何其他活動並儲存工作流程。

   >[!NOTE]
   >
   >如果要從另一個工作流程觸發目標工作流程，請繼續下列步驟。如果您想要從 REST API 呼叫觸發目標工作流程，請參閱 [API 文件](../../api/using/triggering-a-signal-activity.md)，以取得詳細資訊。

1. 開啟來源工作流程並選取 **[!UICONTROL End]** 活動。如果沒有可用 **[!UICONTROL End]** 活動，請在工作流程分支的最後一個活動後新增一個活動。

   有些活動預設沒有任何出站轉變。從這些 **[!UICONTROL Properties]** 活動的索引標籤中，可以新增出站轉變。

   例如，在 **[!UICONTROL Update data]** 活動中，移至 **[!UICONTROL Transitions]** 索引標籤並核取選項 **[!UICONTROL Add an outbound transition without the population]**。此選項可新增不含任何資料且不佔用系統中任何不必要的空間的轉變。它只是用來連接觸發目標工作流程的額外 **[!UICONTROL End]** 活動。

   ![](assets/external_signal_empty_transition.png)

1. 在 **[!UICONTROL End]** 活動 **[!UICONTROL External signal]** 索引標籤中，選取目標工作流程以及要在該工作流程中觸發的 **[!UICONTROL External signal]** 活動。

   當您設定 **[!UICONTROL End]** 活動以觸發另一個工作流程時，其圖示會以其他訊號符號更新。

   如果要使用參數呼叫工作流程，請使用 **[!UICONTROL Parameters and values]** 區域。有關詳細資訊，請參見[此頁面](../../automating/using/defining-parameters-calling-workflow.md)。

   ![](assets/external_signal_end.png)

1. 保存來源工作流程。

執行來源工作流程或 REST API 呼叫的 **[!UICONTROL End]** 活動後，目標工作流程將自動從活動觸發 **[!UICONTROL External signal]**。

>[!NOTE]
>
>目標工作流程必須先手動啟動，才能觸發。啟動後，將啟動 **[!UICONTROL External activity]** 並等待來源工作流程中的訊號。
