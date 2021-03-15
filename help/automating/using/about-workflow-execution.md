---
solution: Campaign Standard
product: campaign
title: 關於工作流程執行
description: 進一步瞭解工作流程執行。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: 工作流程
role: 資料架構師
level: 中級
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 8%

---


# 關於工作流程執行 {#about-workflow-execution}

工作流程一律以手動方式啟動。 但是，啟動後，它可以保持非活動狀態，具體取決於[調度程式](../../automating/using/scheduler.md)活動中指定的資訊。

>[!CAUTION]
>
> Adobe建議客戶排定工作流程執行的優先順序，並執行最多20個並行工作流程執行，以一致地在執行個體間達到最佳效能。 可計畫並行執行超過20個工作流，預設情況下將按順序執行。 您可以將票證提交給客戶服務，以調整併發工作流執行的最大數量的預設設定。

執行相關動作（開始、停止、暫停等） are **asynchronous** processes:命令將保存，並在伺服器可用來應用該命令後生效。

在工作流程中，每個活動的結果通常會透過轉場（以箭頭表示）傳送至下列活動。

如果轉移未連結至目標活動，則不會終止。

![](assets/wkf_execution_1.png)

>[!NOTE]
>
>仍可執行包含未終止轉場的工作流程：將會產生警告訊息，工作流程在轉場時會暫停，但不會產生錯誤。 您也可以開始工作流程，而不需完成設計，而且可以隨時完成設計。

執行活動後，轉場中傳送的記錄數就會顯示在其上方。

![](assets/wkf_transition_count.png)

您可以開啟轉變來檢查在執行工作流程期間或之後傳送的資料是否正確。您可以檢視資料和資料結構。

依預設，只能存取工作流程上次轉換的詳細資訊。 要能夠訪問前述活動的結果，您需要在啟動工作流屬性的&#x200B;**[!UICONTROL Execution]**&#x200B;部分中檢查&#x200B;**[!UICONTROL Keep interim results]**&#x200B;選項。

>[!NOTE]
>
>此選項會耗用大量記憶體，並可協助建立工作流程，並確保其正確設定和運作。 在生產執行個體中保留未核取的狀態。

開啟轉場時，您可以編輯其&#x200B;**[!UICONTROL Label]**，或將&#x200B;**[!UICONTROL Segment code]**&#x200B;連結至該轉場。 若要這麼做，請編輯對應的欄位並確認您的修改。

使用Campaign StandardREST API，您可以&#x200B;**start**、**pause**、**resume**&#x200B;和&#x200B;**stop**&#x200B;工作流。 您可以在[API檔案中找到更多REST呼叫的詳細資訊和範例。](../../api/using/controlling-a-workflow.md)
