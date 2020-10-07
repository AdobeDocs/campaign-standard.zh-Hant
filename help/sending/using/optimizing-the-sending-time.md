---
title: 最佳化傳送時間
description: 瞭解如何設定傳送時間並改善訊息的開放率。
page-status-flag: never-activated
uuid: c2c13934-9819-4e18-b5c7-60915c907f37
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: sheduling-messages
discoiquuid: 609355f6-9003-41b9-9981-ea787419fbf5
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 最佳化傳送時間{#optimizing-the-sending-time}

若要改善訊息的開啟率，您可以手動定義每個收件者的傳送時間。每個設定檔都會在指定的日期和時間收到訊息。

您可以在傳送層級或使用工作流程來定義傳送時間。

對於電子郵件，視伺服器負載和重試次數而定，會盡力在每個收件者排程的日期和時間傳送訊息。

* 重試次數視網際網路提供者與您的信譽而定。第一次嘗試時可能不接受該訊息，並且可以執行多次重試。請參閱[電子郵件通道參數清單](../../administration/using/configuring-email-channel.md)。
* 由於頻寬不足，可能會延遲接收電子郵件。

您可以在[傳送記錄檔](../../sending/using/monitoring-a-delivery.md#sending-logs)中檢視訊息傳送給每個收件者的時間。

有數個選項可供使用：

* **[!UICONTROL No optimization]**：訊息會在使用者的時間傳送。

   例如，如果您的時區是 GMT+1，而您在 **[!UICONTROL Start sending from]** 欄位中輸入 9:00 Am，則位於 GMT+3 時區的收件者將於當地時間上午 11:00 收到該收件者的訊息。

* **[!UICONTROL Send at the recipient's time zone]**：所有收件者都會收到訊息，其時區已納入考量。

   例如，如果您在 **[!UICONTROL Start sending from]** 欄位中輸入 9:00 Am，則位於 GMT+3 時區的收件者將於當地時間上午 9:00 收到該收件者的訊息。

   請參閱[在收件者的時區傳送訊息](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)。

* **[!UICONTROL Send at a custom date defined by a formula]**：每位收件者都會在指定公式設定的日期和時間收到訊息。

   請參閱[計算傳送日期](../../sending/using/computing-the-sending-date.md)。

