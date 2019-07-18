---
title: 個人檔案交易訊息
seo-title: 個人檔案交易訊息
description: 個人檔案交易訊息
seo-description: 瞭解如何建立和發佈個人檔案交易訊息。
page-status-flag: 從未啓動
uuid: a8efe979-74ae-46ff-a305-b86 a90679581
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 頻道
content-type: reference
topic-tags: 交易訊息
discoiquuid: dcb90afc-42c3-419e-8345-79cddf969e41
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 855db33971afdf9f02bf1b00be67c9e3f50bee06

---


# Profile transactional messages{#profile-transactional-messages}

您可以根據客戶行銷設定檔傳送交易訊息，您可以：

* Apply marketing typology rules such as **[!UICONTROL Blacklisted address]** or [fatigue rules](../../administration/using/fatigue-rules.md).
* 在訊息中加入取消訂閱連結。
* 將交易訊息新增至全域傳送報告。
* 運用客戶歷程中的交易訊息。

Once you have created and published an event (the cart abandonment as per the [example](../../channels/using/about-transactional-messaging.md#transactional-messaging-operating-principle) above), the corresponding transactional message is created automatically.

[設定事件中會顯示設定步驟，以傳送描述檔交易訊息](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message) 區段。

為了讓事件觸發傳送交易訊息，您必須個人化訊息，然後加以測試並加以發佈。

>[!NOTE]
>
>To access the transactional messages, you must have administration rights or appear in the **[!UICONTROL Message Center agents]** (mcExec) security group. 疲勞規則與描述檔交易訊息相容。See [Fatigue rules](../../administration/using/fatigue-rules.md).

## Sending a profile transactional message {#sending-a-profile-transactional-message}

建立、個人化和發佈描述檔交易訊息的步驟與事件交易訊息相同。See [Event transactional messages](../../channels/using/event-transactional-messages.md).

差異如下。

1. 前往建立用來編輯的交易訊息。
1. In the transactional message, click the **[!UICONTROL Content]** section. In addition to the transactional template, you can also choose the default email template, which targets **[!UICONTROL Profile]**.

   ![](assets/message-center_marketing_templates.png)

1. 選取預設電子郵件範本。

   類似於所有行銷電子郵件，它包含取消訂閱連結。

   ![](assets/message-center_marketing_perso_unsubscription.png)

   此外，您也可以直接存取所有描述檔資訊，以個人化您的訊息，而不是基於即時事件。See [Inserting a personalization field](../../designing/using/inserting-a-personalization-field.md).

1. 儲存變更並發佈訊息。See [Publishing a transactional message](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message).

## Monitoring a profile transactional message delivery {#monitoring-a-profile-transactional-message-delivery}

訊息發佈後，您的網站整合便會完成，您可以監控傳送。

1. To view the message delivery log, click the icon at the bottom right of the **[!UICONTROL Deployment]** block.

   For more information on accessing the logs, see [Monitoring the delivery](../../sending/using/monitoring-a-delivery.md).

1. Select the **[!UICONTROL Sending logs]** tab. **[!UICONTROL Status]** 在欄中 **[!UICONTROL Sent]** ，表示描述檔已選擇加入。

   ![](assets/message-center_marketing_sending_logs.png)

1. Select the **[!UICONTROL Exclusions logs]** tab to view recipients who have been excluded from the message target, such as blacklisted addresses.

   ![](assets/message-center_marketing_exclusion_logs.png)

For any profile that has opted out, the **[!UICONTROL Blacklisted address]** typology rule excluded the corresponding recipient.

This rule is part of a specific typology that applies to all transactional messages based on the **[!UICONTROL Profile]** table.

![](assets/message-center_marketing_typology.png)

**相關主題**：

* [網站整合](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)
* [Typologies](../../administration/using/about-typology-rules.md)

