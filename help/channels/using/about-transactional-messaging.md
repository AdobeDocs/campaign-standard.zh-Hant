---
title: 關於交易訊息
seo-title: 關於交易訊息
description: 關於交易訊息
seo-description: 探索您可以傳送的不同交易訊息類型，以及如何在Adobe Campaign中使用這些訊息。
page-status-flag: 從未啓動
uuid: 8470e9e-ee17-456f-9e4 c-460e69 c78 a2 c
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 頻道
content-type: reference
topic-tags: 交易訊息
discoiquuid: 71a4d5d5-fal2 a-4ce5-b22 b-a4736 f7 add83
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d93c2600299a8d2ec3672b3d82222f423878034c

---


# About transactional messaging{#about-transactional-messaging}

您可以在Adobe Campaign中建立及管理個人化交易訊息。

交易訊息是由供應商等供應商傳送給使用者的個人和獨特通訊。

* 此類型的訊息特別預期，因為它包含收件人想要檢查或確認的資訊。它可能是建立帳戶後的歡迎訊息，或是確認訂單已出貨、帳單或訊息確認密碼變更的確認訊息。
* 它是定義用戶端關係的重要訊息：使用者預期會即時傳送。觸發事件與到達訊息之間的延遲必須非常簡短。
* 交易訊息通常具有高開信率。

Adobe Campaign可讓您將此功能與傳送事件的資訊系統整合，以便將其轉換為自訂的交易訊息。

>[!NOTE]
>
>可透過電子郵件、SMS或推播通知傳送交易訊息，視您的選項而定。請檢查您的授權合約。

Adobe Campaign提供兩種交易訊息：

* [定位事件](../../channels/using/event-transactional-messages.md) 的事件交易訊息。事件本身中包含的資料可用來定義傳送目標。
* [描述檔交易訊息，](../../channels/using/profile-transactional-messages.md) 定位來自Adobe Campaign行銷資料庫的個人檔案。您可以使用Adobe Campaign資料庫中的資訊，根據客戶行銷設定檔傳送交易訊息。

設定要轉換為交易訊息的事件時，會定義訊息類型。See [Transactional messaging configuration](../../administration/using/configuring-transactional-messaging.md).

>[!NOTE]
>
>Adobe Campaign會排定處理交易訊息時的優先順序。

