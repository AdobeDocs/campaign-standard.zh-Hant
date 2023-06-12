---
title: 交易式訊息限制
description: 瞭解Adobe Campaign Standard中有關交易式訊息的主要建議和限制。
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
feature: Transactional Messaging
role: User
level: Intermediate
exl-id: d6aaec6e-c718-46a2-88e8-7402970def1a
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '742'
ht-degree: 67%

---

# 異動訊息最佳作法和限制 {#transactional-messaging-limitations}

<img src="assets/do-not-localize/icon_concepts.svg" width="60px">

本節列出開始建立交易式訊息之前，您應注意的最佳實務和限制。

<!--For more on transactional messages, including on how to configure and create them, see [Getting started with transactional messaging](../../channels/using/getting-started-with-transactional-msg.md).-->

## 權限 {#permissions}

僅限具有下列專案的使用者： [管理](../../administration/using/users-management.md#functional-administrators) 角色可以設定交易式事件並存取交易式訊息。

## 事件設定和發佈 {#design-and-publication}

當您設定和發佈交易式事件時，您需要執行的某些步驟無法還原。 您必須注意下列限制：

* 異動訊息傳送的可用管道包括： **[!UICONTROL Email]**， **[!UICONTROL Mobile (SMS)]** 和 **[!UICONTROL Push notification]**.
* 每個事件設定只能使用一個通道。請參閱[建立事件](../../channels/using/configuring-transactional-event.md#creating-an-event)。
* 事件建立後，便無法變更通道。因此，如果訊息未成功傳送，您需要設計機制，允許使用工作流程從其他通道傳送訊息。請參閱[工作流程資料和程序](../../automating/using/get-started-workflows.md)。
* 在事件建立後，您無法變更目標維度 **[!UICONTROL Real-time event]** 或 **[!UICONTROL Profile]** ）。請參閱[建立事件](../../channels/using/configuring-transactional-event.md#creating-an-event)。
* 無法回滾發佈，但可以取消發佈事件：此操作使事件和關聯的交易式訊息無法存取。請參閱[取消發佈事件](../../channels/using/publishing-transactional-event.md#unpublishing-an-event)。
* 唯一可與事件關聯的交易式訊息是發佈該事件時自動建立的訊息。請參閱[預覽和發佈事件](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event)。

## 異動訊息的數量 {#transactional-message-number}

已發佈的交易式訊息數量可能會對您的平台產生重大影響。 為獲得最佳效能，已發佈的異動訊息數應維持在100以下。 為確保此，請取消發佈或刪除任何未使用的交易式訊息。 另請參閱 [取消發佈交易式訊息](../../channels/using/publishing-transactional-message.md#unpublishing-a-transactional-message) 和 [刪除交易式訊息](../../channels/using/publishing-transactional-message.md#deleting-a-transactional-message).

為確保最佳效能，您也可以取消發佈或刪除未使用的事件。 事實上，取消發佈或刪除事件也會取消發佈或刪除對應的交易式訊息，以及其傳送和追蹤記錄（如有）。 另請參閱 [取消發佈事件](../../channels/using/publishing-transactional-event.md#unpublishing-an-event) 和 [刪除事件](../../channels/using/publishing-transactional-event.md#deleting-an-event).

## 個人化 {#personalization}

您個人化訊息內容的方式取決於交易式訊息的類型。具體情況列於下方。

### 事件型交易式訊息

* 個人化資訊來自事件本身所包含的資料。另請參閱 [事件型交易式訊息設定](../../channels/using/configuring-transactional-event.md#event-based-transactional-messages).
* 您 **無法** use **[!UICONTROL Unsubscription link]** 事件交易式訊息中的內容區塊。
* 事件型交易式訊息應僅使用傳送事件中的資料來定義收件者和訊息內容個人化。不過，您可以使用 Adobe Campaign 資料庫的資訊，豐富您交易式訊息的內容。另請參閱 [豐富化事件](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content) 和 [個人化交易式訊息](../../channels/using/editing-transactional-message.md#personalizing-a-transactional-message).
* 由於事件交易式訊息不包含配置設定檔資訊，因此它們與疲勞規則不相容，即使在擴充設定檔案的情況下也是如此。

### 設定檔交易式訊息

* 個人化資訊可來自事件中包含的資料，或來自已調解的設定檔記錄。另請參閱 [設定檔交易式訊息設定](../../channels/using/configuring-transactional-event.md#profile-based-transactional-messages) 和 [設定檔交易式訊息特性](../../channels/using/editing-transactional-message.md#profile-transactional-message-specificities).
* 您 **可以** use **[!UICONTROL Unsubscription link]** 設定檔交易式訊息中的內容區塊。 請參閱[新增內容區塊](../../designing/using/personalization.md#adding-a-content-block)。
* 疲勞規則與設定檔交易式訊息相容。請參閱[疲勞規則](../../sending/using/fatigue-rules.md)。

### 產品清單

請注意，產品清單可在交易中使用 **電子郵件訊息** 僅限。 請參閱[在交易式訊息中使用產品清單](../../designing/using/using-product-listings.md)。

## 品牌 {#permissions-and-branding}

在 [品牌](../../administration/using/branding.md) 管理方面，交易式訊息提供的彈性比標準訊息要小。Adobe 建議將交易式訊息中使用的所有品牌連結至 **[!UICONTROL All]** [組織單位](../../administration/using/organizational-units.md)。如需詳細資訊，請閱讀以下詳細說明。

編輯交易式訊息時，您可以將訊息連結至品牌，以自動套用一些參數，例如品牌名稱或品牌標誌。預設情況下，在交易式訊息屬性中將選中 **[!UICONTROL Default brand]**。

![](assets/message-center_branding.png)

交易式訊息使用的所有對象（包括品牌）都必須從 **[!UICONTROL Message Center]** 組織單位中可見，這表示這些對象必須位於 **[!UICONTROL Message Center]** 或 **[!UICONTROL All]** 組織單位中。

但是，如果訊息屬性中選取的品牌連結到與 **[!UICONTROL Message Center]** 或 **[!UICONTROL All]**&#x200B;不同的組織單位，則會導致錯誤，您將無法發送交易式訊息。

因此，如果您想在交易式訊息中使用多品牌，您應將所有品牌連結至 **[!UICONTROL Message Center]** 組織單位或 **[!UICONTROL All]** 組織單位。

## 匯出和匯入交易式訊息 {#exporting-and-importing-transactional-messages}

* 要匯出交易式訊息，在[建立封包匯出](../../automating/using/managing-packages.md#creating-a-package)時需要包含相應的事件配置。
* 透過封包[匯入交易式訊息後](../../automating/using/managing-packages.md#importing-a-package)，交易式訊息清單中不會顯示該訊息。您需要[發佈事件設定](../../channels/using/publishing-transactional-event.md)，才能使關聯的交易式訊息可用。
