---
title: 異動推送通知
description: 瞭解如何與Adobe Campaign Standard發送事務推式通知。
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
ht-degree: 4%

---

# 異動推送通知{#transactional-push-notifications}

您可以使用Adobe Campaign在iOS和Android移動設備上發送事務推式通知。 這些消息是通過利用Experience Cloud移動SDK在Adobe Campaign設定的移動應用程式接收的。

>[!NOTE]
>
>推送通道是可選的。 請檢查您的授權合約。有關標準推送通知的詳細資訊，請參閱 [關於推式通知](../../channels/using/about-push-notifications.md)。

要能夠發送事務推式通知，您需要相應地配置Adobe Campaign。 請參閱 [配置移動應用程式](../../administration/using/configuring-a-mobile-application.md)。

您可以發送兩種類型的事務推式通知：

* [針對事件的事務推式通知](#transactional-push-notifications-targeting-an-event)
* [事務推式通知目標配置檔案](#transactional-push-notifications-targeting-a-profile) 從Adobe Campaign資料庫

## 針對事件的事務推式通知 {#transactional-push-notifications-targeting-an-event}

你可以用Adobe Campaign **匿名事務推送通知給所有用戶** 已選擇從您的移動應用程式接收通知的用戶。

在這種情況下， **事件本身中包含的資料用於定義傳遞目標**。 沒有利用Adobe Campaign綜合資料資料庫的資料。

### 配置基於事件的事務推送通知 {#configuring-event-based-transactional-push-notification}

要向已選擇從移動應用程式接收通知的所有用戶發送事務推送通知，您首先需要建立並配置一個事件，以事件本身包含的資料為目標。

>[!NOTE]
>
>您仍然可以使用 [事件屬性](../../channels/using/configuring-transactional-event.md#defining-the-event-attributes) （來自事件的資料）和 [事件富集](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content) （市場活動資料庫中的資料）。 請參閱 [下面的示例](#sending-event-based-transactional-push-notification)。

事件必須包含以下三個元素：

* A **註冊令牌**，即一個移動應用程式和一個設備的用戶ID。 它可能與Adobe Campaign資料庫中的任何配置檔案不對應。
* A **移動應用程式名** (適用於所有設備 — 安卓和iOS)。 這是在Adobe Campaign配置的用於在用戶設備上接收推送通知的移動應用程式的ID。 有關此內容的詳細資訊，請參閱 [配置移動應用程式](../../administration/using/configuring-a-mobile-application.md)。
* A **推送平台** (Android的「gcm」或iOS的「apns」)。

要配置事件，請執行以下步驟：

1. 建立事件配置時，選擇 **[!UICONTROL Push notification]** 頻道和 **[!UICONTROL Real-time event]** 目標維度（請參見） [建立事件](../../channels/using/configuring-transactional-event.md#creating-an-event))。
1. 將欄位添加到事件。 這將允許您個性化事務性消息(請參閱 [定義事件屬性](../../channels/using/configuring-transactional-event.md#defining-the-event-attributes))。 在本示例中，定義&quot;gateNumber&quot;、&quot;lastname&quot;和&quot;firstname&quot;欄位。
1. 您還可以豐富郵件的內容。 為此，請從連結到事件配置的表中添加欄位(請參閱 [豐富活動內容](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content))。

   <!--Event-based transactional messaging is supposed to use only the data that are in the sent event to define the recipient and the message content personalization. However, you can enrich the content of your transactional message using information from the Adobe Campaign database.-->

1. [預覽和發佈事件](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event)。

   在預覽事件時，REST API包含「registrationToken」、「application」和「pushPlatform」屬性，這些屬性將用於目標傳遞。

   ![](assets/message-center_push_api.png)

   一旦發佈了該事件，將自動建立連結到新事件的事務推送通知。 您現在可以修改並發佈剛建立的郵件(請參見 [此部分](#sending-event-based-transactional-push-notification))。

1. 將活動整合到您的網站(請參閱 [整合事件觸發](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger))。

### 發送基於事件的事務推送通知 {#sending-event-based-transactional-push-notification}

例如，航空公司希望邀請其移動應用用戶到相關登機口登機。

該公司將通過一個設備使用一個移動應用程式，為每個用戶發送一個事務推送通知（用註冊令牌標識）。

1. 移至建立的交易式訊息，以編輯其內容。請參閱 [訪問事務性消息](../../channels/using/editing-transactional-message.md#accessing-transactional-messages)。

   ![](assets/message-center_push_message.png)

1. 按一下 **[!UICONTROL Content]** 阻止以修改郵件的標題和正文。

1. 您可以插入個性化欄位以添加在建立事件時定義的元素(請參閱 [定義事件屬性](../../channels/using/configuring-transactional-event.md#defining-the-event-attributes))。

   ![](assets/message-center_push_content.png)

   要查找這些欄位，請按一下項目旁邊的鉛筆，按一下 **[!UICONTROL Insert personalization field]** 選擇 **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]**。

   ![](assets/message-center_push_personalization.png)

   有關編輯推送通知內容的詳細資訊，請參閱 [準備和發送推送通知](../../channels/using/preparing-and-sending-a-push-notification.md)。

1. 如果希望使用Adobe Campaign資料庫中的其他資訊，還可以豐富事務性消息內容(請參見 [豐富活動內容](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content))。

1. 儲存您的變更並發佈訊息。請參閱[發佈交易式訊息](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message)。

1. 使用Adobe Campaign StandardREST API，使用Android(gcm)上的一個移動應用程式(WeFlight)向註冊令牌(ABCDEF12345789)發送事件，其中包含登機資料：

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

   有關將事件觸發整合到外部系統的詳細資訊，請參見 [整合事件觸發](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger)。

如果註冊令牌存在，則相應用戶接收包括以下內容的事務推送通知：

*「簡·格林，你好，登船才剛開始！ B18次列車最後通告。」*

## 針對配置檔案的事務推式通知 {#transactional-push-notifications-targeting-a-profile}

您可以發送事務推送通知 **訂閱您的移動應用程式的Adobe Campaign個人資料**。 此傳遞可包含 [個性化欄位](../../designing/using/personalization.md#inserting-a-personalization-field)，如收件人的名字，直接從Adobe Campaign資料庫中檢索。

在這種情況下，事件必須包含一些欄位 **允許與Adobe Campaign資料庫的配置檔案進行調節**。

當目標配置式時，每個移動應用程式和每個設備發送一個事務推送通知。 例如，如果Adobe Campaign用戶訂閱了兩個應用程式，則此用戶將收到兩個通知。 如果用戶已使用兩個不同的設備訂閱了同一應用程式，則此用戶將在每台設備上接收通知。

配置檔案訂閱的移動應用程式列在 **[!UICONTROL Mobile App Subscriptions]** 的子菜單。 要訪問此頁籤，請選擇一個配置檔案，然後按一下 **[!UICONTROL Edit profile properties]** 按鈕。

![](assets/push_notif_subscriptions.png)

有關訪問和編輯配置檔案的詳細資訊，請參閱 [關於配置檔案](../../audiences/using/about-profiles.md)。

### 配置基於配置檔案的事務推送通知 {#configuring-profile-based-transactional-push-notification}

要向已訂閱您的移動應用程式的Adobe Campaign配置檔案發送事務推送通知，您首先需要建立並配置針對Adobe Campaign資料庫的事件。

1. 建立事件配置時，選擇 **[!UICONTROL Push notification]** 頻道和 **[!UICONTROL Profile]** 目標維度（請參見） [建立事件](../../channels/using/configuring-transactional-event.md#creating-an-event))。

   預設情況下，事務推送通知將發送到收件人訂閱的所有移動應用程式。 要將推送通知發送到特定的移動應用程式，請在清單中選擇它。 其他移動應用程式將被消息定向，但將被排除在發送之外。

   ![](assets/message-center_push_appfilter.png)

1. 如果要個性化事務性消息，請向事件添加欄位(請參閱 [定義事件屬性](../../channels/using/configuring-transactional-event.md#defining-the-event-attributes))。

   >[!NOTE]
   >
   >必須至少添加一個欄位才能建立富集。 您不需要建立其他欄位，如 **名字** 和 **姓氏** 因為您將能夠使用Adobe Campaign資料庫中的個性化欄位。

1. 建立富集，以將事件連結到 **[!UICONTROL Profile]** 資源(請參閱 [豐富活動內容](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content))並選擇此富集作為 **[!UICONTROL Targeting enrichment]**。

   >[!IMPORTANT]
   >
   >此步驟對於基於配置檔案的事件是必需的。

1. [預覽和發佈事件](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event)。

   在預覽事件時，REST API不包含指定註冊令牌、應用程式名稱和推式平台的屬性，因為它們將從 **[!UICONTROL Profile]** 資源。

   一旦發佈了該事件，將自動建立連結到新事件的事務推送通知。 您現在可以修改並發佈剛建立的郵件(請參見 [此部分](#sending-profile-based-transactional-push-notification))。

1. 將活動整合到您的網站(請參閱 [整合事件觸發](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger))。

### 發送基於配置檔案的事務推送通知 {#sending-profile-based-transactional-push-notification}

例如，一家航空公司希望向所有訂閱其移動應用的Adobe Campaign用戶發送最後一次登機通知。

1. 移至建立的交易式訊息，以編輯其內容。請參閱 [訪問事務性消息](../../channels/using/editing-transactional-message.md#accessing-transactional-messages)。

1. 按一下 **[!UICONTROL Content]** 阻止以修改郵件的標題和正文。

   與基於即時事件的配置不同，您可以直接訪問所有配置檔案資訊以個性化您的消息。 請參閱[插入個人化欄位](../../designing/using/personalization.md#inserting-a-personalization-field)。

   有關編輯推送通知內容的詳細資訊，請參閱 [準備和發送推送通知](../../channels/using/preparing-and-sending-a-push-notification.md)。

1. 儲存您的變更並發佈訊息。請參閱[發佈交易式訊息](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message)。
1. 使用Adobe Campaign StandardREST API向配置檔案發送事件：

   ```
   {
     "ctx":
     {
       "email":"janegreen@email.com",
       "gateNumber":"D16",
     }
   }
   ```

有關將事件觸發整合到外部系統的詳細資訊，請參見 [整合事件觸發](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger)。

相應用戶接收包括從Adobe Campaign資料庫檢索的所有個性化元素的事務推式通知。

>[!NOTE]
>
>沒有註冊令牌、應用程式和推送平台欄位。 在本示例中，使用電子郵件欄位執行協調。

## 更改事務推送通知中的目標映射 {#change-target-mapping}

事務推式通知使用特定 [目標映射](../../administration/using/target-mappings-in-campaign.md) 包含發送此類交貨所需的技術設定。

要更改此目標映射，請執行以下步驟：

1. 從事務性消息清單中，選擇推送通知。

1. 在消息儀表板中，按一下 **[!UICONTROL Edit properties]** 按鈕

   ![](assets/message-center_push_edit.png)

1. 展開 **[!UICONTROL Advanced parameters]** 的子菜單。

1. 按一下&#x200B;**[!UICONTROL Select a 'Target mapping' element]**。

   ![](assets/message-center_push_target-mapping.png)

1. 從清單中選擇目標映射。

   >[!NOTE]
   >
   >在發送時實現最佳交付準備時間和效能 **基於輪廓** 事務推式通知，使用 **[!UICONTROL Profile - Real-time event for Push (mapRtEventAppSubRcp)]** 目標映射。

   ![](assets/message-center_push_target-mapping_change.png)

1. 確認更改並發佈消息。 請參閱[發佈交易式訊息](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message)。

   >[!IMPORTANT]
   >
   >必須再次發佈消息，更改才能生效，否則仍將使用以前的目標映射。


