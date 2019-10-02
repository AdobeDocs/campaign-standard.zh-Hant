---
title: 確認服務訂閱
seo-title: 確認服務訂閱
description: 確認服務訂閱
seo-description: 請依照下列步驟，為訂閱Adobe Campaign中服務的描述檔設定確認訊息。
page-status-flag: 從未激活
uuid: 23e6c4c2-e2c7-472f-b616-36a95225ac1d
contentOwner: 紹維亞
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: 參考
topic-tags: 管理預訂
discoiquuid: 1a24504e-7f9d-4297-b39e-c5f085b0f388
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 8b85bbad7458286252a2900ce730288f6e52442e

---


# 確認服務訂閱{#confirming-subscription-to-a-service}

## 關於傳送訂閱確認 {#sending-subscription-confirmation}

本節說明如何向訂閱特定服務的設定檔傳送自動自訂確認電子郵件。

當您想要傳送訂閱（或取消訂閱）服務的確認訊息時，可以使用預設訊息或自訂訊息。 在建立服務部分中顯示了選擇確認消 [息的步驟](../../audiences/using/creating-a-service.md) 。

如果您選擇使用預設訊息，則可以編輯其內容，但有下列限制：
* 您只能使用事件上下文中有限的欄位個人化訊息內容。
* 對於使用預設模式的所有服務，此消息都相同。

