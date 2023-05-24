---
title: 關於工作流程執行
description: 瞭解有關工作流執行的詳細資訊。
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

工作流始終手動啟動。 但是，一旦啟動，它可以保持非活動狀態，具體取決於 [調度程式](../../automating/using/scheduler.md) 的子菜單。

>[!IMPORTANT]
>
> Adobe建議客戶不要同時運行20個以上的活動工作流執行，並建議客戶確定工作流執行的優先順序並將其分散。 有關詳細資訊，請參閱 [此頁](../../automating/using/best-practices-workflows.md)。

執行相關操作（啟動、停止、暫停等） 是 **非同步** 進程：命令已保存，一旦伺服器可用於應用該命令，該命令將生效。

在工作流中，每個活動的結果通常通過箭頭表示的轉換發送到以下活動。

如果轉移未連結到目標活動，則它將不終止。

![](assets/wkf_execution_1.png)

>[!NOTE]
>
>仍然可以執行包含未終止的轉換的工作流：將生成警告消息，工作流到達轉換後將暫停，但不會生成錯誤。 您也可以在完成設計後啟動工作流，並在繼續時完成它。

執行活動後，在轉移中發送的記錄數將顯示在其上。

![](assets/wkf_transition_count.png)

您可以開啟轉變來檢查在執行工作流程期間或之後傳送的資料是否正確。您可以查看資料和資料結構。

預設情況下，只能訪問工作流上次轉換的詳細資訊。 要能夠訪問上述活動的結果，您需要檢查 **[!UICONTROL Keep interim results]** 的上界 **[!UICONTROL Execution]** 的子菜單。

>[!NOTE]
>
>此選項佔用大量記憶體，旨在幫助構建工作流並確保其正確配置和運行。 在生產執行個體中保留未核取的狀態。

開啟過渡時，可以編輯其 **[!UICONTROL Label]** 或連結 **[!UICONTROL Segment code]** 對它來說。 為此，請編輯相應欄位並確認修改。

使用Campaign StandardREST API，您可以 **開始**。 **暫停**。 **恢復** 和 **停止** 工作流。 您可以在 [API文檔。](../../api/using/controlling-a-workflow.md)
