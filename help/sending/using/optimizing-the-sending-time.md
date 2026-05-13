---
title: 最佳化傳送時間
description: 瞭解如何設定傳送時間並改善訊息的開放率。
audience: sending
content-type: reference
topic-tags: sheduling-messages
feature: Send Time Optimization
role: User
level: Intermediate
exl-id: f35b46c6-de88-4efa-b3b7-8bb9024e40a8
TQID: https://experienceleague.adobe.com/FjL5t1ohvrgDdqLiCr03z1Nbq6IukIBysKkmXJ7561c
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 279
ht-degree: 74%

---

# 最佳化傳送時間{#optimizing-the-sending-time}

若要改善訊息的開啟率，您可以手動定義每個收件者的傳送時間。 每個輪廓都會在指定的日期和時間收到訊息。

您可以在傳送層級或使用工作流程來定義傳送時間。

對於電子郵件，視伺服器負載和重試次數而定，會盡力在每個收件者排程的日期和時間傳送訊息。

* 重試次數視網際網路提供者與您的信譽而定。 第一次嘗試時可能不接受該訊息，並且可以執行多次重試。 請參閱[電子郵件通道參數清單](../../administration/using/configuring-email-channel.md)。
* 由於頻寬不足，可能會延遲接收電子郵件。

您可以在[傳送記錄檔](../../sending/using/monitoring-a-delivery.md#sending-logs)中檢視訊息傳送給每個收件者的時間。

有數個選項可供使用：

* **[!UICONTROL No optimization]**：訊息會在使用者的時間傳送。

  例如，如果您的時區是GMT+1，而您在&#x200B;**[!UICONTROL Start sending from]**&#x200B;欄位中輸入9:00 Am，則位於GMT+3時區的收件者將於當地時間上午11:00收到該收件者的訊息。

* **[!UICONTROL Send at the recipient's time zone]**：所有收件者都會收到訊息，其時區已納入考量。

  例如，如果您在&#x200B;**[!UICONTROL Start sending from]**&#x200B;欄位中輸入9:00 Am，則位於GMT+3時區的收件者將於當地時間上午9:00收到該收件者的訊息。

  請參閱[在收件者的時區傳送訊息](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)。

* **[!UICONTROL Send at a custom date defined by a formula]**：每位收件者都會在指定公式設定的日期和時間收到訊息。

  請參閱[計算傳送日期](../../sending/using/computing-the-sending-date.md)。
