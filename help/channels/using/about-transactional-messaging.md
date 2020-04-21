---
title: 關於交易式訊息傳遞
description: 探索您可傳送的不同交易訊息類型，以及這些訊息在Adobe Campaign中的使用方式。
page-status-flag: never-activated
uuid: 8470e9e2-ee17-456f-9e4c-460e69c78a2c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: transactional-messaging
discoiquuid: 71a4d5d5-fe2a-4ce5-b22b-a4736f7add83
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 72366d56e21933bcd79e907e5f8d5a9ad5281725

---


# 關於交易式訊息傳遞{#about-transactional-messaging}

您可以在Adobe Campaign中建立和管理個人化的交易訊息。

事務性消息是由諸如網站的提供商發送給用戶的個人和唯一通信。

* 此類型的訊息尤其值得期待，因為它包含收件者要檢查或確認的資訊。 例如，建立帳戶後，可能是歡迎訊息，或確認訂單已出貨、帳單或確認密碼變更的訊息。
* 它是定義客戶端關係的重要消息：使用者預期會即時傳送。 因此，觸發的事件和到達的消息之間的延遲必須非常短。
* 事務性消息通常具有高開放率。

Adobe Campaign可讓您將這項功能與資訊系統整合，資訊系統會將要轉換為自訂交易訊息的事件傳送給系統。

>[!NOTE]
>
>交易式訊息可透過電子郵件、簡訊或推播通知傳送，視您的選項而定。 請檢查您的授權合約。

Adobe Campaign提供兩種交易訊息：

* [事件交易訊息](../../channels/using/event-transactional-messages.md) ，以事件為目標。 事件本身包含的資料可用來定義傳送目標。
* [從Adobe Campaign行銷資料庫](../../channels/using/profile-transactional-messages.md) ，設定以個人檔案為目標的交易訊息。 您可以使用Adobe Campaign資料庫中的資訊，根據客戶行銷個人檔案傳送交易訊息。

在配置將轉換為事務性消息的事件時定義消息類型。 請參 [閱事務性消息配置](../../administration/using/configuring-transactional-messaging.md)。

>[!NOTE]
>
>Adobe Campaign會優先處理交易訊息，而非其他傳送。

Adobe Campaign Standard API也提供交易式訊息。 如需詳細資訊，請參閱專用 [檔案](../../api/using/managing-transactional-messages.md)。

>[!IMPORTANT]
>
>現在，所有交易訊息都會與Adobe Campaign Enhanced MTA一起傳送，以改善傳遞能力、總處理能力和彈回數處理。 所有影響與標準行銷訊息的影響相同。

## 事務性消息傳遞操作原則 {#transactional-messaging-operating-principle}

讓我們舉一個有網站的公司為例，其使用者可在此網站上購買產品。

Adobe Campaign可讓您傳送通知電子郵件給已將產品新增至購物車的網站使用者：當其中一人離開網站而未完成購買時，就會自動傳送購物車放棄電子郵件給他們。

將其放置到位的步驟如下：

1. 設定將命名為「購物車放棄」的事件，並發佈此事件設定，以自動建立交易訊息。 「設定事件以傳送事件交易訊 [息」區段中會顯示建立和發佈事件](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message) 。
1. 交易訊息必須個人化、測試，然後發佈。 See [Event transactional messages](../../channels/using/event-transactional-messages.md).
1. 此外，若要在客戶放棄購物車時觸發事件，必須使用Adobe Campaign Standard REST API從公司網站傳送此事件。 請參閱 [網站整合](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)。

執行完所有這些步驟後，當使用者離開網站而未在購物車中訂購產品時，他們會自動收到通知電子郵件。

## 交易式訊息發佈程式 {#transactional-messaging-pub-process}

下圖說明了事務性消息傳遞發佈過程。

![](assets/message-center_pub-process.png)

有關事件配置步驟的詳細資訊，請參 [閱事務性消息配置](../../administration/using/configuring-transactional-messaging.md)。

## 交易式訊息限制 {#transactional-messaging-limitations}

>[!NOTE]
>
>要訪問事務性消息，您必須具有管理權限。

### 設計與出版 {#design-and-publication}

在設計和發佈事務性消息時，您需要執行的某些步驟無法還原。 您必須注意下列限制：

