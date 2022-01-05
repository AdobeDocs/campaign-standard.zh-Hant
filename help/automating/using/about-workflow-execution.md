---
title: 關於工作流程執行
description: 進一步了解工作流程執行。
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

工作流程一律手動啟動。 不過，一旦開始，就可能會維持非作用中狀態，具體取決於 [排程器](../../automating/using/scheduler.md) 活動。

>[!IMPORTANT]
>
> Adobe建議客戶不要同時執行超過20個作用中的工作流程，並排定工作流程執行的優先順序，並將其分散到不同的時間。 如需詳細資訊，請參閱 [本頁](../../automating/using/best-practices-workflows.md).

執行相關動作（開始、停止、暫停等） 為 **非同步** 流程：命令會儲存，並在伺服器可用來套用後生效。

在工作流程中，每個活動的結果通常會透過轉變（以箭頭表示）傳送至下列活動。

如果轉變未連結至目的地活動，則會取消終止。

![](assets/wkf_execution_1.png)

>[!NOTE]
>
>仍可執行包含未終止轉變的工作流程：系統會產生警告訊息，且工作流程一旦到達轉變就會暫停，但這不會產生錯誤。 您也可以在完成設計的情況下開始工作流程，並隨時完成。

執行活動後，轉變中傳送的記錄數會顯示在其上方。

![](assets/wkf_transition_count.png)

您可以開啟轉變來檢查在執行工作流程期間或之後傳送的資料是否正確。您可以檢視資料和資料結構。

依預設，只能存取工作流程最後轉變的詳細資訊。 若要存取前述活動的結果，您必須檢查 **[!UICONTROL Keep interim results]** 選項 **[!UICONTROL Execution]** 區段，然後再開始工作流程。

>[!NOTE]
>
>此選項佔用大量記憶體，旨在協助建構工作流程並確保其正確設定和行為。 在生產執行個體中保留未核取的狀態。

開啟轉變時，您可以編輯其 **[!UICONTROL Label]** 或連結 **[!UICONTROL Segment code]** 對它。 若要這麼做，請編輯對應的欄位並確認您的修改。

使用Campaign StandardREST API，您可以 **開始**, **暫停**, **繼續** 和 **停止** 工作流程。 您可以在 [API檔案。](../../api/using/controlling-a-workflow.md)
