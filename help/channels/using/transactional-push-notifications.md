---
solution: Campaign Standard
product: campaign
title: 交易式推播通知
description: 瞭解如何使用Adobe Campaign Standard傳送交易推播通知。
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
translation-type: tm+mt
source-git-commit: f19d4b5c1837f3f03789958abb1539d4edea0744
workflow-type: tm+mt
source-wordcount: '1336'
ht-degree: 4%

---


# 交易式推播通知{#transactional-push-notifications}

您可以使用Adobe Campaign在iOS和Android行動裝置上傳送交易推播通知。 這些訊息是在您在Adobe Campaign中設定的行動應用程式上，透過運用Experience Cloud Mobile SDK收到的。

>[!NOTE]
>
>推播頻道為選擇性。 請檢查您的授權合約。如需標準推播通知的詳細資訊，請參閱[關於推播通知](../../channels/using/about-push-notifications.md)。

若要傳送交易推播通知，您必須據以設定Adobe Campaign。 請參閱[設定行動應用程式](../../administration/using/configuring-a-mobile-application.md)。

您可以傳送兩種類型的交易推播通知：

* [針對事件的交易式推播通知](#transactional-push-notifications-targeting-an-event)
* [以Adobe Campaign資料庫中的分](#transactional-push-notifications-targeting-a-profile) 析資料為目標的交易推播通知

## 針對事件{#transactional-push-notifications-targeting-an-event}的交易式推播通知

您可以使用Adobe Campaign將&#x200B;**匿名交易推播通知傳送給已選擇從行動應用程式接收通知的所有使用者。**

在這種情況下，僅使用事件本身包含的&#x200B;**資料來定義傳送目標**。 Adobe Campaign整合的設定檔資料庫中沒有任何資料可供使用。

### 設定事件型交易推播通知{#configuring-event-based-transactional-push-notification}

若要向所有選擇接收行動應用程式通知的使用者傳送交易式推播通知，您首先需要建立並設定事件，以事件本身所包含的資料為目標。

>[!NOTE]
>
>您仍可使用[事件屬性](../../channels/using/configuring-transactional-event.md#defining-the-event-attributes)（來自事件的資料）和[事件擴充](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content)（來自促銷活動資料庫的資料），個人化事件型交易推播通知的內容。 請參閱[下面的範例](#sending-event-based-transactional-push-notification)。

事件必須包含下列三個元素：

* **註冊Token**，此為一個行動應用程式與一個裝置的使用者ID。 它可能不對應Adobe Campaign資料庫中的任何描述檔。
* **行動應用程式名稱**（所有裝置皆有一個- Android和iOS）。 這是Adobe Campaign中設定的行動應用程式ID，將用來接收使用者裝置上的推播通知。 有關詳細資訊，請參閱[配置移動應用程式](../../administration/using/configuring-a-mobile-application.md)。
* **推送平台**（Android為「gcm」,iOS為「apns」）。

若要設定事件，請遵循下列步驟：

1. 建立事件配置時，選擇&#x200B;**[!UICONTROL Push notification]**&#x200B;通道和&#x200B;**[!UICONTROL Real-time event]**&#x200B;目標維（請參閱[建立事件](../../channels/using/configuring-transactional-event.md#creating-an-event)）。
1. 新增欄位至事件。 這將允許您個性化事務性消息（請參閱[定義事件屬性](../../channels/using/configuring-transactional-event.md#defining-the-event-attributes)）。 在此範例中，請定義「gateNumber」、「lastname」和「firstname」欄位。
1. 您也可以豐富訊息的內容。 若要這麼做，請從您連結至事件設定的表格新增欄位（請參閱[豐富事件](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content)）。

   <!--Event-based transactional messaging is supposed to use only the data that are in the sent event to define the recipient and the message content personalization. However, you can enrich the content of your transactional message using information from the Adobe Campaign database.-->

1. [預覽並發佈事件](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event)。

   在預覽事件時，REST API會包含「registrationToken」、「application」和「pushPlatform」屬性，這些屬性將用來定位傳送。

   ![](assets/message-center_push_api.png)

   發佈事件後，就會自動建立連結至新事件的交易推播通知。 您現在可以修改並發佈剛建立的訊息（請參閱[本節](#sending-event-based-transactional-push-notification)）。

1. 將事件整合至您的網站（請參閱[整合事件觸發](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger)）。

### 傳送事件型交易推播通知{#sending-event-based-transactional-push-notification}

例如，航空公司希望邀請其行動應用程式使用者前往相關登機口登機。

該公司將使用一個行動應用程式，透過單一裝置，針對每位使用者傳送一則交易式推播通知（以註冊Token識別）。

1. 移至建立的交易式訊息，以編輯其內容。請參閱[訪問事務性消息](../../channels/using/editing-transactional-message.md#accessing-transactional-messages)。

   ![](assets/message-center_push_message.png)

1. 按一下&#x200B;**[!UICONTROL Content]**&#x200B;塊以修改消息的標題和正文。

1. 您可以插入個人化欄位，以新增您在建立事件時定義的元素（請參閱[定義事件屬性](../../channels/using/configuring-transactional-event.md#defining-the-event-attributes)）。

   ![](assets/message-center_push_content.png)

   若要尋找這些欄位，請按一下項目旁的鉛筆，然後按一下&#x200B;**[!UICONTROL Insert personalization field]**&#x200B;並選取&#x200B;**[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]**。

   ![](assets/message-center_push_personalization.png)

   如需編輯推播通知內容的詳細資訊，請參閱[準備和傳送推播通知](../../channels/using/preparing-and-sending-a-push-notification.md)。

1. 如果您想要使用Adobe Campaign資料庫的其他資訊，您也可以豐富交易訊息內容（請參閱[豐富事件](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content)）。

1. 儲存您的變更並發佈訊息。請參閱[發佈交易式訊息](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message)。

1. 使用Adobe Campaign Standard REST API，使用Android(gcm)上的一個行動應用程式(WeFlight)，將事件傳送至註冊Token(ABCDEF123456789)，其中包含登入資料：

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

   有關將事件觸發整合到外部系統的詳細資訊，請參閱[整合事件觸發](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger)。

如果註冊令牌存在，則相應用戶接收包括以下內容的交易推播通知：

*「您好，簡·格林，登機手續剛剛開始！請前往B18門。&quot;*

## 針對描述檔{#transactional-push-notifications-targeting-a-profile}的交易推播通知

您可以傳送交易推播通知&#x200B;**給已訂閱您行動應用程式**&#x200B;的Adobe Campaign設定檔。 此傳送可包含[個人化欄位](../../designing/using/personalization.md#inserting-a-personalization-field)，例如直接從Adobe Campaign資料庫擷取的收件者名稱。

在這種情況下，事件必須包含一些欄位&#x200B;**，允許與Adobe Campaign資料庫**&#x200B;中的描述檔進行協調。

定位設定檔時，會依行動應用程式和裝置傳送一個交易式推播通知。 例如，如果Adobe Campaign使用者訂閱了兩個應用程式，此使用者會收到兩個通知。 如果使用者已訂閱使用兩種不同裝置的相同應用程式，此使用者會在每種裝置上收到通知。

此配置式的&#x200B;**[!UICONTROL Mobile App Subscriptions]**&#x200B;頁籤中列出了配置式預訂的移動應用程式。 要訪問此頁籤，請選擇一個配置檔案並按一下右側的&#x200B;**[!UICONTROL Edit profile properties]**&#x200B;按鈕。

![](assets/push_notif_subscriptions.png)

有關訪問和編輯配置檔案的詳細資訊，請參閱[關於配置檔案](../../audiences/using/about-profiles.md)。

### 設定以描述檔為基礎的交易推播通知{#configuring-profile-based-transactional-push-notification}

若要傳送交易式推播通知給已訂閱您行動應用程式的Adobe Campaign設定檔，您首先需要建立並設定以Adobe Campaign資料庫為目標的事件。

1. 建立事件配置時，選擇&#x200B;**[!UICONTROL Push notification]**&#x200B;通道和&#x200B;**[!UICONTROL Profile]**&#x200B;目標維（請參閱[建立事件](../../channels/using/configuring-transactional-event.md#creating-an-event)）。

   依預設，交易推播通知會傳送至收件者所訂閱的所有行動應用程式。 若要傳送推播通知給特定行動應用程式，請在清單中選取它。 其他行動應用程式將會由訊息定位，但會排除在傳送之外。

   ![](assets/message-center_push_appfilter.png)

1. 如果要個性化事務性消息，請向事件添加欄位（請參閱[定義事件屬性](../../channels/using/configuring-transactional-event.md#defining-the-event-attributes)）。

   >[!NOTE]
   >
   >您必須至少添加一個欄位才能建立富集。 您不需要建立其他欄位，例如&#x200B;**名字**&#x200B;和&#x200B;**姓氏**，因為您可以使用Adobe Campaign資料庫中的個人化欄位。

1. 建立擴充功能，以將事件連結至&#x200B;**[!UICONTROL Profile]**&#x200B;資源（請參閱[豐富事件](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content)），並選取此擴充功能為&#x200B;**[!UICONTROL Targeting enrichment]**。

   >[!IMPORTANT]
   >
   >此步驟是描述檔事件的必要步驟。

1. [預覽並發佈事件](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event)。

   在預覽事件時，REST API不包含指定註冊Token、應用程式名稱和推播平台的屬性，因為這些屬性將從&#x200B;**[!UICONTROL Profile]**&#x200B;資源中擷取。

   發佈事件後，就會自動建立連結至新事件的交易推播通知。 您現在可以修改並發佈剛建立的訊息（請參閱[本節](#sending-profile-based-transactional-push-notification)）。

1. 將事件整合至您的網站（請參閱[整合事件觸發](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger)）。

### 傳送以描述檔為基礎的交易推播通知{#sending-profile-based-transactional-push-notification}

例如，航空公司想要向所有已訂閱其行動應用程式的Adobe Campaign使用者寄送最後一次登入通知。

1. 移至建立的交易式訊息，以編輯其內容。請參閱[訪問事務性消息](../../channels/using/editing-transactional-message.md#accessing-transactional-messages)。

1. 按一下&#x200B;**[!UICONTROL Content]**&#x200B;塊以修改消息的標題和正文。

   與基於即時事件的配置不同，您可以直接訪問所有配置檔案資訊以個性化您的消息。 請參閱[插入個人化欄位](../../designing/using/personalization.md#inserting-a-personalization-field)。

   如需編輯推播通知內容的詳細資訊，請參閱[準備和傳送推播通知](../../channels/using/preparing-and-sending-a-push-notification.md)。

1. 儲存您的變更並發佈訊息。請參閱[發佈交易式訊息](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message)。
1. 使用Adobe Campaign Standard REST API，將事件傳送至描述檔：

   ```
   {
     "ctx":
     {
       "email":"janegreen@email.com",
       "gateNumber":"D16",
     }
   }
   ```

有關將事件觸發整合到外部系統的詳細資訊，請參閱[整合事件觸發](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger)。

對應的使用者會收到交易推播通知，包括從Adobe Campaign資料庫擷取的所有個人化元素。

>[!NOTE]
>
>沒有註冊Token、應用程式和推播平台欄位。 在此示例中，協調是使用電子郵件欄位執行的。