若要針對特定服務傳送特定確認電子郵件，您可以建立自訂訊息，您也可以運用其他資源的個人化欄位。 要執行此操作，必須建立和配置事務性消息。 此訊息可被參考：
* 服務本身。 有關詳細資訊，請參 [閱配置服務的確認消息](../../audiences/using/confirming-subscription-to-a-service.md#configuring-confirmation-message-from-service)。
* 從訂閱登陸頁面。 如需詳細資訊，請參 [閱從著陸頁面設定確認訊息](../../audiences/using/confirming-subscription-to-a-service.md#configuring-confirmation-message-from-landing-page)。

## Configuring confirmation message from a service {#configuring-confirmation-message-from-service}

For example, you want to automatically send a confirmation message to the visitors of your website when they subscribe to your brand newsletter.

You need to configure a transactional email and reference that message from the desired service (subscription to your brand newsletter in this case). In order to enrich the transactional message with service information, you can define a reconciliation when creating the event.

When configuring it from the service, the confirmation transactional message will be sent only the first time each visitor subscribes to that service. If a profile is already subscribed, no confirmation message will be sent again to that profile.

### Step 1: Create the confirmation email {#step-1--create-the-confirmation-email-1}

A confirmation email will be automatically sent to each profile subscribing to the newsletter (through a landing page or any other means). The subscription is considered as an event and the email is a transactional message which will target each profile that subscribes to the service.[](../../channels/using/about-transactional-messaging.md)

Steps to create the confirmation email are described below. As the transactional message will be referenced in the service, you need to create it first.

#### Create the event {#create-the-event-1}

確認電子郵件是一個交易性訊息，當它回應事件時：訂閱服務。 This message will be sent to confirm subscription to your newsletter.

1. 從&gt; &gt;功能表建 **[!UICONTROL Marketing plans]** 立事 **[!UICONTROL Transactional messages]** 件， **[!UICONTROL Event configuration]** 可從Adobe Campaign標誌存取。
1. 輸入標籤，選取定位維度，然後按一下 **[!UICONTROL Create]**。

   The configuration steps are presented in the Configuring transactional messaging section.[](../../administration/using/configuring-transactional-messaging.md)

1. 在該節 **[!UICONTROL Fields]** 中，按一下 **[!UICONTROL Create element]** 並添 **[!UICONTROL publicLabel]** 加到資料結構中以啟用協調。

   ![](assets/confirmation_publicLabel-field.png)

   >[注意]
   >
   >The  field is mandatory. **[!UICONTROL publicLabel]**&#x200B;如果您未將其新增至事件資料結構，Adobe Campaign將無法與服務進行協調。 訂閱服務時，此欄位將填入對應 **[!UICONTROL Service label]** 的服務。

1. 在該部 **[!UICONTROL Enrichment]** 分中，單 **[!UICONTROL Create element]** 擊並選擇 **[!UICONTROL Service]** 目標資源。

   ![](assets/confirmation_enrichment-service.png)

1. 在該 **[!UICONTROL Join definition]** 節中，將資源的 **[!UICONTROL publicLabel]** 欄位與事件 **[!UICONTROL Service]** 配置 **[!UICONTROL publicLabel]** 的欄位進行映射。

   ![](assets/confirmation_publicLabel-join.png)

   >[注意]
   >
   >這可讓您使用交易訊息中資源 **[!UICONTROL Service]** 的個人化欄位。

1. 儲存事件設定，然後按一 **[!UICONTROL Publish]** 下以發佈事件。

活動已就緒。 您現在可以設計交易式電子郵件訊息。

#### 設計確認訊息 {#design-the-confirmation-message-1}

確認電子郵件是根據您剛發佈的事件而傳送的交易訊息。

1. From the Adobe Campaign logo, select  &gt;  and click .**[!UICONTROL Marketing plans]****[!UICONTROL Transactional messages]****[!UICONTROL Transactional messages]**
1. Select the transactional email corresponding to the event that you just published.

1. Click the  section and select an email template. **[!UICONTROL Content]** For more on editing a transactional message content, see Event transactional messages.[](../../channels/using/event-transactional-messages.md)
1. 由於您可以直接存取資源中的所有欄 **[!UICONTROL Service]** 位，因此您可以從 **[!UICONTROL Context]** &gt; **[!UICONTROL Real-time event (rtEvent)]** &gt; **[!UICONTROL Event context (ctx)]****[!UICONTROL Service]** &gt;節點選擇任何欄位，以個人化您的內容。

   ![](assets/confirmation_personalization-service.png)

   有關個人化交易訊息的詳細資訊，請參 [閱本節](../../channels/using/event-transactional-messages.md#personalizing-a-transactional-message)。

1. 使用測試設定檔預覽訊息。 For more on this, see Defining a test profile in a transactional message.[](../../channels/using/event-transactional-messages.md#defining-a-test-profile-in-a-transactional-message)

1. 按一 **[!UICONTROL Save & close]** 下以儲存您的內容。
1. 發佈交易式訊息。 請參 [閱發佈交易訊息](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message)。

### 步驟2:建立和配置服務 {#step-2--create-and-configure-the-service-1}

1. 從進階功能表「 **設定檔與觀眾** &gt; **服務** 」（透過Adobe Campaign標誌）中，建立服務。
1. 轉至「服務」 **[!UICONTROL Service properties]** 儀表板中的按鈕 ![](assets/edit_darkgrey-24px.png) 訪問的部分。
1. 填寫欄 **[!UICONTROL Service label]** 位。

   ![](assets/confirmation_service-label.png)

   >[注意]
   >
   >您必須填寫此欄位，才能啟用事務性消息的協調。

1. 在節 **[!UICONTROL Confirmation messages]** 中，選擇 **[!UICONTROL Custom message]**:此模式允許您為訂閱服務的配置式參考特定確認消息。
1. Select the  associated with the transactional message that you created.**[!UICONTROL Custom subscription event configuration]**

   ![](assets/confirmation_service-confirmation-message.png)

1. 按一 **[!UICONTROL Confirm]** 下並儲存服務。

現在，每次設定檔訂閱此服務時，他都會收到您所定義的交易訊息，並有對應至所選服務的個人化欄位。 訊息只會在使用者第一次訂閱時傳送。

## 從著陸頁面設定確認訊息 {#configuring-confirmation-message-from-landing-page}

您也可以使用登陸頁面區段中的選項，從訂閱登陸頁面 **[!UICONTROL Start sending messages]** 參考 **[!UICONTROL Job]** 確認訊息。

當從著陸頁面參考確認訊息時，每次提交著陸頁面時都會傳送訊息（即使已訂閱描述檔亦然）。

### 步驟1:建立確認電子郵件 {#step-1--create-the-confirmation-email-2}

確認電子郵件會自動傳送至透過登陸頁面訂閱電子報的每個個人檔案。 訂閱會視為事件，而電子郵件則是交易式 [訊息](../../channels/using/about-transactional-messaging.md) ，會針對訂閱服務的每個描述檔。

建立這些元素的步驟如下所述。 當交易性訊息將在登陸頁面中引用時，您必須先建立它。

#### 建立事件 {#create-the-event-2}

確認電子郵件是交 [易性訊息](../../channels/using/about-transactional-messaging.md) ，當它回應事件時：訂閱服務。 此訊息將會傳送以確認訂閱您的電子報。

1. 從&gt; &gt;功能表建 **[!UICONTROL Marketing plans]** 立事 **[!UICONTROL Transactional messages]** 件， **[!UICONTROL Event configuration]** 可從Adobe Campaign標誌存取。
1. 輸入標籤，選取定位維度，然後按一下 **[!UICONTROL Create]**。

   配置步驟將顯示在「配置事務 [消息傳遞](../../administration/using/configuring-transactional-messaging.md) 」部分。

1. 在該節 **[!UICONTROL Fields]** 中，按一下 **[!UICONTROL Create element]** 並添 **[!UICONTROL serviceName]** 加到資料結構中以啟用協調。

   ![](assets/confirmation_serviceName-field.png)

   >[注意]
   >
   >欄位 **[!UICONTROL serviceName]** 為必填欄位。 如果您未將其新增至事件資料結構，Adobe Campaign將無法與訂閱的服務進行協調。

1. 在該部 **[!UICONTROL Enrichment]** 分中，單 **[!UICONTROL Create element]** 擊並選擇 **[!UICONTROL Service]** 目標資源。
1. 在該 **[!UICONTROL Join definition]** 節中，將資源的 **[!UICONTROL serviceName]** 欄位與事件 **[!UICONTROL Service]** 配置 **[!UICONTROL name]** 的欄位進行映射。

   ![](assets/confirmation_serviceName-join.png)

   >[注意]
   >
   >這可讓您使用交易訊息中資源 [!UICONTROL Service] 的個人化欄位。

#### 設計確認訊息 {#design-the-confirmation-message-2}

本節將介紹設計事務性消息的 [步驟](../../audiences/using/confirming-subscription-to-a-service.md#design-the-confirmation-message-1)。

### 步驟2:建立和配置服務 {#step-2--create-and-configure-the-service-2}

1. From the advanced menu  &gt;  via the Adobe Campaign logo, create a service.**[!UICONTROL Profiles & audiences]****[!UICONTROL Services]**
1. Go to the  section, accessed via the  button in the service dashboard.**[!UICONTROL Service properties]**![](assets/edit_darkgrey-24px.png)
1. 填寫欄 **[!UICONTROL Service label]** 位。 This label will be displayed in the confirmation message and in the subscription landing page.
1. 按一 **[!UICONTROL Confirm]** 下並儲存服務。

### 步驟3:建立並設定著陸頁面 {#step-3--create-and-configure-the-landing-page}

建立將發佈在您網站上的訂閱登陸頁面。

To create and configure this landing page, follow the steps below:

1. Design a new landing page based on the  template.[](../../channels/using/about-landing-pages.md)**[!UICONTROL Subscription]**
1. 編輯著陸頁面屬性。 在&gt; **[!UICONTROL Job]** 區 **[!UICONTROL Specific actions]** 段中，選取 **[!UICONTROL Specific service]** 選項並從下拉式清單中選擇您剛建立的服務。

   ![](assets/confirmation_lp-specific-service.png)

1. 選擇 **[!UICONTROL Start sending message]** 選項，然後從下拉清單中選擇剛建立的事務性消息。

   ![](assets/confirmation_lp-start-sending-message.png)

1. 自訂登陸頁面的內容。

1. [測試並發佈](../../channels/using/sharing-a-landing-page.md) 著陸頁面。

現在，每次描述檔透過送出登陸頁面訂閱您的電子報時，他都會收到您定義有對應至服務的個人化欄位的確認訊息。

>[NOTE]
>
>每次提交登陸頁面時都會傳送訊息，即使描述檔已訂閱亦然。
