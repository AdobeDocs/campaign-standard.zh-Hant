---
title: 配置事務性消息傳遞
seo-title: 配置事務性消息傳遞
description: 配置事務性消息傳遞
seo-description: 瞭解如何設定交易式訊息。
page-status-flag: 從未激活
uuid: 4caeadbe-f4a7-43ce-986d-e99fa9ca0d0d
contentOwner: 紹維亞
products: SG_CAMPAIGN/STANDARD
audience: 管理
content-type: 參考
topic-tags: 配置通道
discoiquuid: 3f968556-e774-43dc-a0b8-7188d7665fbc
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 51d80fc9c683e39b9d08ba7d36b76b71a9dd1e8c

---


# 配置事務性消息傳遞{#configuring-transactional-messaging}

若要使用Adobe Campaign傳送交易訊息，您首先需要說明事件資料的結構。

事件配置必須由管理員執 **行** ，請執行以下步驟：

配置會隨您要發送的事務性消息類型而有所不同。 有關詳細資訊，請參閱事務 [性事件特定配置](#transactional-event-specific-configurations)

一旦發佈事件，就會自動建立對應的交易訊息。 For more on transactional messaging, refer to [this page](../../channels/using/about-transactional-messaging.md).

## 建立事件 {#creating-an-event}

首先，建立符合您需求的事件。

1. 按一下 **[!UICONTROL Adobe Campaign]** 左上角的標誌，然後選取 **[!UICONTROL Marketing plans]** &gt; **[!UICONTROL Transactional messages]** &gt; **[!UICONTROL Event configuration]**。
1. Click the **[!UICONTROL Create]** button.
1. 為活 **[!UICONTROL Label]** 動做 **[!UICONTROL ID]** 一個和一個。 欄位 **[!UICONTROL ID]** 是必填欄位，開頭應為"EVT"。 如果您不使用此首碼，則會在您按一下後自動新增該首碼 **[!UICONTROL Create]**。

   ![](assets/message-center_1.png)

   >[!CAUTION]
   >
   >ID不得超過64個字元，包括EVT首碼。

1. 選擇將用來傳送交易訊息的渠道 **[!UICONTROL Email]**, **[!UICONTROL Mobile (SMS)]** 或 **[!UICONTROL Mobile application]** （推播通知）。

   >[!NOTE]
   >
   >每個事件設定只能使用一個頻道。 事件建立後，便無法變更渠道。

1. 選取與所需事件設定對應的定位維度，然後按一下 **[!UICONTROL Create]**。

   事件型交易訊息會鎖定事件本身包含的資料，而以描述檔為基礎的交易訊息則會鎖定Adobe Campaign資料庫中包含的資料。 有關詳細資訊，請參閱事務 [性事件特定配置](#transactional-event-specific-configurations)。

## 定義事件屬性 {#defining-the-event-attributes}

在該部 **[!UICONTROL Fields]** 分中，定義將整合到事件內容中的屬性，然後可用於個性化事務性消息。

新增和修改欄位的步驟與自訂資源的步 [驟相同](../../developing/using/configuring-the-resource-s-data-structure.md#adding-fields-to-a-resource)。

![](assets/message-center_2.png)

>[!NOTE]
>
>如果您想要建立多語言交易訊息，請使用 **[!UICONTROL AC_language]** ID定義其他事件屬性。 這僅適用於事件事務性消息。 發佈事件後，編輯多語言交易訊息內容的步驟與編輯多語言標準電子郵件的步驟相同。 請參 [閱建立多語言電子郵件](../../channels/using/creating-a-multilingual-email.md)。

## 定義資料集合 {#defining-data-collections}

您可以新增元素的集合至事件內容，每個元素本身包含數個屬性。

此系列可用於交易電子郵件中，以新增產品清單至訊息內容，例如產品清單——價格、參考編號、數量等。 清單的每個產品。

1. 在區段 **[!UICONTROL Collections]** 中，按一下按 **[!UICONTROL Create element]** 鈕。

   ![](assets/message-center_collection_create.png)

1. 新增系列的標籤和ID。
1. 為清單的每個產品新增您要在交易訊息中顯示的所有欄位。

   在此範例中，我們新增了下列欄位：

   ![](assets/message-center_collection_fields.png)

發佈事件和訊息後，您就可以在交易訊息中使用此系列。

以下是此範例的API預覽：

![](assets/message-center_collection_api-preview.png)

**相關主題：**

* [預覽和發佈事件](#previewing-and-publishing-the-event)
* [在事務性消息中使用產品清單](#using-product-listings-in-a-transactional-message)

## 豐富交易式訊息內容 {#enriching-the-transactional-message-content}

利用Adobe Campaign資料庫的資訊豐富交易式訊息內容，讓您個人化訊息。 例如，您可以從每個收件者的姓氏或CRM ID中，復原資料，例如其地址、出生日期或「描述檔」表格中新增的任何其他自訂欄位，以個人化傳送給他們的資訊。

可以利用來自擴展或資源的資訊豐富事務性消 **[!UICONTROL Profile]** 息內 **[!UICONTROL Service]** 容。

此資訊也可以儲存在新資源中。 在這種情況下，資源必須直接連結到或 **[!UICONTROL Profile]** 資源 **[!UICONTROL Service]** ，或通過其他表連結。 例如，在以下配置中，如果資源連結到資源，則可以使用資源（如產品類別或ID）中的資訊豐富事務 **[!UICONTROL Product]** 性消息內 **[!UICONTROL Product]****[!UICONTROL Profile]** 容。

![](assets/message-center_usecaseschema.png)

有關資源建立和發佈的詳細資訊，請參 [閱此頁](../../developing/using/key-steps-to-add-a-resource.md)。

1. 在區段 **[!UICONTROL Enrichment]** 中，按一下按 **[!UICONTROL Create element]** 鈕。

   ![](assets/message-center_addenrichment.png)

1. 選擇要將消息連結到的資源。 在這種情況下，請選擇資 **[!UICONTROL Profile]** 源。

   ![](assets/message-center_new-enrichment.png)

1. 使用按 **[!UICONTROL Create element]** 鈕，將選定資源中的欄位連結到您先前添加到事件的其中一個欄位(請 [參閱定義事件屬性](#defining-the-event-attributes))。

   ![](assets/message-center_enrichment-join.png)

1. 在此示例中，我們協調 **[!UICONTROL Last name]** 和字 **[!UICONTROL First name]** 段與資源中相應的字 **[!UICONTROL Profile]** 段。

   ![](assets/message-center_enrichment-join-fields.png)

   您也可以使用資源豐富事務性消息 **[!UICONTROL Service]** 內容。 有關此方面的更多資訊，請參閱。

1. 在該節 **[!UICONTROL Targeting enrichment]** 中，選擇在傳送執行期間將用作消息目標的擴充。 在此示例中，選擇 **[!UICONTROL Profile]**。 選取定位擴充是描述檔事件的必備項目。

   ![](assets/message-center_marketing_targeting_enrichment.png)

發佈事件和消息後，與資源的鏈 **[!UICONTROL Profile]** 接將允許您豐富事務性消息的內容。

**相關主題：**

* [預覽和發佈事件](#previewing-and-publishing-the-event)。
* [個人化交易訊息](../../channels/using/event-transactional-messages.md#personalizing-a-transactional-message)。

## 預覽和發佈事件 {#previewing-and-publishing-the-event}

您必須先預覽並發佈事件，才能使用事件。

1. 按一 **[!UICONTROL API preview]** 下按鈕，即可檢視網站開發人員在發佈之前所使用的REST API模擬。 發佈事件後，此按鈕也可讓您在生產中檢視API的預覽。 請參 [閱整合網站中事件的觸發](#integrating-the-triggering-of-the-event-in-a-website)。

   ![](assets/message-center_api_preview.png)

   >[!NOTE]
   >
   >REST API會依所選渠道和所選定的定位維度而有所不同。 有關各種配置的詳細資訊，請參閱事務 [性事件特定配置](#transactional-event-specific-configurations)。

1. 按一 **[!UICONTROL Publish]** 下以開始發佈。

   ![](assets/message-center_pub.png)

1. 通過選擇相應的頁籤，可以查看發佈日誌。

   ![](assets/message-center_logs.png)

   您也可以選取標籤，以參考先前的出版品。

>[!NOTE]
>
>每次您修改事件時，必須再按一 **[!UICONTROL Publish]** 次，以產生網站開發人員將使用的更新REST API。

發佈事件後，會自動建立連結至新事件的交易訊息。 要使此事件觸發發送事務性消息，您必須修改並發佈剛建立的消息。 請參 [閱事件交易訊息](../../channels/using/event-transactional-messages.md)。

您可以直接從左側區域的連結存取建立的交易式訊息。

![](assets/message-center_messagegeneration.png)

您也必須將此觸發事件整合至您的網站。 請參 [閱整合網站中事件的觸發](#integrating-the-triggering-of-the-event-in-a-website)。

### 取消發佈事件 {#unpublishing-an-event}

按 **[!UICONTROL Unpublish]** 鈕可讓您取消事件的發佈，該發佈會從REST API中刪除與先前建立的事件對應的資源。 現在，即使事件是透過您的網站觸發，對應的訊息也不會再傳送，也不會儲存在資料庫中。

![](assets/message-center_unpublish.png)

>[!NOTE]
>
>如果您已經發佈了相應的事務性消息，事務性消息發佈也將被取消。 請參 [閱取消發佈交易訊息](../../channels/using/event-transactional-messages.md#unpublishing-a-transactional-message)。

按一下 **[!UICONTROL Publish]** 按鈕以產生新的REST API。

## 整合網站中事件的觸發 {#integrating-the-triggering-of-the-event-in-a-website}

建立事件後，您必須將此事件的觸發整合至您的網站。

在「交易式傳訊操作原則 [](../../channels/using/about-transactional-messaging.md#transactional-messaging-operating-principle) 」一節所述的範例中，您希望當客戶在購物車中購買產品之前離開您的網站時，觸發「購物車放棄」事件。 若要這麼做，您的網站網頁開發人員必須使用Adobe Campaign Standard REST API。

請參閱 [REST API檔案](https://final-docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#transactional-messages-api) 。

## 事務性事件特定配置 {#transactional-event-specific-configurations}

事務性事件配置可能因您要發送的事務性消息類型（事件或配置檔案）以及將使用的渠道而異。

以下各節詳細介紹了根據所需事務性消息應設定哪些特定配置。 如需設定事件的一般步驟的詳細資訊，請參 [閱建立事件](#creating-an-event)。

### 事件型交易訊息 {#event-based-transactional-messages}

若要傳送事件型交易訊息，您首先需要建立並設定事件，以事件本身所包含的資料為目標。
如需詳細資訊，請參 [閱「參與交易訊息](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Managedatatofuelengagingexperiences)」。

1. 建立事件設定時，請選取定 **[!UICONTROL Real-time event]** 位維度(請 [參閱建立事件](#creating-an-event))。
1. 為事件添加欄位，以便能夠個性化事務性消息(請參 [閱定義事件屬性](#defining-the-event-attributes))。
1. 如果您想要使用Adobe Campaign資料庫的其他資訊，請豐富交易訊息內容(請參 [閱豐富交易訊息內容](#enriching-the-transactional-message-content))。

   >[!NOTE]
   >
   >事件型交易訊息應僅使用傳送事件中的資料來定義收件者和訊息內容個人化。 不過，您可以使用Adobe Campaign資料庫的資訊，豐富您交易訊息的內容。

1. 預覽並發佈事件(請參閱 [預覽和發佈事件](#previewing-and-publishing-the-event))。

   在預覽事件時，REST API會包含根據所選頻道指定電子郵件地址或行動電話的屬性。

   發佈事件後，會自動建立連結至新事件的交易訊息。 要觸發事件發送事務性消息，您必須修改並發佈剛建立的消息，請參閱事 [件事務性消息](../../channels/using/event-transactional-messages.md)。

1. 將事件整合至您的網站(請 [參閱整合網站中事件的觸發](#integrating-the-triggering-of-the-event-in-a-website))。

### 基於配置檔案的事務性消息 {#profile-based-transactional-messages}

若要傳送以描述檔為基礎的交易訊息，您首先需要建立並設定Adobe Campaign資料庫中包含的事件定位資料。

1. 建立事件設定時，請選取定 **[!UICONTROL Profile event]** 位維度(請 [參閱建立事件](#creating-an-event))。
1. 為事件添加欄位，以便能夠個性化事務性消息(請參 [閱定義事件屬性](#defining-the-event-attributes))。 您必須至少添加一個欄位才能建立富集。 您不需要建立其他欄位，例如 **名字** 、 **姓氏** ，因為您可以使用Adobe Campaign資料庫中的個人化欄位。
1. 建立擴充功能，以將事件連結至資源(請參 **[!UICONTROL Profile]** 閱豐 [富交易訊息內容](#enriching-the-transactional-message-content))。 使用定位維度時，必須建立 **[!UICONTROL Profile]** 擴充。
1. 預覽並發佈事件(請參閱 [預覽和發佈事件](#previewing-and-publishing-the-event))。

   預覽事件時，REST API不包含指定從資源擷取電子郵件地址或行動電話的屬 **[!UICONTROL Profile]** 性。

   發佈事件後，會自動建立連結至新事件的交易訊息。 要觸發發送事務性消息的事件，您必須修改並發佈剛建立的消息，請參閱 [發送配置檔案事務性消息](../../channels/using/profile-transactional-messages.md#sending-a-profile-transactional-message)。

1. 將事件整合至您的網站(請 [參閱整合網站中事件的觸發](#integrating-the-triggering-of-the-event-in-a-website))。

### 事件型交易推播通知 {#event-based-transactional-push-notifications}

若要傳送交易推播通知，您必須據以設定Adobe Campaign。 請參 [閱推播設定](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html)。

若要向所有選擇接收行動應用程式通知的使用者傳送匿名交易式推播通知，您首先需要建立並設定事件，以事件本身所包含的資料為目標。 相應步驟如下。

事件必須包含下列三個元素：

* 注 **冊Token**，是一個行動應用程式與一個裝置的使用者ID。 它可能不對應Adobe Campaign資料庫中的任何描述檔。
* 行動 **應用程式名稱** （所有裝置皆可使用一個名稱- android和iOS）。 這是Adobe Campaign中設定的行動應用程式ID，將用來接收使用者裝置上的推播通知。 For more on this, refer to this [page](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html)
* 推 **播平台** （Android為「gcm」,iOS為「apns」）。

1. 建立事件設定時，請選取 **[!UICONTROL Mobile application]** 渠道和定 **[!UICONTROL Real-time event]** 位維度(請 [參閱建立事件](#creating-an-event))。
1. 為事件添加欄位，以便能夠個性化事務性消息(請參 [閱定義事件屬性](#defining-the-event-attributes))。
1. 如果您想要使用Adobe Campaign資料庫的其他資訊，請豐富交易訊息內容(請參 [閱豐富交易訊息內容](#enriching-the-transactional-message-content))。

   >[!NOTE]
   >
   >事件型交易訊息應僅使用傳送事件中的資料來定義收件者和訊息內容個人化。 不過，您可以使用Adobe Campaign資料庫的資訊，豐富您交易訊息的內容。

1. 預覽並發佈事件(請參閱 [預覽和發佈事件](#previewing-and-publishing-the-event))。

   在預覽事件時，REST API會包含「registrationToken」、「application」和「pushPlatform」屬性，這些屬性將用來定位傳送。

   ![](assets/message-center_push_api.png)

   發佈事件後，就會自動建立連結至新事件的交易推播通知。 若要修改並發佈剛建立的訊息，請參閱傳 [送交易推播通知以事件為目標](../../channels/using/transactional-push-notifications.md#transactional-push-notifications-targeting-an-event)。

1. 將事件整合至您的網站(請 [參閱整合網站中事件的觸發](#integrating-the-triggering-of-the-event-in-a-website))。

### 以個人檔案為基礎的交易推播通知 {#profile-based-transactional-push-notifications}

若要傳送交易式推播通知給已訂閱您行動應用程式的Adobe Campaign設定檔，您首先需要建立並設定以Adobe Campaign資料庫為目標的事件。

1. 建立事件設定時，請選取 **[!UICONTROL Mobile application]** 渠道和定 **[!UICONTROL Profile]** 位維度(請 [參閱建立事件](#creating-an-event))。

   依預設，交易推播通知會傳送至收件者所訂閱的所有行動應用程式。 若要傳送推播通知給特定行動應用程式，請在清單中選取它。 其他行動應用程式將會由訊息定位，但會排除在傳送之外。

   ![](assets/message-center_push_appfilter.png)

1. 如果您想要個人化交易訊息，請新增欄位至事件(請 [參閱定義事件屬性](#defining-the-event-attributes))。

   >[!NOTE]
   >
   >您必須至少添加一個欄位才能建立富集。 您不需要建立其他欄位，例如 **名字** 、 **姓氏** ，因為您可以使用Adobe Campaign資料庫中的個人化欄位。

1. 建立擴充功能，以將事件連結至資源(請參 **[!UICONTROL Profile]** 閱豐 [富交易訊息內容](#enriching-the-transactional-message-content))。 使用定位維度時，必須建立 **[!UICONTROL Profile]** 擴充。
1. 預覽並發佈事件(請參閱 [預覽和發佈事件](#previewing-and-publishing-the-event))。

   預覽事件時，REST API不包含指定註冊Token、應用程式名稱和推播平台的屬性，因為這些屬性將從資源中擷取 **[!UICONTROL Profile]** 。

   發佈事件後，就會自動建立連結至新事件的交易推播通知。 若要修改並發佈剛建立的訊息，請參閱傳 [送交易式推播通知以定位描述檔](../../channels/using/transactional-push-notifications.md#transactional-push-notifications-targeting-a-profile)。

1. 將事件整合至您的網站(請 [參閱整合網站中事件的觸發](#integrating-the-triggering-of-the-event-in-a-website))。

### 設定事件以傳送後續訊息 {#configuring-an-event-to-send-a-follow-up-message}

後續訊息是預先定義的行銷傳送範本，可用於工作流程中，以傳送訊息給特定交易訊息的收件者。 如需詳細資訊，請參 [閱後續訊息](../../channels/using/follow-up-messages.md)。

1. 使用您建立的事件設定來傳送事件交易訊息。 請參 [閱事件型交易訊息](#event-based-transactional-messages)。
1. 設定事件時，請勾選方 **[!UICONTROL Create follow-up delivery template for this event]** 塊，再發佈事件。

   ![](assets/message-center_follow-up-checkbox.png)

1. 預覽並發佈事件(請參閱 [預覽和發佈事件](#previewing-and-publishing-the-event))。

   發佈事件後，會自動建立交易訊息和連結至新事件的後續傳送範本。 有關使用後續消息的詳細資訊，請 [參閱發送後續消息](../../channels/using/follow-up-messages.md#sending-a-follow-up-message)。

## 使用案例：配置事件以發送事務性消息 {#use-case--configuring-an-event-to-send-a-transactional-message}

在此範例中，我們想設定事件，以便在網站上每次購買產品後傳送確認訊息，並具備下列必要條件：

當我們想要透過其CRM ID來識別客戶時，請先確定已使用 **[!UICONTROL Profile]** 此新欄位擴充資源。

同樣地，必須已建立並發佈與購買對應的自訂資源，且必須連結至資 **[!UICONTROL Profile]** 源。 這樣，您就可以從此資源中檢索資訊，以豐富郵件內容。

有關資源建立和發佈的詳細資訊，請參 [閱此頁](../../developing/using/key-steps-to-add-a-resource.md)。

1. 使用渠道和定位維 **[!UICONTROL Email]** 度建立新 **[!UICONTROL Profile]** 事件(請 [參閱建立事件](#creating-an-event))。
1. 定義可用於個性化事務性消息的屬性。 在本例中，請新增「CRM ID」和「產品識別碼」欄位(請參 [閱定義事件屬性](#defining-the-event-attributes))。

   ![](assets/message-center_usecase1.png)

1. 若要以客戶先前購買的相關資訊豐富訊息內容，請建立以資源為目標的擴充 **[!UICONTROL Purchase]** 功能(請 [參閱豐富交易訊息內容](#enriching-the-transactional-message-content))。

   ![](assets/message-center_usecase2.png)

1. 在先前新增至訊息的「產品識別碼」欄位與資源中的對應欄位之間建立連結條 **[!UICONTROL Purchase]** 件

   ![](assets/message-center_usecase3.png)

1. 預覽並發佈事件(請參閱 [預覽和發佈事件](#previewing-and-publishing-the-event))。
1. 將事件整合在您的網站中(請 [參閱整合網站中事件的觸發](#integrating-the-triggering-of-the-event-in-a-website))。

