---
title: 最佳化傳送時間
seo-title: 最佳化傳送時間
description: 最佳化傳送時間
seo-description: 瞭解如何設定傳送時間並改善訊息的打開率。
page-status-flag: 從未啓動
uuid: c2c13934-9819-4e18-b5 c7-60915c907 f37
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 傳送
content-type: reference
topic-tags: sheduling-messages
discoiquuid: 609355f6-9003-41b9-9981-ea778419 ffb5
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6a877d878f01fa1e541dc20b8b0941602113d15b

---


# Optimizing the sending time{#optimizing-the-sending-time}

為改善訊息的打開率，您可以手動定義每位收件者的傳送時間。每個描述檔會在指定的日期和時間收到訊息。

您可以在傳送層級或使用工作流程來定義傳送時間。

對於電子郵件，視伺服器負載和重試量而定，將會盡力在每個收件者的日期和時間傳送訊息。

* 試用版取決於網際網路提供者和您的聲譽。第一次嘗試時可能無法接受訊息，而且可能會執行數次重試。See [List of email channel parameters](../../administration/using/configuring-email-channel.md).
* 收到電子郵件時可能會因為頻寬不足而發生延遲。

You can view when the message was sent to each recipient in the [sending logs](../../sending/using/monitoring-a-delivery.md#sending-logs).

有幾個選項可供使用：

* **[!UICONTROL No optimization]**：訊息會在使用者的時間傳送。

   For example, if your time zone is GMT+1 and if you enter 9:00 AM in the **[!UICONTROL Start sending from]** field, a recipient located in the GMT+3 time zone will receive the message at 11:00 AM local time for that recipient.

* **[!UICONTROL Send at the recipient's time zone]**：所有收件者都會收到考量其時區的訊息。

   For example, if you enter 9:00 AM in the **[!UICONTROL Start sending from]** field, a recipient located in the GMT+3 time zone will receive the message at 9:00 AM local time for that recipient.

   See [Sending messages at the recipient's time zone](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md).

* **[!UICONTROL Send at a custom date defined by a formula]**：每位收件者都會收到指定公式所設定的日期和時間訊息。

   See [Computing the sending date](../../sending/using/computing-the-sending-date.md).

