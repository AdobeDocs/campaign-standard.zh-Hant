---
title: 最佳化傳送時間
description: 瞭解如何設定傳送時間並改善訊息的開放率。
page-status-flag: 從未激活
uuid: c2c13934-9819-4e18-b5c7-60915c907f37
contentOwner: 紹維亞
products: SG_CAMPAIGN/STANDARD
audience: 發送
content-type: 參考
topic-tags: 調度消息
discoiquuid: 609355f6-9003-41b9-9981-ea787419fbf5
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 最佳化傳送時間{#optimizing-the-sending-time}

若要改善訊息的開啟率，您可以手動定義每個收件者的傳送時間。 每個描述檔都會在指定的日期和時間收到訊息。

您可以在傳送層級或使用工作流程來定義傳送時間。

對於電子郵件，視伺服器負載和重試次數而定，會盡力在每個收件者排程的日期和時間傳送訊息。

* 重試次數取決於網際網路提供者和您的信譽。 第一次嘗試時可能不接受該消息，並且可以執行多次重試。 請參 [閱電子郵件渠道參數清單](../../administration/using/configuring-email-channel.md)。
* 由於頻寬不足，可能會延遲接收電子郵件。

您可以在傳送記錄中檢視訊息傳送給每個收件者 [的時間](../../sending/using/monitoring-a-delivery.md#sending-logs)。

有數個選項可供使用：

* **[!UICONTROL No optimization]**:訊息會在使用者的時間傳送。

   例如，如果您的時區是GMT+1，而您在欄位中輸入9:00 AM，則位於 **[!UICONTROL Start sending from]** GMT+3時區的收件者將於當地時間上午11:00收到該收件者的訊息。

* **[!UICONTROL Send at the recipient's time zone]**:所有收件者都會收到訊息，其時區已納入考量。

   例如，如果您在欄位中輸入9:00 AM，則位於 **[!UICONTROL Start sending from]** GMT+3時區的收件者將於當地時間上午9:00收到該收件者的訊息。

   See [Sending messages at the recipient's time zone](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md).

* **[!UICONTROL Send at a custom date defined by a formula]**:每位收件者都會在指定公式設定的日期和時間收到訊息。

   See [Computing the sending date](../../sending/using/computing-the-sending-date.md).