您也可以從Adobe Campaign Standard API取得交易訊息。For more on this, refer to the [dedicated documentation](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#about-transactional-messaging).

## Transactional messaging operating principle {#transactional-messaging-operating-principle}

假設有一家公司擁有網站，而這個網站上的使用者可以購買產品。

Adobe Campaign可讓您傳送通知電子郵件給已新增產品至購物車的網站使用者：當其中一位離開網站而未通過購買時，會自動寄送購物車寄送電子郵件給他們。

將此項目放入位置的步驟包括：

1. 設定名稱為「購物車放棄」並發佈此事件設定的事件，此事件會自動建立交易訊息。Creating and publishing an event are presented in the [Configuring an event to send an event transactional message](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message) section.
1. 交易訊息必須個人化、測試，然後再發佈。See [Event transactional messages](../../channels/using/event-transactional-messages.md).
1. 此外，為了在用戶端放棄購物車時觸發事件，此事件必須使用Adobe Campaign Standard REST API從公司的網站傳送。See [Site integration](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website).

完成上述所有步驟後，只要使用者未在購物車中訂購產品，就會自動收到通知電子郵件。

## Transactional messaging limitations {#transactional-messaging-limitations}

### Design and publication {#design-and-publication}

當您設計和發佈交易訊息時，無法回復某些您需要執行的步驟。您必須注意下列限制：

* 每個事件設定只能使用一個渠道。See [Creating an event](../../administration/using/configuring-transactional-messaging.md#creating-an-event).
* 一旦建立事件後，您就無法變更渠道。因此，如果訊息未成功傳送，您必須設計允許使用工作流程從其他頻道傳送的機制。See [Workflow data and processes](../../automating/using/workflow-data-and-processes.md).
* You cannot change the targeting dimension ( **[!UICONTROL Real-time event]** or **[!UICONTROL Profile]** ) after the event is created. See [Creating an event](../../administration/using/configuring-transactional-messaging.md#creating-an-event).
* 無法還原出版物，但您可以解除發佈事件：此操作可讓事件和相關交易訊息無法存取。See [Unpublishing an event](../../administration/using/configuring-transactional-messaging.md#unpublishing-an-event).
* 唯一可以與事件關聯的交易訊息是在發佈該事件時自動建立的訊息。See [Previewing and publishing the event](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event).

### Personalization {#personalization}

個人化訊息內容的方式，取決於交易訊息的類型。詳情列於下方：

**事件型交易訊息**：

* 個人化資訊來自事件本身所包含的資料。See [Event transactional messages](../../channels/using/event-transactional-messages.md).
* You cannot use **Unsubscription link** content blocks in an event transactional message.
* 事件型交易訊息只應使用傳送事件中的資料來定義收件者和訊息內容個人化。不過，您可以使用Adobe Campaign資料庫中的資訊豐富交易訊息的內容。See [Enriching the transactional message content](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content).
* 由於事件交易訊息不包含描述檔資訊，因此它們與疲勞規則不相容，即使在使用描述檔進行擴充時也不相容。See [Fatigue rules](../../administration/using/fatigue-rules.md).

**以個人檔案為基礎的交易訊息**：

* 個人化資訊可以來自事件中包含的資料或協調的描述檔記錄中。See [Profile transactional messages](../../channels/using/profile-transactional-messages.md).
* You can use **Unsubscription link** content blocks in a profile transactional message. See [Adding a content block](../../designing/using/adding-a-content-block.md).
* 疲勞規則與描述檔交易訊息相容。See [Fatigue rules](../../administration/using/fatigue-rules.md).

請注意，產品清單僅適用於交易式電子郵件訊息。See [Using product listings in a transactional message](../../channels/using/event-transactional-messages.md#using-product-listings-in-a-transactional-message).

### Permissions and branding {#permissions-and-branding}

When it comes to [branding](../../administration/using/branding.md) management, transactional messaging enables less flexibility than standard messaging. Adobe recommends linking all brands used in transactional messages to the **[!UICONTROL All]** organizational unit. 如需詳細資訊，請閱讀下列詳細說明。

編輯交易訊息時，您可以將其連結至品牌，以自動套用某些參數，例如品牌名稱或品牌標誌。The **[!UICONTROL Default brand]** is selected by default in the transactional message properties.

![](assets/message-center_branding.png)

To access the transactional messages, you must be part of the **[!UICONTROL Message Center agents]** (mcExec) security group, which is linked to the **[!UICONTROL Message Center]** [organizational unit](../../administration/using/organizational-units.md). Therefore, all objects (including branding) used in a transactional message must be visible from the **[!UICONTROL Message Center]** organizational unit, meaning that these objects must be in the **[!UICONTROL Message Center]** or **[!UICONTROL All]** organizational units.

However, if the brand selected in the message properties is linked to an organizational unit which is different from **[!UICONTROL Message Center]** or **[!UICONTROL All]**, this will cause an error and you will not be able to send the transactional message.

Therefore, if you want to use multi-branding in the context of transactional messaging, you should link all brands either to the **[!UICONTROL Message Center]** organizational unit or to the **[!UICONTROL All]** organizational unit.

### Exporting and importing transactional messages {#exporting-and-importing-transactional-messages}

* To export a transactional message, you need to include the corresponding event configuration when [creating the package export](../../automating/using/managing-packages.md#creating-a-package).
* Once the transactional message is [imported through a package](../../automating/using/managing-packages.md#importing-a-package), it is not displayed in the transactional message list. You need to [publish](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event) the event configuration in order to make the associated transactional message available.

