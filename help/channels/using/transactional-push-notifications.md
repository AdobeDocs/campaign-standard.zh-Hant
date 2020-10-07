---
title: 交易式推播通知
description: 瞭解如何建立和發佈交易式推播通知。
page-status-flag: never-activated
uuid: ef31c1b6-9ef8-42e3-b49d-72f9eac8ea32
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: transactional-messaging
discoiquuid: e645d4b9-001f-47d9-8a0f-b4696c75c5d3
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '740'
ht-degree: 13%

---


# 交易式推播通知{#transactional-push-notifications}

您可以使用Adobe Campaign在iOS和Android行動裝置上傳送交易推播通知。 這些訊息是在您在Adobe Campaign中設定的行動應用程式上，透過運用Experience Cloud Mobile SDK收到的。

>[!NOTE]
>
>推播頻道為選擇性。 請檢查您的授權合約。如需標準推播通知的詳細資訊，請參閱 [推播通知](../../channels/using/about-push-notifications.md)。

您可以傳送兩種類型的交易推播通知：

* 以事件為目標的交易式推播通知。
* 以Adobe Campaign資料庫的設定檔為目標的交易式推播通知。

Once you have created and published an event (the cart abandonment explained in [this section](../../channels/using/getting-started-with-transactional-msg.md#transactional-messaging-operating-principle)), the corresponding transactional push notification is created automatically.

The configuration steps are presented in the [Configuring an event to send a transactional push notification](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message) section.

為了讓事件觸發傳送交易式訊息，您必須個人化訊息，然後再測試之後發佈訊息。

>[!NOTE]
>
>您必須是 **[!UICONTROL Administrators (all units)]** 安全群組的成員，才能存取交易式訊息。

## 針對事件的交易式推播通知 {#transactional-push-notifications-targeting-an-event}

您可以傳送匿名交易式推播通知給所有選擇接收行動應用程式通知的使用者。

在此情況下，僅使用事件本身包含的資料來定義傳送目標。 Adobe Campaign整合的設定檔資料庫中沒有任何資料可供使用。

### 傳送針對事件的交易推播通知 {#sending-a-transactional-push-notification-targeting-an-----------event}

例如，航空公司希望邀請其行動應用程式使用者前往相關登機口登機。

該公司將使用一個行動應用程式，透過單一裝置，針對每位使用者傳送一則交易式推播通知（以註冊Token識別）。

1. 移至建立的交易式訊息，以編輯其內容。請參閱[事件交易式訊息](../../channels/using/event-transactional-messages.md)。

   ![](assets/message-center_push_message.png)

1. Click the **[!UICONTROL Content]** block to modify your message&#39;s title and body.

   您可以插入個人化欄位，以新增您在建立事件時定義的元素。

   ![](assets/message-center_push_content.png)

   若要尋找這些欄位，請按一下項目旁的鉛筆，然後按一 **[!UICONTROL Insert personalization field]** 下並選 **[!UICONTROL Context]** 取> **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]**。

   ![](assets/message-center_push_personalization.png)

   如需編輯推播通知內容的詳細資訊，請參 [閱建立推播通知](../../channels/using/preparing-and-sending-a-push-notification.md)。

1. 儲存您的變更並發佈訊息。請參閱[發佈交易式訊息](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message)。

1. 使用Adobe Campaign Standard REST API，在Android(gcm)上使用一個行動應用程式(WeFlight)，將事件傳送至註冊Token(ABCDEF123456789)，其中包含登入資料。

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

如果註冊令牌存在，則相應用戶接收包括以下內容的交易推播通知：

「您好，簡·格林，登機手續剛剛開始！ 請前往B18門。」

## 針對描述檔的交易推播通知 {#transactional-push-notifications-targeting-a-profile}

您可以傳送交易式推播通知給已訂閱您行動應用程式的Adobe Campaign設定檔。 此傳送可包含 [個人化](../../designing/using/personalization.md#inserting-a-personalization-field) 欄位，例如收件者的名字。

在這種情況下，事件必須包含一些欄位，允許與Adobe Campaign資料庫的描述檔進行協調。

定位設定檔時，會依行動應用程式和裝置傳送一個交易式推播通知。 例如，如果Adobe Campaign使用者訂閱了兩個應用程式，此使用者會收到兩個通知。 如果使用者已訂閱使用兩種不同裝置的相同應用程式，此使用者會在每種裝置上收到通知。

描述檔已訂閱的行動應用程式會列在此描述檔 **[!UICONTROL Mobile App Subscriptions]** 的標籤中。 要訪問此頁籤，請選擇一個配置檔案，然後按一下 **[!UICONTROL Edit profile properties]** 右側的按鈕。

![](assets/push_notif_subscriptions.png)

有關訪問和編輯配置檔案的詳細資訊，請參 [閱Profiles](../../audiences/using/creating-profiles.md)。

### 傳送針對描述檔的交易推播通知 {#sending-a-transactional-push-notification-targeting-a-----------profile}

例如，航空公司想要向所有已訂閱其行動應用程式的Adobe Campaign使用者寄送最後一次登入通知。

1. 移至建立的交易式訊息，以編輯其內容。請參閱[事件交易式訊息](../../channels/using/event-transactional-messages.md)。

1. Click the **[!UICONTROL Content]** block to modify your message&#39;s title and body.

   與基於即時事件的配置不同，您可以直接訪問所有配置檔案資訊以個性化您的消息。 請參閱[插入個人化欄位](../../designing/using/personalization.md#inserting-a-personalization-field)。

   如需編輯推播通知內容的詳細資訊。 請參 [閱建立推播通知](../../channels/using/preparing-and-sending-a-push-notification.md)。

1. 儲存您的變更並發佈訊息。請參閱[發佈交易式訊息](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message)。
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
