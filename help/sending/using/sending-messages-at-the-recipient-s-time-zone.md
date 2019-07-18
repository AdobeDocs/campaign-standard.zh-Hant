---
title: 在收件者的時區傳送訊息
seo-title: 在收件者的時區傳送訊息
description: 在收件者的時區傳送訊息
seo-description: 瞭解如何在收件人的時區傳送訊息。
page-status-flag: 從未啓動
uuid: 70228c07-451f-4ddb-8d26-92a5a4814e3a
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 傳送
content-type: reference
topic-tags: sheduling-messages
discoiquuid: daa980ba-8c7c-4673-a68 f-379d63 e4 b8 bd
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 806dc4736ffb395a0eea102090c688102478aaca

---


# Sending messages at the recipient's time zone{#sending-messages-at-the-recipient-s-time-zone}

在管理日期和時間的促銷活動時，您可以排程每個收件者當地時間的傳送時間：他們會在您排程的時區收到電子郵件、簡訊或推播通知。

>[!NOTE]
>
>To use this functionality, make sure that all profiles targeted by your delivery have a time zone specified in the **[!UICONTROL Address]** section of their properties. For more information on accessing profile properties, refer to this [section](../../audiences/using/editing-profiles.md).

To send a delivery at the recipient's time zone, you can also use the **[!UICONTROL Scheduler]** activity in a workflow. For more on this, refer to this [page](../../automating/using/scheduler.md).

在下列範例中，我們想要傳送僅適用於世界所有客戶的促銷代碼。為了提供充足的時間使用它，所有客戶都必須在月14日上午8：00(視時區而定)收到您的訊息。

1. **[!UICONTROL Marketing activities]** 在標籤中，從我們的個案開始建立您的傳送。To learn more on delivery creation, refer to this [section](../../channels/using/creating-an-email.md).
1. After designing your Valentine's Day email, click **[!UICONTROL Create]** to access the delivery dashboard. For more on email designing, refer to this [page](../../designing/using/example--email-personalization.md).

   ![](assets/send-time_opt_valentine_1.png)

1. From the delivery dashboard, select the **[!UICONTROL Schedule]** block.

   ![](assets/send-time_opt_valentine_2.png)

1. Select the **[!UICONTROL Messages to be sent automatically on the date]** option specified below. Then in the **[!UICONTROL Start sending from]** field, set the contact date, in our case February 14th at 8:00 AM so that every recipient receives it on Valentine's Day.

   ![](assets/send-time_opt_valentine.png)

1. In the **[!UICONTROL Time zone of the contact date]** field, select at which time zone your delivery should be sent by default.

   If a profile's **[!UICONTROL Time zone]** is left as **[!UICONTROL Default]**, the recipients will receive the delivery depending on the chosen time zone here.

1. From the **[!UICONTROL Optimize the sending time per recipient]** drop-down menu, choose **[!UICONTROL Send at the recipient's time zone]**. 這可讓收件者在二月收到Valentine的日電子郵件，視其時區而定。

   ![](assets/send-time_opt_valentine_3.png)

1. After confirming your schedule for your delivery, click the **[!UICONTROL Prepare]** button then **[!UICONTROL Confirm]** your delivery.

   請務必提前24小時確認傳送。否則，有些收件者可能會在實際Valentine當天事件之前收到傳送。

   ![](assets/send-time_opt_valentine_4.png)

不論位於何處，所有收件者都會在月14日早上8：00收到訊息。
