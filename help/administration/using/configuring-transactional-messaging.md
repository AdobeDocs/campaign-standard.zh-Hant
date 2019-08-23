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
source-git-commit: 8800562922e68d33cca93cd838c294198b630684

---


# 設定交易式傳訊{#configuring-transactional-messaging}

若要使用Adobe Campaign傳送交易訊息，您必須先描述事件資料的結構。

事件設定必須 **由管理員** 執行，下列步驟如下：

視您要傳送的交易訊息類型而定，設定可能會有所不同。如需詳細資訊，請參閱 [交易事件特定設定](../../administration/using/configuring-transactional-messaging.md#transactional-event-specific-configurations)

一旦發佈事件，就會自動建立對應的交易訊息。有關交易訊息的更多資訊，請參閱 [本頁](../../channels/using/about-transactional-messaging.md)。

## 建立事件 {#creating-an-event}

開始建立符合您需求的事件。

1. 按一下 **[!UICONTROL Adobe Campaign]** 標誌，位於左上角，然後選取 **[!UICONTROL Marketing plans]** &gt; **[!UICONTROL Transactional messages]** &gt; **[!UICONTROL Event configuration]**。
1. 按一下 **[!UICONTROL Create]** 按鈕。
1. 為事件提供 **[!UICONTROL Label]** 和登入 **[!UICONTROL ID]** 。**[!UICONTROL ID]** 欄位為強制欄位，應以首碼「EVT」開頭。如果您未使用此首碼，在按一下 **[!UICONTROL Create]**&#x200B;後會自動新增此前置詞。

   ![](assets/message-center_1.png)

   >[!CAUTION]
   >
   >ID不得超過64個字元，包括EVT首碼。

1. 選取將用來傳送交易訊息 **[!UICONTROL Email]****[!UICONTROL Mobile (SMS)]** 或 **[!UICONTROL Mobile application]** (推播通知)的渠道。

   >[!NOTE]
   >
   >每個事件設定只能使用一個渠道。一旦建立事件後，您就無法變更渠道。

1. 選取對應至所需事件設定的定位維度 **[!UICONTROL Create]**，然後按一下。

   事件型交易訊息目標資料包含在事件本身中，而以描述檔為基礎的交易訊息則會定位在Adobe Campaign資料庫中。如需詳細資訊，請參閱 [交易事件特定設定](../../administration/using/configuring-transactional-messaging.md#transactional-event-specific-configurations)。

## 定義事件屬性 {#defining-the-event-attributes}

在 **[!UICONTROL Fields]** 區段中，定義將整合至事件內容的屬性，然後將其用於個人化的訊息。

新增和修改欄位的步驟與 [自訂資源](../../developing/using/configuring-the-resource-s-data-structure.md#adding-fields-to-a-resource)相同。

![](assets/message-center_2.png)

>[!NOTE]
>
>如果您想要建立多語言交易訊息，請使用 **[!UICONTROL AC_language]** ID定義另一個事件屬性。這只適用於事件交易訊息。在發佈事件後，編輯多語言交易訊息內容的步驟就與多語言標準電子郵件相同。請參閱 [建立多語言電子郵件](../../channels/using/creating-a-multilingual-email.md)。

## 定義資料集 {#defining-data-collections}

您可以將元素新增至事件內容，每個元素本身包含數個屬性。

此系列可用於交易式電子郵件中，將產品清單新增至訊息的內容，例如產品清單-價格、參考數字、數量等。清單中的每個產品。

1. 在 **[!UICONTROL Collections]** 區段中按一下 **[!UICONTROL Create element]** 按鈕。

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

## 豐富交易訊息內容 {#enriching-the-transactional-message-content}

利用Adobe Campaign資料庫中的資訊豐富交易訊息內容，讓您可以個人化訊息。例如，從每個收件者的姓氏或CRM ID，您可以恢復資料(例如其地址或出生日期)，或是設定檔表格中新增的任何其他自訂欄位，以便個人化傳送給他們的資訊。

透過擴充 **[!UICONTROL Profile]** 或 **[!UICONTROL Service]** 資源的資訊豐富交易訊息內容。

這些資訊也可以儲存在新資源中。在此情況下，資源必須直接連結至或 **[!UICONTROL Profile]****[!UICONTROL Service]** 透過其他表格連結。例如，在下列組態中，可以將交易訊息內容與來自產品類別或 **[!UICONTROL Product]** ID( **[!UICONTROL Product]** 如果資源連結 **[!UICONTROL Profile]** 到資源)的資訊豐富。

![](assets/message-center_usecaseschema.png)

如需資源建立和發佈的詳細資訊，請參閱 [此頁面](../../developing/using/key-steps-to-add-a-resource.md)。

1. 在 **[!UICONTROL Enrichment]** 區段中按一下 **[!UICONTROL Create element]** 按鈕。

   ![](assets/message-center_addenrichment.png)

1. 選取您要連結訊息的資源。在此情況下，請選擇 **[!UICONTROL Profile]** 資源。

   ![](assets/message-center_new-enrichment.png)

1. 使用 **[!UICONTROL Create element]** 按鈕將欄位從所選資源連結至您先前新增至事件的其中一個欄位(請參閱 [定義事件屬性](../../administration/using/configuring-transactional-messaging.md#defining-the-event-attributes))。

   ![](assets/message-center_enrichment-join.png)

1. 在此範例中，我們將與 **[!UICONTROL Last name]** 資源中對應欄位的 **[!UICONTROL First name]** 欄位 **[!UICONTROL Profile]** 調和。

   ![](assets/message-center_enrichment-join-fields.png)

1. **[!UICONTROL Targeting enrichment]** 在區段中，選取將在傳送執行期間作為訊息目標的擴充功能。在此範例 **[!UICONTROL Profile]**&#x200B;中，選取。對於以描述檔為基礎的事件，需要選取定位增強功能。

   ![](assets/message-center_marketing_targeting_enrichment.png)

一旦事件和訊息發佈後， **[!UICONTROL Profile]** 含有資源的連結就可讓您豐富交易訊息的內容。

**相關主題：**

* [預覽和發佈事件](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)。
* [個人化交易訊息](../../channels/using/event-transactional-messages.md#personalizing-a-transactional-message)。

## 預覽和發佈事件 {#previewing-and-publishing-the-event}

您必須先預覽並發佈事件，才能使用事件。

1. 按一下 **[!UICONTROL API preview]** 按鈕以查看REST API的模擬，您的網站開發人員將會在發佈之前使用此API。在發佈事件後，此按鈕也可讓您查看生產中API的預覽。請參閱 [整合網站中的事件觸發](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)。

   ![](assets/message-center_api_preview.png)

   >[!NOTE]
   >
   >REST API會根據選取的頻道和所選的定位維度而有所不同。如需各種組態的詳細資訊，請參閱 [交易事件特定設定](../../administration/using/configuring-transactional-messaging.md#transactional-event-specific-configurations)。

1. 按一下 **[!UICONTROL Publish]** 以開始發佈。

   ![](assets/message-center_pub.png)

1. 您可以選擇對應的標籤來檢視出版物記錄。

   ![](assets/message-center_logs.png)

   您也可以選擇此標籤來諮詢先前的出版物。

>[!NOTE]
>
>每次修改事件時，您必須 **[!UICONTROL Publish]** 再次按一下，產生網站開發人員將使用的更新REST API。

在發佈事件後，會自動建立連結至新事件的交易訊息。為了讓事件觸發傳送交易訊息，您必須修改並發佈剛才建立的訊息。請參閱 [事件交易訊息](../../channels/using/event-transactional-messages.md)。

您可以存取直接從左側區域連結建立的交易訊息。

![](assets/message-center_messagegeneration.png)

您也必須將此觸發器事件整合至您的網站。請參閱 [整合網站中的事件觸發](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)。

### 取消發佈事件 {#unpublishing-an-event}

**[!UICONTROL Unpublish]** 此按鈕可讓您取消事件的發佈，此事件會從REST API刪除與您先前建立之事件對應的資源。現在，即使是透過您的網站觸發事件，對應的訊息也不會再傳送，也不會儲存在資料庫中。

![](assets/message-center_unpublish.png)

>[!NOTE]
>
>如果您已發佈對應的交易訊息，則也會取消交易訊息出版物。請參閱 [取消發佈交易訊息](../../channels/using/event-transactional-messages.md#unpublishing-a-transactional-message)。

按一下 **[!UICONTROL Publish]** 按鈕以產生新REST API。

## 整合網站中事件的觸發 {#integrating-the-triggering-of-the-event-in-a-website}

建立事件後，您將必須將此事件觸發整合至您的網站。

在 [Transactional Messaging作業原則](../../channels/using/about-transactional-messaging.md#transactional-messaging-operating-principle) 區段中所述的範例中，您想要在客戶離開您的網站前觸發「購物車放棄」事件，然後再在購物車中購買產品。若要這麼做，您的網站網頁開發人員必須使用Adobe Campaign Standard REST API。

請參閱 [REST API文件](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#transactional-messages-api) 。

## 交易事件特定設定 {#transactional-event-specific-configurations}

交易事件設定可能會視您要傳送的交易訊息類型(事件或描述檔)以及將使用的頻道而有所不同。

下列章節詳細說明應根據所需的交易訊息設定何種設定。如需設定事件的一般步驟的詳細資訊，請參閱 [建立事件](../../administration/using/configuring-transactional-messaging.md#creating-an-event)。

### 事件型交易訊息 {#event-based-transactional-messages}

若要傳送事件型交易訊息，您首先需要建立並設定事件目標中包含的事件。
如需詳細資訊，請參閱 [「參與交易訊息」](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Managedatatofuelengagingexperiences)。

1. 建立事件設定時，選取 **[!UICONTROL Real-time event]** 定位維度(請參閱 [建立事件](../../administration/using/configuring-transactional-messaging.md#creating-an-event))。
1. 新增欄位至事件，以便能夠個人化交易訊息(請參閱 [定義事件屬性](../../administration/using/configuring-transactional-messaging.md#defining-the-event-attributes))。
1. 如果您想要從Adobe Campaign資料庫使用其他資訊(請參閱 [豐富交易訊息內容](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content))，請豐富交易訊息內容。

   >[!NOTE]
   >
   >事件型交易訊息只應使用傳送事件中的資料來定義收件者和訊息內容個人化。不過，您可以使用Adobe Campaign資料庫中的資訊豐富交易訊息的內容。

1. 預覽並發佈事件(請參閱 [預覽和發佈事件](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event))。

   在預覽事件時，REST API包含根據選取的頻道來指定電子郵件地址或行動電話的屬性。

   在發佈事件後，會自動建立連結至新事件的交易訊息。為了讓事件觸發傳送交易訊息，您必須修改並發佈剛才建立的訊息，請參閱 [事件交易訊息](../../channels/using/event-transactional-messages.md)。

1. 將事件整合至您的網站(請參閱 [整合網站](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)中的事件)。

### 以描述檔為基礎的交易訊息 {#profile-based-transactional-messages}

若要傳送以描述檔為基礎的交易訊息，您必須先建立並設定Adobe Campaign資料庫中包含的事件定位資料。

1. 建立事件設定時，選取 **[!UICONTROL Profile event]** 定位維度(請參閱 [建立事件](../../administration/using/configuring-transactional-messaging.md#creating-an-event))。
1. 新增欄位至事件，以便能夠個人化交易訊息(請參閱 [定義事件屬性](../../administration/using/configuring-transactional-messaging.md#defining-the-event-attributes))。您必須至少新增一個欄位來建立擴充功能。您不需要建立其他欄位，例如 **「名字** 」和 **「姓氏」，** 因為您可以從Adobe Campaign資料庫使用個人化欄位。
1. 建立擴充功能，將事件連結至 **[!UICONTROL Profile]** 資源(請參閱 [豐富交易訊息內容](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content))。使用 **[!UICONTROL Profile]** 定位維度時，必須建立擴充功能。
1. 預覽並發佈事件(請參閱 [預覽和發佈事件](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event))。

   在預覽事件時，REST API不包含指定電子郵件地址或行動電話的屬性，因為它將從 **[!UICONTROL Profile]** 資源中擷取。

   在發佈事件後，會自動建立連結至新事件的交易訊息。為了讓事件觸發傳送交易訊息，您必須修改並發佈剛才建立的訊息，請參閱 [傳送描述檔交易訊息](../../channels/using/profile-transactional-messages.md#sending-a-profile-transactional-message)。

1. 將事件整合至您的網站(請參閱 [整合網站](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)中的事件)。

### 事件型交易推播通知 {#event-based-transactional-push-notifications}

若要傳送交易推播通知，您必須據此設定Adobe Campaign。請參閱 [推送設定](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html)。

若要傳送匿名交易推播通知給選擇接收行動應用程式通知的所有使用者，您必須先建立並設定事件目標所包含的事件。以下列出相應步驟。

事件必須包含下列三個元素：

* **註冊Token**，此為一個行動應用程式和一個裝置的使用者ID。它可能不對應Adobe Campaign資料庫中的任何描述檔。
* **行動應用程式名稱** (適用於所有裝置- Android和iOS)。這是在Adobe Campaign中設定的行動應用程式ID，用來接收使用者裝置上的推播通知。如需更多資訊，請參閱本 [頁](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html)
* **推播平台** (適用於Android的「gcm」或iOS適用的「apns」)。

1. 建立事件設定時，請選取 **[!UICONTROL Mobile application]** 渠道和 **[!UICONTROL Real-time event]** 定位維度(請參閱 [建立事件](../../administration/using/configuring-transactional-messaging.md#creating-an-event))。
1. 新增欄位至事件，以便能夠個人化交易訊息(請參閱 [定義事件屬性](../../administration/using/configuring-transactional-messaging.md#defining-the-event-attributes))。
1. 如果您想要從Adobe Campaign資料庫使用其他資訊(請參閱 [豐富交易訊息內容](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content))，請豐富交易訊息內容。

   >[!NOTE]
   >
   >事件型交易訊息只應使用傳送事件中的資料來定義收件者和訊息內容個人化。不過，您可以使用Adobe Campaign資料庫中的資訊豐富交易訊息的內容。

1. 預覽並發佈事件(請參閱 [預覽和發佈事件](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event))。

   在預覽事件時，REST API包含「registrationToken」、「應用程式」和將用來定位傳送的「pushPlatform」屬性。

   ![](assets/message-center_push_api.png)

   在發佈事件後，會自動建立連結至新事件的交易推播通知。若要修改並發佈剛才建立的訊息，請參閱 [傳送針對事件](../../channels/using/transactional-push-notifications.md#transactional-push-notifications-targeting-an-event)的交易推播通知。

1. 將事件整合至您的網站(請參閱 [整合網站](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)中的事件)。

### 以描述檔為基礎的交易推播通知 {#profile-based-transactional-push-notifications}

若要傳送交易式推播通知給已訂閱您行動應用程式的Adobe Campaign設定檔，您必須先建立並設定定位Adobe Campaign資料庫的事件。

1. 建立事件設定時，請選取 **[!UICONTROL Mobile application]** 渠道和 **[!UICONTROL Profile]** 定位維度(請參閱 [建立事件](../../administration/using/configuring-transactional-messaging.md#creating-an-event))。

   根據預設，交易推播通知會傳送給收件者訂閱的所有行動應用程式。若要將推播通知傳送至特定的行動應用程式，請在清單中選取它。其他行動應用程式將會被訊息鎖定，但將排除在傳送之外。

   ![](assets/message-center_push_appfilter.png)

1. 如果您想要個人化交易訊息，請將欄位新增至事件(請參閱 [定義事件屬性](../../administration/using/configuring-transactional-messaging.md#defining-the-event-attributes))。

   >[!NOTE]
   >
   >您必須至少新增一個欄位來建立擴充功能。您不需要建立其他欄位，例如 **「名字** 」和 **「姓氏」，** 因為您可以從Adobe Campaign資料庫使用個人化欄位。

1. 建立擴充功能，將事件連結至 **[!UICONTROL Profile]** 資源(請參閱 [豐富交易訊息內容](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content))。使用 **[!UICONTROL Profile]** 定位維度時，必須建立擴充功能。
1. 預覽並發佈事件(請參閱 [預覽和發佈事件](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event))。

   在預覽事件時，REST API不包含指定註冊Token的屬性、應用程式名稱和推送平台，因為它們將從 **[!UICONTROL Profile]** 資源擷取。

   在發佈事件後，會自動建立連結至新事件的交易推播通知。若要修改並發佈剛才建立的訊息，請參閱 [傳送針對描述檔](../../channels/using/transactional-push-notifications.md#transactional-push-notifications-targeting-a-profile)的交易推播通知。

1. 將事件整合至您的網站(請參閱 [整合網站](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)中的事件)。

### 設定事件以傳送追蹤訊息 {#configuring-an-event-to-send-a-follow-up-message}

後續訊息是預先定義的行銷傳送範本，可用於工作流程中，將訊息傳送給特定交易訊息的收件者。如需詳細資訊，請參閱 [「後續訊息](../../channels/using/follow-up-messages.md)」。

1. 使用您建立的相同事件設定來傳送事件交易訊息。請參閱 [事件型交易訊息](../../administration/using/configuring-transactional-messaging.md#event-based-transactional-messages)。
1. 設定事件時，請先勾選 **[!UICONTROL Create follow-up delivery template for this event]** 方塊，然後再發佈事件。

   ![](assets/message-center_follow-up-checkbox.png)

1. 預覽並發佈事件(請參閱 [預覽和發佈事件](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event))。

   在發佈事件後，會自動建立交易訊息和連結至新事件的後續傳送範本。如需使用後續訊息的詳細資訊，請參閱 [傳送追蹤訊息](../../channels/using/follow-up-messages.md#sending-a-follow-up-message)。

## 使用案例：設定事件以傳送交易訊息 {#use-case--configuring-an-event-to-send-a-transactional-message}

在此範例中，我們想要設定事件，以便在網站上每次購買後傳送確認訊息，並使用下列先決條件：

我們希望透過他的CRM ID識別客戶，請先確定 **[!UICONTROL Profile]** 此新欄位已擴充資源。

同樣地，必須建立和發佈對應的自訂資源，而且必須連結 **[!UICONTROL Profile]** 至資源。如此，您就可以擷取此資源的資訊，豐富訊息內容。

如需資源建立和發佈的詳細資訊，請參閱 [此頁面](../../developing/using/key-steps-to-add-a-resource.md)。

1. 使用 **[!UICONTROL Email]** 頻道和 **[!UICONTROL Profile]** 定位維度建立新事件(請參閱 [建立事件](../../administration/using/configuring-transactional-messaging.md#creating-an-event))。
1. 定義將可個人化交易訊息的屬性。在本範例中，新增「CRM ID」和「產品識別碼」欄位(請參閱 [定義事件屬性](../../administration/using/configuring-transactional-messaging.md#defining-the-event-attributes))。

   ![](assets/message-center_usecase1.png)

1. 若要透過有關客戶先前購買的資訊豐富訊息內容，請建立目標資源的擴充 **[!UICONTROL Purchase]** (請參閱 [豐富交易訊息內容](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content))。

   ![](assets/message-center_usecase2.png)

1. 建立先前新增至訊息之「產品識別碼」欄位之間的連結條件，以及 **[!UICONTROL Purchase]** 資源的對應欄位

   ![](assets/message-center_usecase3.png)

1. 預覽並發佈事件(請參閱 [預覽和發佈事件](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event))。
1. 整合網站中的事件(請參閱 [整合網站](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)中的事件)。

