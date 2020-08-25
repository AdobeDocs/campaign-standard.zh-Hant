---
title: 交易式訊息限制
description: 瞭解Adobe Campaign Standard中有關交易訊息的主要限制和建議。
page-status-flag: never-activated
uuid: b316bf47-7d98-46fa-ab4f-67ff50de8095
contentOwner: lemaitre
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: landing-pages
discoiquuid: ca8d1698-6e8a-4f5a-b017-74a152e14286
context-tags: landingPage,wizard;landingPage,overview;landingPage,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0b6607afe05e762c87a95fd88bda0196baa57f1e
workflow-type: tm+mt
source-wordcount: '640'
ht-degree: 87%

---


# 交易式訊息限制 {#transactional-messaging-limitations}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_concepts.svg" width="60px"></td>
<td><p>以下部分列出了在開始建立事務性消息之前應注意的限制。</p></td>
</tr>
</table>

有關事務性消息的詳細資訊，包括如何配置和建立這些消息，請參 [閱事務性消息入門](../../channels/using/getting-started-with-transactional-msg.md)。

>[!NOTE]
>
>若要存取交易式訊息，您必須具有管理權限。

## 設計與發佈 {#design-and-publication}

在設計和發佈交易式訊息時，您需要執行的某些步驟無法還原。您必須注意下列限制：

* 每個事件設定只能使用一個通道。請參閱[建立事件](../../administration/using/configuring-transactional-messaging.md#creating-an-event)。
* 事件建立後，便無法變更通道。因此，如果訊息未成功傳送，您需要設計機制，允許使用工作流程從其他通道傳送訊息。請參閱[工作流程資料和程序](../../automating/using/get-started-workflows.md)。
* 在事件建立後，您無法變更目標維度 **[!UICONTROL Real-time event]** 或 **[!UICONTROL Profile]** ）。請參閱[建立事件](../../administration/using/configuring-transactional-messaging.md#creating-an-event)。
* 無法回滾發佈，但可以取消發佈事件：此操作使事件和關聯的交易式訊息無法存取。請參閱[取消發佈事件](../../administration/using/configuring-transactional-messaging.md#unpublishing-an-event)。
* 唯一可與事件關聯的交易式訊息是發佈該事件時自動建立的訊息。請參閱[預覽和發佈事件](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)。

## 個人化{#personalization}

您個人化訊息內容的方式取決於交易式訊息的類型。具體情況列於下方。

### 事件型交易訊息

* 個人化資訊來自事件本身所包含的資料。請參閱[事件交易式訊息](../../channels/using/event-transactional-messages.md)。
* You **cannot** use **[!UICONTROL Unsubscription link]** content blocks in an event transactional message.
* 事件型交易式訊息應僅使用傳送事件中的資料來定義收件者和訊息內容個人化。不過，您可以使用 Adobe Campaign 資料庫的資訊，豐富您交易式訊息的內容。請參閱 [豐富交易式訊息內容](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content)。
* 由於事件交易式訊息不包含配置設定檔資訊，因此它們與疲勞規則不相容，即使在擴充設定檔案的情況下也是如此。請參閱[疲勞規則](../../sending/using/fatigue-rules.md)。

### 基於配置檔案的事務性消息

* 個人化資訊可來自事件中包含的資料，或來自已調解的設定檔記錄。請參閱[設定檔交易式訊息](../../channels/using/profile-transactional-messages.md)。
* You **can** use **[!UICONTROL Unsubscription link]** content blocks in a profile transactional message. 請參閱[新增內容區塊](../../designing/using/personalization.md#adding-a-content-block)。
* 疲勞規則與設定檔交易式訊息相容。請參閱[疲勞規則](../../sending/using/fatigue-rules.md)。

請注意，產品清單僅適用於交易電子郵件訊息。請參閱[在交易式訊息中使用產品清單](../../channels/using/event-transactional-messages.md#using-product-listings-in-a-transactional-message)。

## 權限與品牌化 {#permissions-and-branding}

在 [品牌](../../administration/using/branding.md) 管理方面，交易式訊息提供的彈性比標準訊息要小。Adobe 建議將交易式訊息中使用的所有品牌連結至 **[!UICONTROL All]** [組織單位](../../administration/using/organizational-units.md)。如需詳細資訊，請閱讀以下詳細說明。

編輯交易式訊息時，您可以將訊息連結至品牌，以自動套用一些參數，例如品牌名稱或品牌標誌。預設情況下，在交易式訊息屬性中將選中 **[!UICONTROL Default brand]**。

![](assets/message-center_branding.png)

交易式訊息使用的所有對象（包括品牌）都必須從 **[!UICONTROL Message Center]** 組織單位中可見，這表示這些對象必須位於 **[!UICONTROL Message Center]** 或 **[!UICONTROL All]** 組織單位中。

但是，如果訊息屬性中選取的品牌連結到與 **[!UICONTROL Message Center]** 或 **[!UICONTROL All]**&#x200B;不同的組織單位，則會導致錯誤，您將無法發送交易式訊息。

因此，如果您想在交易式訊息中使用多品牌，您應將所有品牌連結至 **[!UICONTROL Message Center]** 組織單位或 **[!UICONTROL All]** 組織單位。

## 匯出和匯入交易式訊息 {#exporting-and-importing-transactional-messages}

* 要匯出交易式訊息，在[建立封包匯出](../../automating/using/managing-packages.md#creating-a-package)時需要包含相應的事件配置。
* 透過封包[匯入交易式訊息後](../../automating/using/managing-packages.md#importing-a-package)，交易式訊息清單中不會顯示該訊息。您需要[發佈事件設定](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)，才能使關聯的交易式訊息可用。
