---
title: 異動推送通知
description: 瞭解如何使用Adobe Campaign Standard傳送異動推播通知。
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
feature: Transactional Messaging
role: User
level: Intermediate
exl-id: 61988c1d-d538-47b1-94c1-f3fbdf314b65
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '1451'
ht-degree: 3%

---

# 異動推送通知{#transactional-push-notifications}

您可以使用Adobe Campaign在iOS和Android行動裝置上傳送異動推播通知。 這些訊息會在您透過Experience Cloud Mobile SDK在Adobe Campaign中設定的行動應用程式上接收。

>[!NOTE]
>
>推播通道為選用。 請檢查您的授權合約。如需標準推播通知的詳細資訊，請參閱 [關於推播通知](../../channels/using/about-push-notifications.md).

為了能夠傳送異動推播通知，您需要據此設定Adobe Campaign。 另請參閱 [設定行動應用程式](../../administration/using/configuring-a-mobile-application.md).

您可以傳送兩種型別的交易式推播通知：

* [以事件為目標的異動推播通知](#transactional-push-notifications-targeting-an-event)
* [以設定檔為目標的異動推播通知](#transactional-push-notifications-targeting-a-profile) 從Adobe Campaign資料庫

## 以事件為目標的異動推播通知 {#transactional-push-notifications-targeting-an-event}

您可以使用Adobe Campaign來傳送 **匿名交易式推播通知給所有使用者** 選擇接收行動應用程式通知的使用者。

在此案例中， **事件本身包含的資料可用來定義傳遞目標**. 不會利用來自Adobe Campaign整合式設定檔資料庫的資料。

### 設定事件型異動推播通知 {#configuring-event-based-transactional-push-notification}

若要將交易式推播通知傳送給選擇接收來自行動應用程式通知的所有使用者，您首先需要建立和設定以事件本身所含資料為目標的事件。

>[!NOTE]
>
>您仍然可以使用個人化事件型交易式推播通知的內容 [事件屬性](../../channels/using/configuring-transactional-event.md#defining-the-event-attributes) （來自事件的資料）和 [事件擴充](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content) （Campaign資料庫中的資料）。 另請參閱 [以下範例](#sending-event-based-transactional-push-notification).

事件必須包含下列三個元素：

* A **註冊權杖**，此為單一行動應用程式和單一裝置的使用者ID。 它可能不會對應至Adobe Campaign資料庫中的任何設定檔。
* A **行動應用程式名稱** (適用於所有裝置 — Android和iOS)。 這是在Adobe Campaign中設定的行動應用程式ID，用來接收使用者裝置上的推播通知。 有關詳細資訊，請參閱 [設定行動應用程式](../../administration/using/configuring-a-mobile-application.md).
* A **推播平台** (「gcm」適用於Android，「apns」適用於iOS)。

若要設定事件，請遵循下列步驟：

1. 建立事件設定時，選取 **[!UICONTROL Push notification]** 頻道和 **[!UICONTROL Real-time event]** 目標維度(請參閱 [建立事件](../../channels/using/configuring-transactional-event.md#creating-an-event))。
1. 新增欄位至事件。 這可讓您個人化交易式訊息(請參閱 [定義事件屬性](../../channels/using/configuring-transactional-event.md#defining-the-event-attributes))。 在此範例中，定義「gateNumber」、「lastname」和「firstname」欄位。
1. 您也可以擴充訊息的內容。 若要這麼做，請從您連結至事件設定的表格新增欄位(請參閱 [豐富化事件](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content))。

   <!--Event-based transactional messaging is supposed to use only the data that are in the sent event to define the recipient and the message content personalization. However, you can enrich the content of your transactional message using information from the Adobe Campaign database.-->

1. [預覽和發佈事件](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event).

   預覽事件時，REST API包含將用於鎖定傳送目標的「registrationToken」、「application」和「pushPlatform」屬性。

   ![](assets/message-center_push_api.png)

   發佈事件後，就會自動建立連結至新事件的交易式推播通知。 您現在可以修改並發佈剛建立的訊息(請參閱 [本節](#sending-event-based-transactional-push-notification))。

1. 將事件整合至您的網站(請參閱 [整合事件觸發](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger))。

### 傳送事件型異動推播通知 {#sending-event-based-transactional-push-notification}

例如，一家航空公司想要邀請其行動應用程式使用者前往相關登機口。

公司將使用單一行動應用程式，透過單一裝置為每位使用者傳送一個交易式推播通知（以註冊權杖識別）。

1. 移至建立的交易式訊息以對其進行編輯。 另請參閱 [存取交易式訊息](../../channels/using/editing-transactional-message.md#accessing-transactional-messages).

   ![](assets/message-center_push_message.png)

1. 按一下 **[!UICONTROL Content]** 區塊以修改訊息的標題和內文。

1. 您可以插入個人化欄位，以新增建立事件時定義的元素(請參閱 [定義事件屬性](../../channels/using/configuring-transactional-event.md#defining-the-event-attributes))。

   ![](assets/message-center_push_content.png)

   若要尋找這些欄位，請按一下專案旁的鉛筆，然後按一下 **[!UICONTROL Insert personalization field]** 並選取 **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]**.

   ![](assets/message-center_push_personalization.png)

   如需編輯推播通知內容的詳細資訊，請參閱 [準備和傳送推播通知](../../channels/using/preparing-and-sending-a-push-notification.md).

1. 如果您想使用Adobe Campaign資料庫的其他資訊，也可以擴充交易式訊息內容(請參閱 [豐富化事件](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content))。

1. 儲存您的變更並發佈訊息。請參閱[發佈交易式訊息](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message)。

1. 使用Adobe Campaign Standard REST API，使用單一行動應用程式(WeFlight)，將事件傳送至包含登機資料的Android (gcm)上的註冊權杖(ABCDEF123456789)：

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

   如需將事件觸發整合至外部系統的詳細資訊，請參閱 [整合事件觸發](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger).

如果註冊權杖存在，則對應的使用者會收到包含以下內容的交易式推播通知：

*「Jane Green，您好，剛剛開始登機！ 請前往B18門。」*

## 以設定檔為目標的異動推播通知 {#transactional-push-notifications-targeting-a-profile}

您可以傳送異動推播通知 **訂閱您行動應用程式的Adobe Campaign設定檔**. 此傳遞可包含 [個人化欄位](../../designing/using/personalization.md#inserting-a-personalization-field)，例如收件者的名字，會直接從Adobe Campaign資料庫擷取。

在這種情況下，事件必須包含一些欄位 **允許與Adobe Campaign資料庫中的設定檔進行調解**.

目標定位設定檔時，會針對每個行動應用程式和裝置傳送一個交易式推播通知。 例如，如果一個Adobe Campaign使用者訂閱了兩個應用程式，則此使用者將收到兩個通知。 如果使用者使用兩個不同的裝置訂閱了相同的應用程式，則此使用者將在每個裝置上收到通知。

設定檔已訂閱的行動應用程式會列在 **[!UICONTROL Mobile App Subscriptions]** 此設定檔的索引標籤。 若要存取此索引標籤，請選取設定檔並按一下 **[!UICONTROL Edit profile properties]** 按鈕。

![](assets/push_notif_subscriptions.png)

如需存取和編輯設定檔的詳細資訊，請參閱 [關於設定檔](../../audiences/using/about-profiles.md).

### 設定設定檔交易式推播通知 {#configuring-profile-based-transactional-push-notification}

若要將交易式推播通知傳送給已訂閱行動應用程式的Adobe Campaign設定檔，您首先需要建立和設定以Adobe Campaign資料庫為目標的事件。

1. 建立事件設定時，選取 **[!UICONTROL Push notification]** 頻道和 **[!UICONTROL Profile]** 目標維度(請參閱 [建立事件](../../channels/using/configuring-transactional-event.md#creating-an-event))。

   依預設，交易式推播通知會傳送給收件者訂閱的所有行動應用程式。 若要將推播通知傳送至特定的行動應用程式，請在清單中選取該應用程式。 訊息會鎖定其他行動應用程式，但會將其從傳送中排除。

   ![](assets/message-center_push_appfilter.png)

1. 如果您想要個人化交易式訊息(請參閱 [定義事件屬性](../../channels/using/configuring-transactional-event.md#defining-the-event-attributes))。

   >[!NOTE]
   >
   >您必須至少新增一個欄位才能建立擴充。 您不需要建立其他欄位，例如 **名字** 和 **姓氏** 因為您將能夠使用Adobe Campaign資料庫中的個人化欄位。

1. 建立擴充以將事件連結至 **[!UICONTROL Profile]** 資源(請參閱 [豐富化事件](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content))並選取此擴充作為 **[!UICONTROL Targeting enrichment]**.

   >[!IMPORTANT]
   >
   >設定檔事件必須有此步驟。

1. [預覽和發佈事件](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event).

   預覽事件時，REST API不包含指定註冊權杖、應用程式名稱和推送平台的屬性，因為它們將會從擷取 **[!UICONTROL Profile]** 資源。

   發佈事件後，就會自動建立連結至新事件的交易式推播通知。 您現在可以修改並發佈剛建立的訊息(請參閱 [本節](#sending-profile-based-transactional-push-notification))。

1. 將事件整合至您的網站(請參閱 [整合事件觸發](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger))。

### 傳送設定檔交易式推播通知 {#sending-profile-based-transactional-push-notification}

例如，一家航空公司想要傳送最後一個入門呼叫給所有已訂閱其行動應用程式的Adobe Campaign使用者。

1. 移至建立的交易式訊息以對其進行編輯。 另請參閱 [存取交易式訊息](../../channels/using/editing-transactional-message.md#accessing-transactional-messages).

1. 按一下 **[!UICONTROL Content]** 區塊以修改訊息的標題和內文。

   與以即時事件為基礎的設定相反，您可以直接存取所有設定檔資訊，以個人化您的訊息。 請參閱[插入個人化欄位](../../designing/using/personalization.md#inserting-a-personalization-field)。

   如需編輯推播通知內容的詳細資訊，請參閱 [準備和傳送推播通知](../../channels/using/preparing-and-sending-a-push-notification.md).

1. 儲存您的變更並發佈訊息。請參閱[發佈交易式訊息](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message)。
1. 使用Adobe Campaign Standard REST API，傳送事件至設定檔：

   ```
   {
     "ctx":
     {
       "email":"janegreen@email.com",
       "gateNumber":"D16",
     }
   }
   ```

如需將事件觸發整合至外部系統的詳細資訊，請參閱 [整合事件觸發](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger).

對應的使用者會收到交易式推播通知，其中包含從Adobe Campaign資料庫擷取的所有個人化元素。

>[!NOTE]
>
>沒有註冊權杖、應用程式和推播平台欄位。 在此範例中，調解是使用email欄位執行。

## 變更異動推播通知中的目標對應 {#change-target-mapping}

異動推播通知使用特定 [目標對應](../../administration/using/target-mappings-in-campaign.md) 其中包含傳送此類傳送所需的技術設定。

若要變更此目標對應，請遵循下列步驟：

1. 從交易式訊息清單中，選取推播通知。

1. 在訊息控制面板中，按一下 **[!UICONTROL Edit properties]** 按鈕。

   ![](assets/message-center_push_edit.png)

1. 展開 **[!UICONTROL Advanced parameters]** 區段。

1. 按一下&#x200B;**[!UICONTROL Select a 'Target mapping' element]**。

   ![](assets/message-center_push_target-mapping.png)

1. 從清單中選取目標對應。

   >[!NOTE]
   >
   >為了提供傳送時的最佳傳送準備時間和效能 **以設定檔為基礎** 異動推播通知，使用 **[!UICONTROL Profile - Real-time event for Push (mapRtEventAppSubRcp)]** 目標對應。

   ![](assets/message-center_push_target-mapping_change.png)

1. 確認變更並發佈訊息。 請參閱[發佈交易式訊息](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message)。

   >[!IMPORTANT]
   >
   >您必須再次發佈訊息，變更才會生效，否則仍會使用先前的目標對應。


