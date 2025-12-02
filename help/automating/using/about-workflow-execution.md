---
title: 關於工作流程執行
description: 進一步瞭解工作流程執行。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 3b95fc66-d6f4-44b2-be33-925c1109a57f
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '354'
ht-degree: 8%

---

# 關於工作流程執行 {#about-workflow-execution}

工作流程一律以手動方式啟動。 不過，啟動後，它會根據[排程器](../../automating/using/scheduler.md)活動中指定的資訊，維持非使用中狀態。

>[!IMPORTANT]
>
> Adobe建議客戶不要同時執行超過20個作用中工作流程，並隨著時間安排您工作流程執行的優先順序和分佈。 如需詳細資訊，請參閱[此頁面](../../automating/using/best-practices-workflows.md)中提供的最佳實務。

與執行相關的動作（啟動、停止、暫停等）為&#x200B;**非同步**&#x200B;處理序：命令已儲存，一旦伺服器可供套用，命令就會生效。

在工作流程中，每個活動的結果通常會透過轉變（以箭頭表示）傳送到以下活動。

如果未連結至目的地活動，則不會終止轉變。

![](assets/wkf_execution_1.png)

>[!NOTE]
>
>仍可執行包含未終止轉變的工作流程：將會產生警告訊息，工作流程在轉變時會暫停，但不會產生錯誤。 您也可以在未完全完成設計的情況下開始工作流程，並隨時完成設計。

執行活動後，轉變中傳送的記錄數會顯示在其上方。

![](assets/wkf_transition_count.png)

您可以開啟轉變來檢查在執行工作流程期間或之後傳送的資料是否正確。您可以檢視資料和資料結構。

依預設，僅可存取工作流程的最後轉變的詳細資訊。 若要能夠存取先前活動的結果，您必須先核取工作流程屬性&#x200B;**[!UICONTROL Keep interim results]**&#x200B;區段中的&#x200B;**[!UICONTROL Execution]**&#x200B;選項，才能啟動工作流程。

>[!NOTE]
>
>此選項會耗用大量記憶體，其設計旨在協助建構工作流程並確保其正確設定和行為。 在生產執行個體中保留未核取的狀態。

當切換開啟時，您可以編輯其&#x200B;**[!UICONTROL Label]**&#x200B;或將&#x200B;**[!UICONTROL Segment code]**&#x200B;連結至其中。 要執行此操作，請編輯對應的欄位並確認您的修改。

使用Campaign Standard REST API，您可以&#x200B;**開始**、**暫停**、**繼續**&#x200B;和&#x200B;**停止**&#x200B;工作流程。 您可以在[API檔案中找到更多詳細資訊和REST呼叫範例。](../../api/using/controlling-a-workflow.md)
