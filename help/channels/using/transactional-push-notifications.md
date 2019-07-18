---
title: 交易推播通知
seo-title: 交易推播通知
description: 交易推播通知
seo-description: 瞭解如何建立和發佈交易推播通知。
page-status-flag: 從未啓動
uuid: ef31c1b6-9ef8-42e3-b49 d-72f9 eac8 ea32
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 頻道
content-type: reference
topic-tags: 交易訊息
discoiquuid: e645d4b9-001f-47d9-8a0f-b4696 c75 c5 d
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 855db33971afdf9f02bf1b00be67c9e3f50bee06

---


# Transactional push notifications{#transactional-push-notifications}

您可以使用Adobe Campaign在iOS和Android行動裝置上傳送交易推播通知。這些訊息會透過運用Experience Cloud Mobile SDK在Adobe Campaign中設定的行動應用程式收到。

>[!NOTE]
>
>推播管道是選擇性的。請檢查您的授權合約。For more information on standard push notifications, see [Push notifications](../../channels/using/about-push-notifications.md).

您可以傳送兩種交易推播通知：

* 針對事件的交易推播通知。
* 來自Adobe Campaign資料庫的交易推播通知定位設定檔。

Once you have created and published an event (the cart abandonment explained in [this section](../../channels/using/about-transactional-messaging.md#transactional-messaging-operating-principle)), the corresponding transactional push notification is created automatically.

The configuration steps are presented in the [Configuring an event to send a transactional push notification](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message) section.

為了讓事件觸發傳送交易訊息，您必須個人化訊息，然後加以測試並加以發佈。

>[!NOTE]
>
>To access the transactional messages, you must have administration rights or appear in the **[!UICONTROL Message Center agents]** (mcExec) security group.

## Transactional push notifications targeting an event {#transactional-push-notifications-targeting-an-event}

您可以傳送匿名交易推播通知給選擇接收行動應用程式通知的所有使用者。

在此情況下，只會使用事件本身中包含的資料來定義傳送目標。Adobe Campaign整合式個人檔案資料庫中沒有任何資料可運用。

### Sending a transactional push notification targeting an event {#sending-a-transactional-push-notification-targeting-an-----------event}

例如，航空公司希望邀請其行動應用程式使用者前往相關的閘道進行登機。

公司會透過單一裝置，將一個交易推播通知(以註冊代號識別)傳送給每位使用者(使用註冊代號識別)。

1. 前往建立用來編輯的交易訊息。See [Event transactional messages](../../channels/using/event-transactional-messages.md).

   ![](assets/message-center_push_message.png)

1. Click the **[!UICONTROL Content]** block to modify your message's title and body.

   您可以插入個人化欄位，新增您在建立事件時定義的元素。

   ![](assets/message-center_push_content.png)

   To find these fields, click the pencil next to an item, click **[!UICONTROL Insert personalization field]** and select **[!UICONTROL Transactional event]** &gt; **[!UICONTROL Event context]**.

   ![](assets/message-center_push_personalization.png)

   For more on editing a push notification content, see [Creating a push notification](../../channels/using/preparing-and-sending-a-push-notification.md).

1. 儲存變更並發佈訊息。See [Publishing a transactional message](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message).
1. 使用Adobe Campaign Standard REST API，將事件傳送至註冊Token(ABCDEF12345689)，使用一個在Android(gcm)上的行動應用程式(whight)，包含內嵌資料。

   ```
   {
     "registrationToken":"ABCDEF123456789",
     "application":"WeFlight",
     "pushPlatform":"gcm",
     "ctx":
     {
       "gateNumber":"Gate B18",
       "lastname":"Green",
       "firstname":"Jane"
     }
   }
   ```

   For more on integrating the triggering of an event into an external system, see [Site integration](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website).

如果註冊Token存在，對應的使用者會收到交易式推播通知，其中包含下列內容：

「Hello Jane Green，登機剛開始！請前往Gate B18」。

## Transactional push notifications targeting a profile {#transactional-push-notifications-targeting-a-profile}

您可以傳送交易推播通知給已訂閱您行動應用程式的Adobe Campaign設定檔。This delivery can contain [personalization](../../designing/using/inserting-a-personalization-field.md) fields, such as the recipient's first name.

在此情況下，事件必須包含允許與Adobe Campaign資料庫中的描述檔協調的欄位。

定位設定檔時，每個行動應用程式和每個裝置會傳送單次交易推播通知。例如，如果Adobe Campaign使用者已訂閱兩個應用程式，此使用者將會收到兩個通知。如果使用者已訂閱兩個不同裝置的相同應用程式，則此使用者將會收到每個裝置上的通知。

The mobile applications a profile has subscribed to are listed in the **[!UICONTROL Mobile App Subscriptions]** tab of this profile. To access this tab, select a profile and click the **[!UICONTROL Edit profile properties]** button on the right.

![](assets/push_notif_subscriptions.png)

For more information on accessing and editing profiles, see [Profiles](../../audiences/using/creating-profiles.md).

### Sending a transactional push notification targeting a profile {#sending-a-transactional-push-notification-targeting-a-----------profile}

例如，某家航空公司想要傳送最後一通電話給已訂閱其行動應用程式的所有Adobe Campaign使用者。

1. 前往建立用來編輯的交易訊息。See [Event transactional messages](../../channels/using/event-transactional-messages.md).

   ![](assets/message-center_push_message_profile.png)

1. Click the **[!UICONTROL Content]** block to modify your message's title and body.

   相對於根據即時事件的設定，您可以直接存取所有描述檔資訊，以個人化您的訊息。See [Inserting a personalization field](../../designing/using/inserting-a-personalization-field.md).

   ![](assets/message-center_push_content_profile.png)

   如需更多有關編輯推播通知內容的資訊。See [Creating a push notification](../../channels/using/preparing-and-sending-a-push-notification.md).

1. 儲存變更並發佈訊息。See [Publishing a transactional message](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message).
1. 使用Adobe Campaign Standard REST API，將事件傳送至描述檔。

   ```
   {
     "ctx":
     {
       "email":"janegreen@email.com",
       "gateNumber":"D16",
     }
   }
   ```

   For more on integrating the triggering of an event into an external system, see [Site integration](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website).

   >[!NOTE]
   >
   >沒有註冊Token、應用程式和推播平台欄位。在此範例中，協調是以電子郵件欄位執行。

