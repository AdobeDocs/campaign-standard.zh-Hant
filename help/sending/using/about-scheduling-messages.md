---
title: 關於排程訊息
seo-title: 關於排程訊息
description: 關於排程訊息
seo-description: 瞭解如何排程您的訊息。
page-status-flag: 從未啓動
uuid: 286fcee-65a9-4cb9-b2055-9ce5 d024675 c
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 傳送
content-type: reference
topic-tags: sheduling-messages
discoiquuid: 9c7fd670-bba9-4f3 c-8cb1-87397a1 acd27
context-tags: 傳送，排程，返回
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: cb6396228e42f99f7e184a82e6c894b09a164cd9

---


# About scheduling messages{#about-scheduling-messages}

>[!CAUTION]
>
>Whenever making changes to a delivery’s schedule, you must re-prepare the delivery by clicking on the **Prepare** button before clicking **Confirm**.

In the message dashboard, the **[!UICONTROL Schedule]** block allows you to define when messages (email, SMS or Push notifications) will be sent.

![](assets/delivery_dashboard.png)

**[!UICONTROL Schedule]** 這些屬性可讓您設定電子郵件、SMS或推播通知的傳送選項：

* **[!UICONTROL Messages to be sent once confirmed]**：訊息會在確認傳送時立即傳送。See [Confirming the send](../../sending/using/confirming-the-send.md).

   ![](assets/delivery_planning_1.png)

* **[!UICONTROL Messages to be sent automatically on the date specified below]**：訊息將於稍後傳送。Specify the **contact date** in the **Start sending from** field.

   您可以準備並確認傳送，但只會傳送所選日期和時間的訊息。Preparing and confirming the send are presented in the [Preparing the send](../../sending/using/preparing-the-send.md) and [Confirming the send](../../sending/using/confirming-the-send.md) sections.

   **[!UICONTROL Time zone of the contact date]** 下拉式清單可讓您修改要考慮傳送時間的時區。For example, if you enter 9:00 AM in the **[!UICONTROL Start sending from]** field and if you select Brussels, Copenhagen, Madrid, Paris (GMT+1) in the **[!UICONTROL Time zone of the contact date]** drop-down list, all recipients will receive the message at 9:00 AM Paris time. 因此，位於莫斯科(GMT+3)的收件者將於莫斯科時間上午11：00收到訊息。

   If you would like to manually confirm the send, check the **[!UICONTROL Request confirmation before sending messages]** option. 預設會啓用此選項。

   ![](assets/delivery_planning.png)

>[!CAUTION]
>
>複製傳送時，會刪除所有排程設定。除非您排程新的聯絡日期，否則傳送確認後將會傳送重復傳送。

**相關主題**：

* [最佳化傳送時間](../../sending/using/optimizing-the-sending-time.md)
* [在收件者的時區傳送訊息](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)
* [計算傳送日期](../../sending/using/computing-the-sending-date.md)

