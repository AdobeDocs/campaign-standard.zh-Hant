---
title: 確認訂閱服務
description: 請依照下列步驟，為訂閱 Adobe Campaign 中服務的設定檔設定確認訊息。
page-status-flag: never-activated
uuid: 23e6c4c2-e2c7-472f-b616-36a95225ac1d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-subscriptions
discoiquuid: 1a24504e-7f9d-4297-b39e-c5f085b0f388
internal: n
snippet: y
translation-type: ht
source-git-commit: 95e01eb33097fc76caac3f4dd5f5591461b887cf
workflow-type: ht
source-wordcount: '1322'
ht-degree: 100%

---


# 確認訂閱服務{#confirming-subscription-to-a-service}

## 關於傳送訂閱確認 {#sending-subscription-confirmation}

本節說明如何向訂閱特定服務的設定檔傳送自動自訂確認電子郵件。

當您想要傳送訂閱（或取消訂閱）服務的確認訊息時，可以使用預設訊息或自訂訊息。在[建立服務](../../audiences/using/creating-a-service.md)區段中顯示了選取確認訊息的步驟。

如果您選取使用預設訊息，則可以編輯其內容，但有下列限制：
* 您只能使用事件內容的有限欄位，以個人化訊息內容。
* 對於使用預設模式的所有服務，此訊息都相同。

