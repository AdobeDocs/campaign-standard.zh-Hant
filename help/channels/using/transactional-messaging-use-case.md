---
solution: Campaign Standard
product: campaign
title: 異動訊息使用案例
description: 探索Adobe Campaign交易式訊息功能的端對端範例。
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
feature: 異動訊息傳送
role: User
level: Intermediate
exl-id: ee1a9705-4c21-4d46-a178-fde2e059f443
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '506'
ht-degree: 4%

---

# 異動訊息使用案例 {#transactional-messaging-use-case}

在此範例中，您想要使用Adobe Campaign交易訊息功能，在您網站上的每次購買後傳送確認電子郵件，透過客戶CRM ID識別客戶。

先決條件如下：

* 請確定&#x200B;**[!UICONTROL Profile]**&#x200B;資源已擴充，並有與CRM ID對應的新欄位。

* 建立並發佈與購買對應的自訂資源，並將其連結至&#x200B;**[!UICONTROL Profile]**&#x200B;資源。 這樣，您將能夠從此資源中擷取資訊，以豐富訊息內容。

有關擴展、建立和發佈資源的詳細資訊，請參閱[此部分](../../developing/using/key-steps-to-add-a-resource.md)。

實作此使用案例的主要步驟如下。

>[!NOTE]
>
>有關交易式消息傳送一般進程的圖形表示，請參見[此架構](../../channels/using/getting-started-with-transactional-msg.md#key-steps)。

## 步驟1 — 建立並發佈事件設定 {#create-event-configuration}

1. 使用&#x200B;**[!UICONTROL Email]**&#x200B;通道建立新事件。 請參閱[建立事件](../../channels/using/configuring-transactional-event.md#creating-an-event)。

1. 選取&#x200B;**[!UICONTROL Profile]**&#x200B;目標維度以建立[設定檔交易式訊息](../../channels/using/configuring-transactional-event.md#profile-based-transactional-messages)。

1. 定義將可用於個人化交易式訊息的屬性。 在此範例中，新增「CRM ID」和「產品識別碼」欄位。 請參閱[定義事件屬性](../../channels/using/configuring-transactional-event.md#defining-the-event-attributes)。

   ![](assets/message-center_usecase1.png)

1. 若要以客戶購買的相關資訊擴充訊息內容，請建立以&#x200B;**[!UICONTROL Purchase]**&#x200B;資源為目標的擴充。 請參閱[豐富事件](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content)。

   ![](assets/message-center_usecase2.png)

1. 在先前已新增至事件的「產品識別碼」欄位與&#x200B;**[!UICONTROL Purchase]**&#x200B;資源的對應欄位之間建立連結條件。

   ![](assets/message-center_usecase3.png)

1. 因為這對於設定檔事件是必要項目，您也必須建立以&#x200B;**[!UICONTROL Profile]**&#x200B;資源為目標的擴充。

1. 在先前已新增至訊息的「CRM ID」欄位與您延伸之&#x200B;**[!UICONTROL Profile]**&#x200B;資源的對應欄位之間建立連結條件。<!--What's the purpose to have created a CRM ID for this event and to have the CRM ID as a join condition? could it be any other field provided you created it in the event?-->

   ![](assets/message-center_usecase4.png)

1. 在&#x200B;**[!UICONTROL Targeting enrichment]**&#x200B;區段中，選取&#x200B;**[!UICONTROL Profile]**&#x200B;資源的擴充，該資源將在傳送執行期間用作訊息目標。

   ![](assets/message-center_usecase5.png)

1. 預覽並發佈事件。 請參閱[預覽和發佈事件](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event)。

## 步驟2 — 編輯和發佈交易式訊息 {#create-transactional-message}

1. 前往發佈事件時自動建立的交易式訊息。 請參閱[存取交易式訊息](../../channels/using/editing-transactional-message.md#accessing-transactional-messages)。

1. 編輯訊息並加以個人化。 請參閱[編輯設定檔交易式訊息](../../channels/using/editing-transactional-message.md#editing-profile-transactional-message)。

1. 透過與您新增至&#x200B;**[!UICONTROL Profile]**&#x200B;資源的「CRM ID」欄位調解，您可以直接存取[個人化](../../designing/using/personalization.md#inserting-a-personalization-field)訊息的所有設定檔資訊。

   ![](assets/message-center_usecase6.png)

1. 透過與「產品識別碼」欄位調解，您可以透過從&#x200B;**[!UICONTROL Purchase]**&#x200B;資源新增任何欄位，以客戶購買的相關資訊豐富訊息內容。

   ![](assets/message-center_usecase7.png)

   要執行此操作，請從內容工具列選取&#x200B;**[!UICONTROL Insert personalization field]**。 從&#x200B;**[!UICONTROL Context]** > **[!UICONTROL Transactional event]** > **[!UICONTROL Event context]**&#x200B;節點中，開啟與&#x200B;**[!UICONTROL Purchase]**&#x200B;自訂資源對應的節點，然後選取任何欄位。

1. 您可以使用特定測試設定檔來測試訊息。 請參閱[測試交易式訊息](../../channels/using/testing-transactional-message.md#testing-a-transactional-message)。

1. 內容準備就緒後，請儲存變更並發佈訊息。 請參閱[發佈交易式訊息](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message)。

## 步驟3 — 整合事件觸發 {#integrate-event-trigger}

將事件整合至您的網站。 請參閱[整合事件觸發](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger)。

## 步驟4 — 訊息傳送 {#message-delivery}

執行完所有這些步驟後，當客戶從您的網站購買產品時，他們會收到個人化確認電子郵件，包括其購買的資訊。
