---
title: 關於使用 Campaign 傳送訊息
description: 探索測試和傳送訊息的不同步驟。
page-status-flag: never-activated
uuid: 58666444-6e7c-4049-b2d2-8b26eabf5a82
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: about-sending-messages-with-campaign
discoiquuid: ae2eba1c-24ad-4839-afa9-5a2975570d9b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c49fcd793cbb13d26ccf3a47af145de7acd697e7

---


# 關於使用 Campaign 傳送訊息{#about-sending-messages-with-campaign}

定義目標並建立訊息內容後，您需要測試並核准內容、個人化、演算和設定，並在將訊息傳送至主要目標之前，先確定一切正確。

為此，最佳做法是：

* 準備傳送：此步驟可讓您移至分析和準備要傳送的訊息。 消息準備分析了消息的目標、個性化和有效性。 在此步驟中檢測到的錯誤必須先更正，才能繼續。 您可以視需要多次啟動訊息準備。 For more on message preparation, refer to [this section](../../sending/using/preparing-the-send.md).

   >[!NOTE]
   >
   >您可以設定全域跨通道疲勞規則，自動從促銷活動中排除過度徵求的個人檔案。 請參 [閱疲勞規則](../../sending/using/fatigue-rules.md)。

* 使用測試設定檔來預覽訊息。 For more on previewing messages, refer to [this section](../../sending/using/previewing-messages.md).
* 傳送校樣以測試訊息。 For more on proofs, refer to [this  section](../../sending/using/sending-proofs.md).
* 檢查消息呈現：請確定您的訊息會以最佳方式顯示在各種網頁用戶端、網頁郵件和裝置上。 在本節中進一步瞭解電子郵 [件轉換](../../sending/using/email-rendering.md)。

然後，您可以：

* 排程傳送：您可以定義訊息的傳送時間。 例如，您可以調整收件者時區的傳送、最佳化傳送時間或計算傳送日期。 在本節中進 [一步瞭解](../../sending/using/about-scheduling-messages.md)。
* 傳送訊息：訊息準備就緒後，您就可以開始傳送。 接著，存取記錄檔和報表便可用來監控訊息傳送，並評估促銷活動的成功。 Adobe Campaign也提供電子郵件警報系統，以追蹤傳送的成功或失敗。 在本頁中進 [一步瞭解](../../sending/using/confirming-the-send.md)。

## 相關主題

| 有用的頁面 | 其他資源 |
|---|---|
| [最佳化您的傳遞能力](../../sending/using/about-deliverability.md) | [疲勞管理](../../sending/using/fatigue-rules.md) |
| [控制傳送總處理量](../../reporting/using/delivery-throughput.md) | [設計A/B測試電子郵件](../../channels/using/designing-an-a-b-test-email.md) |
| [在失敗時接收通知](../../sending/using/receiving-alerts-when-failures-happen.md) | [監控傳送](../../sending/using/monitoring-a-delivery.md) |
| [建立控制群組](../../automating/using/workflow-control-group.md) | [傳送後續訊息](../../channels/using/follow-up-messages.md) |