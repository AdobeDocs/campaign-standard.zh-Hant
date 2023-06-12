---
title: 異動訊息使用案例
description: 探索Adobe Campaign交易式訊息功能的端對端範例。
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
feature: Transactional Messaging
role: User
level: Intermediate
exl-id: ee1a9705-4c21-4d46-a178-fde2e059f443
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '504'
ht-degree: 4%

---

# 異動訊息使用案例 {#transactional-messaging-use-case}

在此範例中，您想要使用Adobe Campaign交易式訊息功能，在網站上每次購買後傳送確認電子郵件，透過其CRM ID識別客戶。

先決條件如下：

* 請確定 **[!UICONTROL Profile]** 資源已擴充為與CRM ID對應的新欄位。

* 建立並發佈與購買對應的自訂資源，並將其連結至 **[!UICONTROL Profile]** 資源。 如此一來，您將能夠從此資源擷取資訊，以豐富訊息內容。

如需擴充、建立和發佈資源的詳細資訊，請參閱 [本節](../../developing/using/key-steps-to-add-a-resource.md).

實施此使用案例的主要步驟如下所示。

>[!NOTE]
>
>如需交易式訊息一般程式的圖形表示，請參閱 [此結構描述](../../channels/using/getting-started-with-transactional-msg.md#key-steps).

## 步驟1 — 建立並發佈事件設定 {#create-event-configuration}

1. 使用建立新事件 **[!UICONTROL Email]** 頻道。 請參閱[建立事件](../../channels/using/configuring-transactional-event.md#creating-an-event)。

1. 選取 **[!UICONTROL Profile]** 目標維度，以建立 [設定檔交易式訊息](../../channels/using/configuring-transactional-event.md#profile-based-transactional-messages).

1. 定義可用於個人化交易式訊息的屬性。 在此範例中，新增「CRM ID」和「產品識別碼」欄位。 另請參閱 [定義事件屬性](../../channels/using/configuring-transactional-event.md#defining-the-event-attributes).

   ![](assets/message-center_usecase1.png)

1. 若要使用客戶購買的相關資訊來擴充訊息內容，請建立目標定位的擴充 **[!UICONTROL Purchase]** 資源。 另請參閱 [豐富化事件](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content).

   ![](assets/message-center_usecase2.png)

1. 在先前新增至事件的「產品識別碼」欄位與來自的對應欄位之間建立連線條件 **[!UICONTROL Purchase]** 資源。

   ![](assets/message-center_usecase3.png)

1. 由於此為設定檔型事件的強制專案，因此您也必須建立目標定位於 **[!UICONTROL Profile]** 資源。

1. 在先前新增至訊息的「CRM ID」欄位與來自的對應欄位之間建立加入條件 **[!UICONTROL Profile]** 您已擴充的資源。 <!--What's the purpose to have created a CRM ID for this event and to have the CRM ID as a join condition? could it be any other field provided you created it in the event?-->

   ![](assets/message-center_usecase4.png)

1. 在 **[!UICONTROL Targeting enrichment]** 區段，選取擴充於 **[!UICONTROL Profile]** 資源，在傳遞執行期間將用作訊息目標。

   ![](assets/message-center_usecase5.png)

1. 預覽和發佈事件。 請參閱[預覽和發佈事件](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event)。

## 步驟2 — 編輯並發佈交易式訊息 {#create-transactional-message}

1. 前往發佈事件時自動建立的交易式訊息。 另請參閱 [存取交易式訊息](../../channels/using/editing-transactional-message.md#accessing-transactional-messages).

1. 編輯並個人化訊息。 另請參閱 [編輯設定檔交易式訊息](../../channels/using/editing-transactional-message.md#editing-profile-transactional-message).

1. 透過與您新增至的「CRM ID」欄位進行調解 **[!UICONTROL Profile]** 資源，您可以直接存取所有設定檔資訊至 [個人化](../../designing/using/personalization.md#inserting-a-personalization-field) 您的訊息。

   ![](assets/message-center_usecase6.png)

1. 透過與「產品識別碼」欄位進行調解，您可以從新增任何欄位，擴充訊息內容與客戶購買相關的資訊。 **[!UICONTROL Purchase]** 資源。

   ![](assets/message-center_usecase7.png)

   要執行此操作，請選取 **[!UICONTROL Insert personalization field]** 從內容工具列。 從 **[!UICONTROL Context]** > **[!UICONTROL Transactional event]** > **[!UICONTROL Event context]** 節點，開啟與 **[!UICONTROL Purchase]** 自訂資源並選取任何欄位。

1. 您可以使用特定的測試設定檔測試訊息。 另請參閱 [測試交易式訊息](../../channels/using/testing-transactional-message.md#testing-a-transactional-message).

1. 內容準備就緒後，請儲存變更並發佈訊息。 請參閱[發佈交易式訊息](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message)。

## 步驟3 — 整合事件觸發 {#integrate-event-trigger}

將事件整合至您的網站。 另請參閱 [整合事件觸發](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger).

## 步驟4 — 訊息傳送 {#message-delivery}

執行完所有這些步驟後，當客戶從您的網站購買產品時，就會收到包含購買資訊的個人化確認電子郵件。
