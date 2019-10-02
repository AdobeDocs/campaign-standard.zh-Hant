---
title: 交易式推播通知
seo-title: 交易式推播通知
description: 交易式推播通知
seo-description: 瞭解如何建立和發佈交易式推播通知。
page-status-flag: 從未激活
uuid: ef31c1b6-9ef8-42e3-b49d-72f9ea8ea32
contentOwner: 紹維亞
products: SG_CAMPAIGN/STANDARD
audience: 頻道
content-type: 參考
topic-tags: transactional-messaging
discoiquuid: e645d4b9-001f-47d9-8a0f-b4696c75c5d3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d9357481a567cb0d11eea43211abf08a6dcb07d6

---


# 交易式推播通知{#transactional-push-notifications}

您可以使用Adobe Campaign在iOS和Android行動裝置上傳送交易推播通知。 這些訊息是在您在Adobe Campaign中設定的行動應用程式上，透過運用Experience Cloud Mobile SDK收到的。

>[!NOTE]
>
>推播頻道為選擇性。 請檢查您的授權合約。 如需標準推播通知的詳細資訊，請參閱 [推播通知](../../channels/using/about-push-notifications.md)。

您可以傳送兩種類型的交易推播通知：

* 以事件為目標的交易式推播通知。
* 以Adobe Campaign資料庫的設定檔為目標的交易式推播通知。

在您建立並發佈事件後(本節說明的購物車放棄 [率](../../channels/using/about-transactional-messaging.md#transactional-messaging-operating-principle))，就會自動建立對應的交易推播通知。

設定步驟會顯示在「設 [定事件以傳送交易推播通知](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message) 」區段。

為了讓事件觸發傳送交易訊息，您必須個人化訊息，然後測試並發佈訊息。

>[!NOTE]
>
>要訪問事務性消息，您必須具有管理權限或顯示在( **[!UICONTROL Message Center agents]** mcExec)安全組中。

## 針對事件的交易式推播通知 {#transactional-push-notifications-targeting-an-event}

您可以傳送匿名交易式推播通知給所有選擇接收行動應用程式通知的使用者。

在此情況下，僅使用事件本身包含的資料來定義傳送目標。 Adobe Campaign整合的設定檔資料庫中沒有任何資料可供使用。

### Sending a transactional push notification targeting an event {#sending-a-transactional-push-notification-targeting-an-----------event}

For example, an airline company wants to invite its mobile application users to proceed to the relevant gate for boarding.

The company will send one transactional push notification per user (identified with a registration token), using one mobile application, through one single device.

1. Go the transactional message that was created to edit it. See Event transactional messages.[](../../channels/using/event-transactional-messages.md)

   ![](assets/message-center_push_message.png)

1. Click the  block to modify your message's title and body.**[!UICONTROL Content]**

   You can insert personalization fields to add elements that you defined when you created your event.

   ![](assets/message-center_push_content.png)

   To find these fields, click the pencil next to an item, click **[!UICONTROL Insert personalization field]** and select **[!UICONTROL Context]** &gt; **[!UICONTROL Real-time event]** &gt; **[!UICONTROL Event context]**.

   ![](assets/message-center_push_personalization.png)

   For more on editing a push notification content, see [Creating a push notification](../../channels/using/preparing-and-sending-a-push-notification.md).

1. Save your changes and publish the message. See Publishing a transactional message.[](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message)
1. Using the Adobe Campaign Standard REST API, send an event to a registration token (ABCDEF123456789), using one mobile application (WeFlight), on Android (gcm), containing the boarding data.

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

   如需將事件觸發整合至外部系統的詳細資訊，請參閱網 [站整合](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)。

If the registration token exists, the corresponding user receives a transactional push notification including the following content:

"Hello Jane Green, boarding has just started! 請前往B18門。」

## 針對描述檔的交易推播通知 {#transactional-push-notifications-targeting-a-profile}

您可以傳送交易式推播通知給已訂閱您行動應用程式的Adobe Campaign設定檔。 此傳送可包含 [個人化](../../designing/using/personalization.md#inserting-a-personalization-field) 欄位，例如收件者的名字。

在這種情況下，事件必須包含一些欄位，允許與Adobe Campaign資料庫的描述檔進行協調。

定位設定檔時，會依行動應用程式和裝置傳送一個交易式推播通知。 例如，如果Adobe Campaign使用者訂閱了兩個應用程式，此使用者會收到兩個通知。 If a user has subscribed to the same application with two different devices, this user will receive a notification on each device.

描述檔已訂閱的行動應用程式會列在此描述檔 **[!UICONTROL Mobile App Subscriptions]** 的標籤中。 要訪問此頁籤，請選擇一個配置檔案，然後按一下 **[!UICONTROL Edit profile properties]** 右側的按鈕。

![](assets/push_notif_subscriptions.png)

有關訪問和編輯配置檔案的詳細資訊，請參 [閱Profiles](../../audiences/using/creating-profiles.md)。

### 傳送針對描述檔的交易推播通知 {#sending-a-transactional-push-notification-targeting-a-----------profile}

例如，航空公司想要向所有已訂閱其行動應用程式的Adobe Campaign使用者寄送最後一次登入通知。

1. 轉至為編輯而建立的交易訊息。 請參 [閱事件交易訊息](../../channels/using/event-transactional-messages.md)。

   <!--![](assets/message-center_push_message_profile.png)-->

1. 按一下 **[!UICONTROL Content]** 區塊以修改訊息的標題和內文。

   與基於即時事件的配置不同，您可以直接訪問所有配置檔案資訊以個性化您的消息。 請參 [閱插入個人化欄位](../../designing/using/personalization.md#inserting-a-personalization-field)。

   <!--![](assets/message-center_push_content_profile.png)-->

   如需編輯推播通知內容的詳細資訊。 請參 [閱建立推播通知](../../channels/using/preparing-and-sending-a-push-notification.md)。

1. 儲存變更並發佈訊息。 請參 [閱發佈交易訊息](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message)。
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

   如需將事件觸發整合至外部系統的詳細資訊，請參閱網 [站整合](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)。

   >[!NOTE]
   >
   >沒有註冊Token、應用程式和推播平台欄位。 在此示例中，協調是使用電子郵件欄位執行的。

