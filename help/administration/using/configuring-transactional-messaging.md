---
title: 設定交易式傳訊
seo-title: 設定交易式傳訊
description: 設定交易式傳訊
seo-description: 瞭解如何設定交易訊息。
page-status-flag: 從未啓動
uuid: caeadbe-f4 a7-43ce-986d-e99 fa9 ca0 d0 d
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 管理
content-type: reference
topic-tags: 設定頻道
discoiquuid: 3f968556-e774-43dc-a0 b8-7188d7665 fbc
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 806dc4736ffb395a0eea102090c688102478aaca

---


# Configuring transactional messaging{#configuring-transactional-messaging}

若要使用Adobe Campaign傳送交易訊息，您必須先描述事件資料的結構。

Event configuration must be performed by an **administrator** by following the steps below:

視您要傳送的交易訊息類型而定，設定可能會有所不同。For more on this, refer to [Transactional event specific configurations](../../administration/using/configuring-transactional-messaging.md#transactional-event-specific-configurations)

一旦發佈事件，就會自動建立對應的交易訊息。For more on transactional messaging, refer to [this page](../../channels/using/about-transactional-messaging.md).

## Creating an event {#creating-an-event}

開始建立符合您需求的事件。

1. Click the **[!UICONTROL Adobe Campaign]** logo, in the top left corner, then select **[!UICONTROL Marketing plans]** &gt; **[!UICONTROL Transactional messages]** &gt; **[!UICONTROL Event configuration]**.
1. Click the **[!UICONTROL Create]** button.
1. Give a **[!UICONTROL Label]** and an **[!UICONTROL ID]** to the event. **[!UICONTROL ID]** 欄位為強制欄位，應以首碼「EVT」開頭。If you do not use this prefix, it is automatically added once you click **[!UICONTROL Create]**.

   ![](assets/message-center_1.png)

1. Select the channel that will be used to send your transactional messages **[!UICONTROL Email]**, **[!UICONTROL Mobile (SMS)]** or **[!UICONTROL Mobile application]** (push notification).

   >[!NOTE]
   >
   >每個事件設定只能使用一個渠道。一旦建立事件後，您就無法變更渠道。

1. Select the targeting dimension corresponding to the desired event configuration and click **[!UICONTROL Create]**.

   事件型交易訊息目標資料包含在事件本身中，而以描述檔為基礎的交易訊息則會定位在Adobe Campaign資料庫中。For more on this, refer to [Transactional event specific configurations](../../administration/using/configuring-transactional-messaging.md#transactional-event-specific-configurations).

## Defining the event attributes {#defining-the-event-attributes}

In the **[!UICONTROL Fields]** section, define the attributes that will be integrated into the event content and will then be able to be used to personalize the transactional message.

The steps for adding and modifying fields are the same as for [custom resources](../../developing/using/configuring-the-resource-s-data-structure.md#adding-fields-to-a-resource).

![](assets/message-center_2.png)

>[!NOTE]
>
>If you want to create a multilingual transactional message, define an additional event attribute with the **[!UICONTROL AC_language]** ID. 這只適用於事件交易訊息。在發佈事件後，編輯多語言交易訊息內容的步驟就與多語言標準電子郵件相同。See [Creating a multilingual email](../../channels/using/creating-a-multilingual-email.md).

## Defining data collections {#defining-data-collections}

您可以將元素新增至事件內容，每個元素本身包含數個屬性。

此系列可用於交易式電子郵件中，將產品清單新增至訊息的內容，例如產品清單-價格、參考數字、數量等。清單中的每個產品。

1. In the **[!UICONTROL Collections]** section, click the **[!UICONTROL Create element]** button.

   ![](assets/message-center_collection_create.png)

1. 為您的系列新增標籤和ID。
1. 為清單中每個產品新增您要顯示在交易訊息中的所有欄位。

   在此範例中，我們新增了下列欄位：

   ![](assets/message-center_collection_fields.png)

一旦事件和訊息發佈後，您就可以在交易訊息中使用此系列。

以下是此範例的API預覽：

![](assets/message-center_collection_api-preview.png)

**相關主題：**

* [預覽和發佈事件](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)
* [在交易訊息中使用產品清單](../../channels/using/event-transactional-messages.md#using-product-listings-in-a-transactional-message)

## Enriching the transactional message content {#enriching-the-transactional-message-content}

利用Adobe Campaign資料庫中的資訊豐富交易訊息內容，讓您可以個人化訊息。例如，從每個收件者的姓氏或CRM ID，您可以恢復資料(例如其地址或出生日期)，或是設定檔表格中新增的任何其他自訂欄位，以便個人化傳送給他們的資訊。

It is possible to enrich the transactional message content with information from extended **[!UICONTROL Profile]** or **[!UICONTROL Service]** resources.

這些資訊也可以儲存在新資源中。In that case, the resource must be linked to the **[!UICONTROL Profile]** or **[!UICONTROL Service]** resources either directly, or via another table. For example, in the configuration below, it is possible to enrich the transactional message content with information from the **[!UICONTROL Product]** resource like the product category or ID, if the **[!UICONTROL Product]** resource is linked to the **[!UICONTROL Profile]** resource.

![](assets/message-center_usecaseschema.png)

For more on resource creation and publishing, refer to [this page](../../developing/using/key-steps-of-adding-a-resource.md).

1. In the **[!UICONTROL Enrichment]** section, click the **[!UICONTROL Create element]** button.

   ![](assets/message-center_addenrichment.png)

1. 選取您要連結訊息的資源。In this case, choose the **[!UICONTROL Profile]** resource.

   ![](assets/message-center_new-enrichment.png)

1. Use the **[!UICONTROL Create element]** button to link a field from the selected resource to one of the fields you previously added to the event (see [Defining the event attributes](../../administration/using/configuring-transactional-messaging.md#defining-the-event-attributes)).

   ![](assets/message-center_enrichment-join.png)

1. In this example, we reconcile the **[!UICONTROL Last name]** and the **[!UICONTROL First name]** fields with the corresponding fields in the **[!UICONTROL Profile]** resource.

   ![](assets/message-center_enrichment-join-fields.png)

1. **[!UICONTROL Targeting enrichment]** 在區段中，選取將在傳送執行期間作為訊息目標的擴充功能。In this example, select **[!UICONTROL Profile]**. 對於以描述檔為基礎的事件，需要選取定位增強功能。

   ![](assets/message-center_marketing_targeting_enrichment.png)

Once the event and the message are published, the link with the **[!UICONTROL Profile]** resource will allow you to enrich the content of the transactional message.

**相關主題：**

* [預覽和發佈事件](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)。
* [個人化交易訊息](../../channels/using/event-transactional-messages.md#personalizing-a-transactional-message)。

## Previewing and publishing the event {#previewing-and-publishing-the-event}

您必須先預覽並發佈事件，才能使用事件。

1. Click the **[!UICONTROL API preview]** button to see a simulation of the REST API that will be used by your website developer before it is published. 在發佈事件後，此按鈕也可讓您查看生產中API的預覽。See [Integrating the triggering of the event in a website](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website).

   ![](assets/message-center_api_preview.png)

   >[!NOTE]
   >
   >REST API會根據選取的頻道和所選的定位維度而有所不同。For more details on the various configurations, refer to [Transactional event specific configurations](../../administration/using/configuring-transactional-messaging.md#transactional-event-specific-configurations).

1. Click **[!UICONTROL Publish]** to start publication.

   ![](assets/message-center_pub.png)

1. 您可以選擇對應的標籤來檢視出版物記錄。

   ![](assets/message-center_logs.png)

   您也可以選擇此標籤來諮詢先前的出版物。

>[!NOTE]
>
>Each time you modify the event, you must click **[!UICONTROL Publish]** again to generate the updated REST API that will be used by your website developer.

在發佈事件後，會自動建立連結至新事件的交易訊息。為了讓事件觸發傳送交易訊息，您必須修改並發佈剛才建立的訊息。See [Event transactional messages](../../channels/using/event-transactional-messages.md).

您可以存取直接從左側區域連結建立的交易訊息。

![](assets/message-center_messagegeneration.png)

您也必須將此觸發器事件整合至您的網站。See [Integrating the triggering of the event in a website](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website).

### Unpublishing an event {#unpublishing-an-event}

**[!UICONTROL Unpublish]** 此按鈕可讓您取消事件的發佈，此事件會從REST API刪除與您先前建立之事件對應的資源。現在，即使是透過您的網站觸發事件，對應的訊息也不會再傳送，也不會儲存在資料庫中。

![](assets/message-center_unpublish.png)

>[!NOTE]
>
>如果您已發佈對應的交易訊息，則也會取消交易訊息出版物。See [Unpublishing a transactional message](../../channels/using/event-transactional-messages.md#unpublishing-a-transactional-message).

Click the **[!UICONTROL Publish]** button to generate a new REST API.

## Integrating the triggering of the event in a website {#integrating-the-triggering-of-the-event-in-a-website}

建立事件後，您將必須將此事件觸發整合至您的網站。

In the example described in the [Transactional messaging operating principle](../../channels/using/about-transactional-messaging.md#transactional-messaging-operating-principle) section, you want a "Cart abandonment" event to be triggered whenever one of your clients leaves your website before purchasing the products in their cart. 若要這麼做，您的網站網頁開發人員必須使用Adobe Campaign Standard REST API。

See the [REST API Documentation](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#transactional-messages-api) .

## Transactional event specific configurations {#transactional-event-specific-configurations}

交易事件設定可能會視您要傳送的交易訊息類型(事件或描述檔)以及將使用的頻道而有所不同。

下列章節詳細說明應根據所需的交易訊息設定何種設定。For more on the general steps to configure an event, refer to [Creating an event](../../administration/using/configuring-transactional-messaging.md#creating-an-event).

### Event-based transactional messages {#event-based-transactional-messages}

若要傳送事件型交易訊息，您首先需要建立並設定事件目標中包含的事件。

1. When creating the event configuration, select the **[!UICONTROL Real-time event]** targeting dimension (see [Creating an event](../../administration/using/configuring-transactional-messaging.md#creating-an-event)).
1. Add fields to the event, in order to be able to personalize the transactional message (see [Defining the event attributes](../../administration/using/configuring-transactional-messaging.md#defining-the-event-attributes)).
1. Enrich the transactional message content if you want to use additional information from the Adobe Campaign database (see [Enriching the transactional message content](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content)).

   >[!NOTE]
   >
   >事件型交易訊息只應使用傳送事件中的資料來定義收件者和訊息內容個人化。不過，您可以使用Adobe Campaign資料庫中的資訊豐富交易訊息的內容。

1. Preview and publish the event (see [Previewing and publishing the event](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)).

   在預覽事件時，REST API包含根據選取的頻道來指定電子郵件地址或行動電話的屬性。

   在發佈事件後，會自動建立連結至新事件的交易訊息。In order for the event to trigger sending a transactional message, you must modify and publish the message that was just created, see [Event transactional messages](../../channels/using/event-transactional-messages.md).

1. Integrate the event into your website (see [Integrating the triggering of the event in a website](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)).

### Profile-based transactional messages {#profile-based-transactional-messages}

若要傳送以描述檔為基礎的交易訊息，您必須先建立並設定Adobe Campaign資料庫中包含的事件定位資料。

1. When creating the event configuration, select the **[!UICONTROL Profile event]** targeting dimension (see [Creating an event](../../administration/using/configuring-transactional-messaging.md#creating-an-event)).
1. Add fields to the event, in order to be able to personalize the transactional message (see [Defining the event attributes](../../administration/using/configuring-transactional-messaging.md#defining-the-event-attributes)). 您必須至少新增一個欄位來建立擴充功能。You do not need to create other fields such as **First name** and **Last name** as you will be able to use personalization fields from the Adobe Campaign database.
1. Create an enrichment in order to link the event to the **[!UICONTROL Profile]** resource (see [Enriching the transactional message content](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content)). Creating an enrichment is mandatory when using a **[!UICONTROL Profile]** targeting dimension.
1. Preview and publish the event (see [Previewing and publishing the event](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)).

   When previewing the event, the REST API does not contain an attribute specifying the email address or the mobile phone as it will be retrieved from the **[!UICONTROL Profile]** resource.

   在發佈事件後，會自動建立連結至新事件的交易訊息。In order for the event to trigger sending a transactional message, you must modify and publish the message that was just created, see [Sending a profile transactional message](../../channels/using/profile-transactional-messages.md#sending-a-profile-transactional-message).

1. Integrate the event into your website (see [Integrating the triggering of the event in a website](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)).

### Event-based transactional push notifications {#event-based-transactional-push-notifications}

若要傳送交易推播通知，您必須據此設定Adobe Campaign。See [Push configuration](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html).

若要傳送匿名交易推播通知給選擇接收行動應用程式通知的所有使用者，您必須先建立並設定事件目標所包含的事件。以下列出相應步驟。

事件必須包含下列三個元素：

* **註冊Token**，此為一個行動應用程式和一個裝置的使用者ID。它可能不對應Adobe Campaign資料庫中的任何描述檔。
* **行動應用程式名稱** (適用於所有裝置- Android和iOS)。這是在Adobe Campaign中設定的行動應用程式ID，用來接收使用者裝置上的推播通知。For more on this, refer to this [page](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html)
* **推播平台** (適用於Android的「gcm」或iOS適用的「apns」)。

1. When creating the event configuration, select the **[!UICONTROL Mobile application]** channel and the **[!UICONTROL Real-time event]** targeting dimension (see [Creating an event](../../administration/using/configuring-transactional-messaging.md#creating-an-event)).
1. Add fields to the event, in order to be able to personalize the transactional message (see [Defining the event attributes](../../administration/using/configuring-transactional-messaging.md#defining-the-event-attributes)).
1. Enrich the transactional message content if you want to use additional information from Adobe Campaign database (see [Enriching the transactional message content](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content)).

   >[!NOTE]
   >
   >事件型交易訊息只應使用傳送事件中的資料來定義收件者和訊息內容個人化。不過，您可以使用Adobe Campaign資料庫中的資訊豐富交易訊息的內容。

1. Preview and publish the event (see [Previewing and publishing the event](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)).

   在預覽事件時，REST API包含「registrationToken」、「應用程式」和將用來定位傳送的「pushPlatform」屬性。

   ![](assets/message-center_push_api.png)

   在發佈事件後，會自動建立連結至新事件的交易推播通知。To modify and publish the message that was just created, see [Sending a transactional push notification targeting an event](/channels/using/transactional-push-notifications.html#sending-a-transactional-push-notification-targeting-an
----------event#sending-a-transactional-push-notification-targeting-an
----------event#sending-a-transactional-push-notification-targeting-an
----------event#sending-a-transactional-push-notification-targeting-an
----------event).

1. Integrate the event into your website (see [Integrating the triggering of the event in a website](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)).

### Profile-based transactional push notifications {#profile-based-transactional-push-notifications}

若要傳送交易式推播通知給已訂閱您行動應用程式的Adobe Campaign設定檔，您必須先建立並設定定位Adobe Campaign資料庫的事件。

1. When creating the event configuration, select the **[!UICONTROL Mobile application]** channel and the **[!UICONTROL Profile]** targeting dimension (see [Creating an event](../../administration/using/configuring-transactional-messaging.md#creating-an-event)).

   根據預設，交易推播通知會傳送給收件者訂閱的所有行動應用程式。若要將推播通知傳送至特定的行動應用程式，請在清單中選取它。其他行動應用程式將會被訊息鎖定，但將排除在傳送之外。

   ![](assets/message-center_push_appfilter.png)

1. Add fields to the event, if you want to personalize the transactional message (see [Defining the event attributes](../../administration/using/configuring-transactional-messaging.md#defining-the-event-attributes)).

   >[!NOTE]
   >
   >您必須至少新增一個欄位來建立擴充功能。You do not need to create other fields such as **First name** and **Last name** as you will be able to use personalization fields from the Adobe Campaign database.

1. Create an enrichment in order to link the event to the **[!UICONTROL Profile]** resource (see [Enriching the transactional message content](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content)). Creating an enrichment is mandatory when using a **[!UICONTROL Profile]** targeting dimension.
1. Preview and publish the event (see [Previewing and publishing the event](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)).

   When previewing the event, the REST API does not contain an attribute specifying the registration token, the application name and the push platform as they will be retrieved from the **[!UICONTROL Profile]** resource.

   在發佈事件後，會自動建立連結至新事件的交易推播通知。To modify and publish the message that was just created, see [Sending a transactional push notification targeting a profile](/channels/using/transactional-push-notifications.html#sending-a-transactional-push-notification-targeting-a
----------profile#sending-a-transactional-push-notification-targeting-a
----------profile#sending-a-transactional-push-notification-targeting-a
----------profile#sending-a-transactional-push-notification-targeting-a
----------profile).

1. Integrate the event into your website (see [Integrating the triggering of the event in a website](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)).

### Configuring an event to send a follow-up message {#configuring-an-event-to-send-a-follow-up-message}

後續訊息是預先定義的行銷傳送範本，可用於工作流程中，將訊息傳送給特定交易訊息的收件者。For more on this, see [Follow-up messages](../../channels/using/follow-up-messages.md).

1. 使用您建立的相同事件設定來傳送事件交易訊息。See [Event-based transactional messages](../../administration/using/configuring-transactional-messaging.md#event-based-transactional-messages).
1. When configuring your event, check the **[!UICONTROL Create follow-up delivery template for this event]** box before publishing the event.

   ![](assets/message-center_follow-up-checkbox.png)

1. Preview and publish the event (see [Previewing and publishing the event](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)).

   在發佈事件後，會自動建立交易訊息和連結至新事件的後續傳送範本。For more on using follow-up messages, see [Sending a follow-up message](../../channels/using/follow-up-messages.md#sending-a-follow-up-message).

## Use case: configuring an event to send a transactional message {#use-case--configuring-an-event-to-send-a-transactional-message}

在此範例中，我們想要設定事件，以便在網站上每次購買後傳送確認訊息，並使用下列先決條件：

As we want to identify our client via his CRM ID, first make sure that the **[!UICONTROL Profile]** resource has been extended with this new field.

In the same way, a custom resource corresponding to purchases must have been created and published, and must be linked to the **[!UICONTROL Profile]** resource. 如此，您就可以擷取此資源的資訊，豐富訊息內容。

For more on resource creation and publishing, refer to [this page](../../developing/using/key-steps-of-adding-a-resource.md).

1. Create a new event using the **[!UICONTROL Email]** channel and the **[!UICONTROL Profile]** targeting dimension (see [Creating an event](../../administration/using/configuring-transactional-messaging.md#creating-an-event)).
1. 定義將可個人化交易訊息的屬性。In our case, add the "CRM ID" and the "Product identifier" fields (see [Defining the event attributes](../../administration/using/configuring-transactional-messaging.md#defining-the-event-attributes)).

   ![](assets/message-center_usecase1.png)

1. To enrich the message content with information regarding the client's previous purchases, create an enrichment targeting the **[!UICONTROL Purchase]** resource (see [Enriching the transactional message content](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content)).

   ![](assets/message-center_usecase2.png)

1. Create a join condition between the "Product identifier" field that was previously added to the message, and the corresponding field from the **[!UICONTROL Purchase]** resource

   ![](assets/message-center_usecase3.png)

1. Preview and publish the event (see [Previewing and publishing the event](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)).
1. Integrate the event in your website (see [Integrating the triggering of the event in a website](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)).