* 每個事件設定只能使用一個頻道。 請參 [閱建立事件](../../administration/using/configuring-transactional-messaging.md#creating-an-event)。
* 事件建立後，便無法變更渠道。 因此，如果訊息未成功傳送，您需要設計機制，允許使用工作流程從其他管道傳送訊息。 See [Workflow data and processes](../../automating/using/workflow-data-and-processes.md).
* 在事件建立後，您無 **[!UICONTROL Real-time event]** 法變 **[!UICONTROL Profile]** 更定位維度（或）。 請參 [閱建立事件](../../administration/using/configuring-transactional-messaging.md#creating-an-event)。
* 無法回滾發佈，但可以取消發佈事件：此操作使事件和關聯的事務性消息無法訪問。 請參 [閱取消發佈事件](../../administration/using/configuring-transactional-messaging.md#unpublishing-an-event)。
* 唯一可與事件關聯的交易訊息是發佈該事件時自動建立的訊息。 請參 [閱預覽和發佈事件](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)。

### 個人化 {#personalization}

您個人化訊息內容的方式取決於交易訊息的類型。 具體情況列於下列：

**事件型交易訊息**:

* 個人化資訊來自事件本身所包含的資料。 See [Event transactional messages](../../channels/using/event-transactional-messages.md).
* 在事件事務 **性訊息中** ，您無法使用取消訂閱連結內容區塊。
* 事件型交易訊息應僅使用傳送事件中的資料來定義收件者和訊息內容個人化。 不過，您可以使用Adobe Campaign資料庫的資訊，豐富您交易訊息的內容。 請參 [閱豐富交易式訊息內容](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content)。
* 由於事件事務性消息不包含配置檔案資訊，因此它們與疲勞規則不相容，即使在富集配置檔案的情況下也是如此。 請參 [閱疲勞規則](../../sending/using/fatigue-rules.md)。

**基於概要的事務性消息**:

* 個人化資訊可來自事件中包含的資料，或來自已調節的描述檔記錄。 See [Profile transactional messages](../../channels/using/profile-transactional-messages.md).
* 您可以在描述檔 **交易訊息中** ，使用取消訂閱連結內容區塊。 請參 [閱新增內容區塊](../../designing/using/personalization.md#adding-a-content-block)。
* 疲勞規則與描述檔交易訊息相容。 請參 [閱疲勞規則](../../sending/using/fatigue-rules.md)。

請注意，產品清單僅適用於交易電子郵件訊息。 請參 [閱在交易訊息中使用產品清單](../../channels/using/event-transactional-messages.md#using-product-listings-in-a-transactional-message)。

### 權限與品牌 {#permissions-and-branding}

在品牌管理方面 [](../../administration/using/branding.md) ，交易式訊息提供的彈性比標準訊息要小。 Adobe建議將交易訊息中使用的所有品牌連結至 **[!UICONTROL All]** 組織 [單位](../../administration/using/organizational-units.md)。 如需詳細資訊，請閱讀以下詳細說明。

編輯交易訊息時，您可以將訊息連結至品牌，以自動套用一些參數，例如品牌名稱或品牌標誌。 預設 **[!UICONTROL Default brand]** 情況下，在事務性消息屬性中將選中。

![](assets/message-center_branding.png)

事務性消息中使用的所有對象（包括品牌）都必須從組織單位中可見，這表 **[!UICONTROL Message Center]** 示這些對象必須位於 **[!UICONTROL Message Center]** 或組 **[!UICONTROL All]** 織單位中。

但是，如果消息屬性中選擇的品牌連結到與或不同的組織單位 **[!UICONTROL Message Center]****[!UICONTROL All]**，則會導致錯誤，您將無法發送事務性消息。

因此，如果您想在交易訊息中使用多品牌，您應將所有品牌連結至組織單位或 **[!UICONTROL Message Center]** 組織單 **[!UICONTROL All]** 位。

### 導出和導入事務性消息 {#exporting-and-importing-transactional-messages}

* 要導出事務性消息，在建立包導出時需要包 [含相應的事件配置](../../automating/using/managing-packages.md#creating-a-package)。
* 通過包導入事務 [性消息後](../../automating/using/managing-packages.md#importing-a-package)，事務性消息清單中不顯示該消息。 您需要發 [布事件配置](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event) ，才能使關聯的事務性消息可用。