若要針對特定服務傳送特定確認電子郵件，您可以建立自訂訊息，您也可以運用其他資源的個人化欄位。要執行此操作，必須建立和設定交易式訊息。此訊息可供參考：
* 服務本身。如需詳細資訊，請參閱[設定服務的確認訊息](#configuring-confirmation-message-from-service)。
* 從訂閱登錄頁面。如需詳細資訊，請參閱[從登錄頁面設定確認訊息](#configuring-confirmation-message-from-landing-page)。

## 從服務設定確認訊息 {#configuring-confirmation-message-from-service}

例如，您想要在網站的訪客訂閱您的品牌電子報時，自動傳送確認訊息給他們。

您需要設定交易式電子郵件，並參考所需服務（在此情況下訂閱您的品牌電子報）中的訊息。為了使交易式訊息與服務資訊更加豐富，可以在建立事件時定義調解。

從服務設定時，確認交易式訊息只會在每位訪客第一次訂閱該服務時傳送。如果已訂閱設定檔，則不會再傳送任何確認訊息給該設定檔。

### 步驟 1：建立確認電子郵件 {#step-1--create-the-confirmation-email-1}

系統會自動傳送確認電子郵件給訂閱電子報的每個個人檔案（透過登錄頁面或任何其他方式）。會將訂閱視為事件，而電子郵件則是[交易式訊息](../../channels/using/about-transactional-messaging.md)，會將目標設為訂閱服務的每個設定檔。

建立確認電子郵件的步驟如下。由於服務會參考交易式訊息，因此您需要先建立它。

#### 建立事件 {#create-the-event-1}

確認電子郵件是一則交易式訊息，當它回應事件時：訂閱服務。此訊息將會傳送以確認訂閱您的電子報。

1. 從 **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Event configuration]** 功能表建立事件，可從 Adobe Campaign 標誌存取。
1. 輸入標籤，選取目標維度，然後按一下 **[!UICONTROL Create]**。

   設定步驟將顯示在[設定交易式訊息傳送](../../administration/using/configuring-transactional-messaging.md)區段。

1. 在 **[!UICONTROL Fields]** 區段中，按一下 **[!UICONTROL Create element]** 並將 **[!UICONTROL publicLabel]** 新增至資料結構以啟用調解。

   ![](assets/confirmation_publicLabel-field.png)

   >[!NOTE]
   >
   >**[!UICONTROL publicLabel]** 欄位為必填欄位。如果您未將其新增至事件資料結構，Adobe Campaign 將無法與服務進行調解。訂閱服務時，此欄位將填入相對應服務的 **[!UICONTROL Service label]**。

1. 在 **[!UICONTROL Enrichment]** 區段中，按一下 **[!UICONTROL Create element]** 並選取 **[!UICONTROL Service]** 目標資源。

   ![](assets/confirmation_enrichment-service.png)

1. 在 **[!UICONTROL Join definition]** 區段中，將 **[!UICONTROL Service]** 資源的 **[!UICONTROL publicLabel]** 欄位與事件設定的 **[!UICONTROL publicLabel]** 欄位相對應。

   ![](assets/confirmation_publicLabel-join.png)

   >[!NOTE]
   >
   >這可讓您使用交易式訊息中 **[!UICONTROL Service]** 資源的個人化欄位。

1. 儲存事件設定，然後按一下 **[!UICONTROL Publish]** 以發佈事件。

活動已就緒。您現在可以設計交易式電子郵件訊息。

#### 設計確認訊息 {#design-the-confirmation-message-1}

確認電子郵件是根據您剛發佈的事件而傳送的交易式訊息。

1. 從 Adobe Campaign 標誌中，選取 **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** 並按一下 **[!UICONTROL Transactional messages]**。
1. 選取與您剛發佈之事件對應的交易式電子郵件。

1. 按一下 **[!UICONTROL Content]** 區段並選取電子郵件範本。有關編輯交易式訊息內容的詳細資訊，請參閱[事件交易式訊息](../../channels/using/event-transactional-messages.md)。
1. 由於您可以直接存取 **[!UICONTROL Service]** 資源中的所有欄位，因此您可以從 **[!UICONTROL Context]** > **[!UICONTROL Real-time event (rtEvent)]** > **[!UICONTROL Event context (ctx)]** >**[!UICONTROL Service]** 節點選取任何欄位，以個人化您的內容。

   ![](assets/confirmation_personalization-service.png)

   有關個人化交易式訊息的詳細資訊，請參閱[本區段](../../channels/using/event-transactional-messages.md#personalizing-a-transactional-message)。

1. 使用測試設定檔預覽訊息。如需詳細資訊，請參閱[在交易式訊息中定義測試設定檔](../../channels/using/event-transactional-messages.md#defining-a-test-profile-in-a-transactional-message)。

1. 按一下 **[!UICONTROL Save & close]** 以儲存您的內容。
1. 發佈交易式訊息。請參閱[發佈交易式訊息](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message)。

### 步驟 2：建立和設定服務 {#step-2--create-and-configure-the-service-1}

1. 從進階功能表 **Profiles &amp; audiences** > **Services**，透過 Adobe Campaign 標誌來建立服務。
1. 移至 **[!UICONTROL Service properties]** 區段，可透過服務控制面板的 ![](assets/edit_darkgrey-24px.png) 按鈕進行存取。
1. 填寫 **[!UICONTROL Service label]** 欄位。

   ![](assets/confirmation_service-label.png)

   >[!NOTE]
   >
   >您必須填寫此欄位，才能啟用交易式訊息的調解。

1. 在 **[!UICONTROL Confirmation messages]** 區段中，選取 **[!UICONTROL Custom message]**：此模式可讓您為訂閱服務的設定式參考特定的確認訊息。
1. 選取與您建立之交易式訊息相關聯的 **[!UICONTROL Custom subscription event configuration]**。

   ![](assets/confirmation_service-confirmation-message.png)

1. 按一下 **[!UICONTROL Confirm]** 並儲存服務。

現在，每次設定檔訂閱此服務時，他都會收到您所定義的交易式訊息，並有對應至所選服務的個人化欄位。

>[!NOTE]
>
>訊息只會在使用者第一次訂閱時傳送。

## 從登錄頁面設定確認訊息 {#configuring-confirmation-message-from-landing-page}

您也可以使用登錄頁面 **[!UICONTROL Job]** 區段的 **[!UICONTROL Start sending messages]** 選項，從訂閱登錄頁面參考確認訊息。

當從登錄頁面參考確認訊息時，每次提交登錄頁面時都會傳送訊息（即使已訂閱設定檔亦然）。

### 步驟 1：建立確認電子郵件 {#step-1--create-the-confirmation-email-2}

系統會透過登錄頁面，自動傳送確認電子郵件給訂閱電子報的每個個人檔案。會將訂閱視為事件，而電子郵件則是[交易式訊息](../../channels/using/about-transactional-messaging.md)，會將目標設為訂閱服務的每個設定檔。

建立這些元素的步驟如下所述。由於登錄頁面會參考交易式訊息，因此您需要先建立它。

#### 建立事件 {#create-the-event-2}

確認電子郵件是一則[交易式訊息](../../channels/using/about-transactional-messaging.md)，當它回應事件時：訂閱服務。此訊息將會傳送以確認訂閱您的電子報。

1. 從 **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Event configuration]** 功能表建立事件，可從 Adobe Campaign 標誌存取。
1. 輸入標籤，選取目標維度，然後按一下 **[!UICONTROL Create]**。

   設定步驟將顯示在[設定交易式訊息傳送](../../administration/using/configuring-transactional-messaging.md)區段。

1. 在 **[!UICONTROL Fields]** 區段中，按一下 **[!UICONTROL Create element]** 並將 **[!UICONTROL serviceName]** 新增至資料結構以啟用調解。

   ![](assets/confirmation_serviceName-field.png)

   >[!NOTE]
   >
   >**[!UICONTROL serviceName]** 欄位為必填欄位。如果您未將其新增至事件資料結構，Adobe Campaign 將無法與訂閱服務進行調解。

1. 在 **[!UICONTROL Enrichment]** 區段中，按一下 **[!UICONTROL Create element]** 並選取 **[!UICONTROL Service]** 目標資源。
1. 在 **[!UICONTROL Join definition]** 區段中，將 **[!UICONTROL Service]** 資源的 **[!UICONTROL serviceName]** 欄位與事件設定的 **[!UICONTROL name]** 欄位相對應。

   ![](assets/confirmation_serviceName-join.png)

   >[!NOTE]
   >
   >這可讓您使用交易式訊息中 [!UICONTROL Service] 資源的個人化欄位。

#### 設計確認訊息 {#design-the-confirmation-message-2}

[本區段](#design-the-confirmation-message-1)將介紹設計交易式訊息的步驟。

### 步驟 2：建立和設定服務 {#step-2--create-and-configure-the-service-2}

1. 從進階功能表 **[!UICONTROL Profiles & audiences]** > **[!UICONTROL Services]** 透過 Adobe Campaign 標誌建立服務。
1. 移至 **[!UICONTROL Service properties]** 區段，可透過服務控制面板的 ![](assets/edit_darkgrey-24px.png) 按鈕進行存取。
1. 填寫 **[!UICONTROL Service label]** 欄位。此標籤將顯示在確認訊息和訂閱登錄頁面中。
1. 按一下 **[!UICONTROL Confirm]** 並儲存服務。

### 步驟 3：建立並設定著陸頁面 {#step-3--create-and-configure-the-landing-page}

建立將發佈在您網站上的訂閱登錄頁面。

若要建立和設定此登錄頁面，請遵循下列步驟：

1. 根據 **[!UICONTROL Subscription]** 範本，設計[新登錄頁面](../../channels/using/getting-started-with-landing-pages.md)。
1. 編輯登錄頁面屬性。在 **[!UICONTROL Job]** > **[!UICONTROL Specific actions]** 區段中，選取 **[!UICONTROL Specific service]** 選項並從下拉式清單中選取您剛建立的服務。

   ![](assets/confirmation_lp-specific-service.png)

1. 選取 **[!UICONTROL Start sending message]** 選項，然後從下拉清單中選取剛建立的交易式訊息。

   ![](assets/confirmation_lp-start-sending-message.png)

1. 自訂登錄頁面的內容。

1. [測試和發佈](../../channels/using/testing-publishing-landing-page.md)登錄頁面

現在，每次設定檔透過提交登錄頁面來訂閱此服務時，他都會收到您所定義的交易式訊息，並有對應至所選服務的個人化欄位。

>[!NOTE]
>
>每次提交登錄頁面時都會傳送訊息（即使已訂閱設定檔亦然）。
