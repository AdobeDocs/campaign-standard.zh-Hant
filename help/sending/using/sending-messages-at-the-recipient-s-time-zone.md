---
title: 在收件者的時區傳送訊息
description: 瞭解如何在收件者的時區傳送訊息。
page-status-flag: 從未激活
uuid: 70228c07-451f-4ddb-8d26-92a5a4814e3a
contentOwner: 紹維亞
products: SG_CAMPAIGN/STANDARD
audience: 發送
content-type: 參考
topic-tags: 調度消息
discoiquuid: daa980ba-8c7c-4673-a68f-379d63e4b8bd
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 在收件者的時區傳送訊息{#sending-messages-at-the-recipient-s-time-zone}

在管理日期和時間很重要的促銷活動時，您可以排程將每位收件者的當地時間納入考量的傳送：他們會在您排程時，在自己的時區收到電子郵件、簡訊或推播通知。

>[!NOTE]
>
>若要使用此功能，請確定您傳送的目標設定檔在其屬性的區段中指定 **[!UICONTROL Address]** 了時區。 有關訪問配置檔案屬性的詳細資訊，請參閱本 [節](../../audiences/using/editing-profiles.md)。

若要在收件者的時區傳送傳送，您也可以在工作流程中 **[!UICONTROL Scheduler]** 使用活動。 For more on this, refer to this [page](../../automating/using/scheduler.md).

在下列範例中，我們想傳送促銷代碼，該代碼僅在情人節當天有效，給全球所有客戶。 為了在白天提供足夠的時間使用，所有客戶必須在2月14日上午8:00（視其時區而定）收到您的訊息。

1. 在標籤 **[!UICONTROL Marketing activities]** 中，開始建立您的傳送內容（以我們的例子來說）。 若要進一步瞭解建立傳送內容，請參閱本 [節](../../channels/using/creating-an-email.md)。
1. 在設計您的情人節電子郵件後，按一下 **[!UICONTROL Create]** 以存取傳送儀表板。 有關電子郵件設計的更多資訊，請參閱 [本頁](../../designing/using/personalization.md#example-email-personalization)。

   ![](assets/send-time_opt_valentine_1.png)

1. 從傳送控制面板中，選取 **[!UICONTROL Schedule]** 區塊。

   ![](assets/send-time_opt_valentine_2.png)

1. 選擇下面 **[!UICONTROL Messages to be sent automatically on the date]** 指定的選項。 然後在現 **[!UICONTROL Start sending from]** 場中，設定聯絡日期，在我們的案例中是2月14日上午8:00，如此每位收件者都會在情人節收到。

   ![](assets/send-time_opt_valentine.png)

1. 在欄位 **[!UICONTROL Time zone of the contact date]** 中，選取預設應傳送傳送的時區。

   如果設定檔 **[!UICONTROL Time zone]** 保留為 **[!UICONTROL Default]**，收件者會根據此處選擇的時區接收傳送。

1. 從下拉 **[!UICONTROL Optimize the sending time per recipient]** 式選單中選擇 **[!UICONTROL Send at the recipient's time zone]**。 這可讓收件者在2月14日收到情人節電子郵件，視其時區而定。

   ![](assets/send-time_opt_valentine_3.png)

1. 確認傳送排程後，按一下按鈕， **[!UICONTROL Prepare]** 然後 **[!UICONTROL Confirm]** 再傳送。

   請務必至少提前24小時確認傳送。 否則，某些收件者可能會在實際的情人節之前收到送禮，視其所在位置而定。

   ![](assets/send-time_opt_valentine_4.png)

無論收件者位於何處，都會在當地時間2月14日上午8點收到訊息。
