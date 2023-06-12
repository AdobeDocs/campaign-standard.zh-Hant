---
title: 關於工作流程執行
description: 進一步瞭解工作流程執行。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 3b95fc66-d6f4-44b2-be33-925c1109a57f
source-git-commit: 6ca3ffe3ba2cf7629e511e4ba035b170b25ad79e
workflow-type: tm+mt
source-wordcount: '353'
ht-degree: 8%

---

# 關於工作流程執行 {#about-workflow-execution}

工作流程一律以手動方式啟動。 不過，啟動後，視中指定的資訊而定，此功能可能會維持非使用中。 [排程器](../../automating/using/scheduler.md) 活動。

>[!IMPORTANT]
>
> Adobe建議客戶不要同時執行超過20個作用中工作流程，並隨著時間安排工作流程執行的優先順序和分佈。 如需詳細資訊，請參閱中提供的最佳實務 [此頁面](../../automating/using/best-practices-workflows.md).

執行相關動作（啟動、停止、暫停等） 是 **非同步** 處理序：命令已儲存，一旦伺服器可供套用，命令就會生效。

在工作流程中，每個活動的結果通常會透過轉變（以箭頭表示）傳送到以下活動。

如果轉變未連結至目的地活動，則轉變不會終止。

![](assets/wkf_execution_1.png)

>[!NOTE]
>
>仍可執行包含未終止轉變的工作流程：將會產生警告訊息，且工作流程在轉變時會暫停，但不會產生錯誤。 您也可以在未完全完成設計的情況下開始工作流程，並隨時完成設計。

執行活動後，轉變中傳送的記錄數會顯示在活動上方。

![](assets/wkf_transition_count.png)

您可以開啟轉變來檢查在執行工作流程期間或之後傳送的資料是否正確。您可以檢視資料和資料結構。

依預設，只能存取工作流程的最後一個轉變的詳細資訊。 若要存取前述活動的結果，您必須檢查 **[!UICONTROL Keep interim results]** 中的選項 **[!UICONTROL Execution]** 區段（在啟動工作流程之前）。

>[!NOTE]
>
>此選項會耗用大量記憶體，且設計旨在協助建構工作流程，並確保工作流程已正確設定且運作正常。 在生產執行個體中保留未核取的狀態。

當轉變開啟時，您可以編輯其 **[!UICONTROL Label]** 或連結 **[!UICONTROL Segment code]** 至此。 要執行此操作，請編輯對應的欄位並確認您的修改。

使用Campaign Standard REST API，您可以 **開始**， **pause**， **繼續** 和 **停止** 工作流程。 您可以在「 」中找到更多詳情和REST呼叫範例 [API檔案。](../../api/using/controlling-a-workflow.md)
