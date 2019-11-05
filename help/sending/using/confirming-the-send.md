---
title: 確認傳送
description: 瞭解如何完成訊息準備。
page-status-flag: 從未激活
uuid: 1eaecb32-ffd2-45d0-a8b4-f97be59a1bd
contentOwner: 紹維亞
products: SG_CAMPAIGN/STANDARD
audience: 發送
content-type: 參考
topic-tags: 傳送和追蹤訊息
discoiquuid: 8bb160b1-7de9-4c1f-bb89-b2e5fdafed41
context-tags: 交付，部署，返回
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 確認傳送{#confirming-the-send}

在您準備完訊息並執行核准步驟後，即可傳送訊息。 有關消息準備的詳細資訊，請參 [閱準備發送](../../sending/using/preparing-the-send.md)。

只有具有角色的 **[!UICONTROL Start deliveries]** 使用者可確認傳送。 有關詳細資訊，請參閱「角 [色清單](../../administration/using/list-of-roles.md) 」部分。

沒有此角色的使用者會看到下列訊息：

![](assets/confirm_delivery_2.png)

若要傳送傳送，請按一 **[!UICONTROL Confirm send]** 下訊息動作列中的按鈕。

![](assets/confirm_delivery.png)

系統會要求您按一下按鈕，以最終完成傳送 **[!UICONTROL OK]** 作業。

![](assets/confirm_delivery1.png)

正在傳送訊息。

>[!NOTE]
>
>如果訊息已排程，則會在到達傳送時間時傳送訊息。 For more on scheduling messages, refer to [this section](../../sending/using/about-scheduling-messages.md).

如果您使用不含匯總期間的循環傳送，則可在傳送傳送前要求確認。 若要這麼做，請開啟 **[!UICONTROL Schedule]** 傳送控制面板的區塊，然後啟動專用選項。

![](assets/confirmation_recurring_deliveries.png)

塊 **[!UICONTROL Deployment]** 顯示發送的進度。

將消息發送到聯繫人後，區域將 **[!UICONTROL Deployment]** 顯示您的KPI（關鍵績效指標）資料，包括：

* 要傳送的訊息數
* 已發送的消息數
* 傳送的訊息百分比
* 彈回數和錯誤的百分比
* 開啟的消息的百分比
* 訊息中的點按百分比（電子郵件）

   >[!NOTE]
   >
   >和 **[!UICONTROL Open rate]** 每 **[!UICONTROL Click-through rate]** 小時更新一次。

![](assets/sending_delivery.png)

如果KPI更新時間太長或未考慮到傳送記錄檔的結果，請按一下視窗 **[!UICONTROL Compute stats]** 中的按 **[!UICONTROL Deployment]** 鈕。

![](assets/sending_delivery7.png)

您可以在其中一個用戶端描述檔的歷史記錄中檢視訊息，這些描述檔是觀眾的一部分。 See [Integrated customer profile](../../audiences/using/integrated-customer-profile.md).

傳送訊息後，您可以追蹤收件者的行為，並監控訊息，以評估其影響。 如需更多相關資訊，請參閱以下章節：

* [追蹤訊息](../../sending/using/tracking-messages.md)
* [監控傳送](../../sending/using/monitoring-a-delivery.md)

