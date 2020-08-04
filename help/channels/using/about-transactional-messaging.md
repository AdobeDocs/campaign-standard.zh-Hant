---
title: 關於交易式訊息傳送
description: 探索您可傳送的不同交易式訊息類型，以及這些訊息在 Adobe Campaign 中的使用方式。
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
translation-type: ht
source-git-commit: 68e825bc3b6b7f94f61875e7da2bc8f63f06d9cb
workflow-type: ht
source-wordcount: '1147'
ht-degree: 100%

---


# 關於交易式訊息傳送{#about-transactional-messaging}

您可以在 Adobe Campaign 中建立和管理個人化的交易式訊息。

交易式訊息是由諸如網站的提供者傳送給使用者的個人和唯一通訊。

* 此類型的訊息尤其值得期待，因為它包含收件者要檢查或確認的資訊。例如，建立帳戶後，可能是歡迎訊息，或確認訂單已出貨、帳單或確認密碼變更的訊息。
* 它是定義客戶端關係的重要訊息：使用者預期會即時傳送。因此，觸發的事件和到達的訊息之間的延遲必須非常短。
* 交易式訊息通常具有高開放率。

Adobe Campaign 可讓您將這項功能與資訊系統整合，資訊系統會將要轉換為自訂交易式訊息的事件傳送給系統。

>[!NOTE]
>
>交易式訊息可透過電子郵件、簡訊或推播通知傳送，視您的選項而定。請檢查您的授權合約。

Adobe Campaign 提供兩種類型的交易式訊息：

* [事件交易式訊息](../../channels/using/event-transactional-messages.md)以事件為目標。事件本身包含的資料可用來定義傳送目標。
* [從 Adobe Campaign 行銷資料庫](../../channels/using/profile-transactional-messages.md)，設定以設定檔為目標的交易式訊息。您可以使用 Adobe Campaign 資料庫中的資訊，根據客戶行銷設定檔傳送交易式訊息。

在配置將轉換為交易式訊息的事件時定義訊息類型。請參閱[交易式訊息配置](../../administration/using/configuring-transactional-messaging.md)。

>[!NOTE]
>
>Adobe Campaign 會優先處理交易式訊息，而非其他傳送。

Adobe Campaign Standard API 也提供交易式訊息。如需詳細資訊，請參閱[詳細文件](../../api/using/managing-transactional-messages.md)。

>[!NOTE]
>
>現在，所有交易式訊息都會與 Adobe Campaign Enhanced MTA 一起傳送，以改善傳遞能力、總處理能力和彈回數處理。所有影響與標準行銷訊息的影響相同。如需詳細資訊，請參閱[本區段](../../administration/using/configuring-email-channel.md)。

## 交易式訊息傳遞操作原則 {#transactional-messaging-operating-principle}

讓我們舉一個有網站的公司為例，其使用者可在此網站上購買產品。

Adobe Campaign 可讓您傳送通知電子郵件給已將產品新增至購物車的網站使用者：當其中一人離開網站而未完成購買時，就會自動傳送購物車放棄電子郵件給他們。

設定步驟如下：

1. 設定將命名為「購物車放棄」的事件，並發佈此事件設定，以自動建立交易式訊息。在[設定事件以傳送事件交易式訊息](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message)區段中會顯示建立和發佈事件。
1. 交易式訊息必須經過個人化、測試，然後發佈。請參閱[事件交易式訊息](../../channels/using/event-transactional-messages.md)。
1. 此外，若要在客戶放棄購物車時觸發事件，必須使用 Adobe Campaign Standard REST API 從公司網站傳送此事件。請參閱[網站整合](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)。

執行完所有這些步驟後，當使用者離開網站而未在購物車中訂購產品時，他們會自動收到通知電子郵件。

## 交易式訊息發佈程序 {#transactional-messaging-pub-process}

下圖說明了交易式訊息發佈程序。

![](assets/message-center_pub-process.png)

有關事件配置步驟的詳細資訊，請參閱[交易式訊息設定](../../administration/using/configuring-transactional-messaging.md)。

## 交易式訊息限制 {#transactional-messaging-limitations}

>[!NOTE]
>
>若要存取交易式訊息，您必須具有管理權限。

### 設計與發佈 {#design-and-publication}

在設計和發佈交易式訊息時，您需要執行的某些步驟無法還原。您必須注意下列限制：

* 每個事件設定只能使用一個通道。請參閱[建立事件](../../administration/using/configuring-transactional-messaging.md#creating-an-event)。
* 事件建立後，便無法變更通道。因此，如果訊息未成功傳送，您需要設計機制，允許使用工作流程從其他通道傳送訊息。請參閱[工作流程資料和程序](../../automating/using/get-started-workflows.md)。
* 在事件建立後，您無法變更目標維度 **[!UICONTROL Real-time event]** 或 **[!UICONTROL Profile]** ）。請參閱[建立事件](../../administration/using/configuring-transactional-messaging.md#creating-an-event)。
* 無法回滾發佈，但可以取消發佈事件：此操作使事件和關聯的交易式訊息無法存取。請參閱[取消發佈事件](../../administration/using/configuring-transactional-messaging.md#unpublishing-an-event)。
* 唯一可與事件關聯的交易式訊息是發佈該事件時自動建立的訊息。請參閱[預覽和發佈事件](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)。

### 個人化{#personalization}

您個人化訊息內容的方式取決於交易式訊息的類型。具體情況列於下列：

**事件交易式訊息**：

* 個人化資訊來自事件本身所包含的資料。請參閱[事件交易式訊息](../../channels/using/event-transactional-messages.md)。
* 在事件交易式訊息中，您無法使用&#x200B;**取消訂閱連結**&#x200B;內容區塊。
* 事件型交易式訊息應僅使用傳送事件中的資料來定義收件者和訊息內容個人化。不過，您可以使用 Adobe Campaign 資料庫的資訊，豐富您交易式訊息的內容。請參閱 [豐富交易式訊息內容](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content)。
* 由於事件交易式訊息不包含配置設定檔資訊，因此它們與疲勞規則不相容，即使在擴充設定檔案的情況下也是如此。請參閱[疲勞規則](../../sending/using/fatigue-rules.md)。

**設定檔交易式訊息**：

* 個人化資訊可來自事件中包含的資料，或來自已調解的設定檔記錄。請參閱[設定檔交易式訊息](../../channels/using/profile-transactional-messages.md)。
* 您可以在設定檔交易式訊息中，使用&#x200B;**取消訂閱連結**&#x200B;內容區塊。請參閱[新增內容區塊](../../designing/using/personalization.md#adding-a-content-block)。
* 疲勞規則與設定檔交易式訊息相容。請參閱[疲勞規則](../../sending/using/fatigue-rules.md)。

請注意，產品清單僅適用於交易電子郵件訊息。請參閱[在交易式訊息中使用產品清單](../../channels/using/event-transactional-messages.md#using-product-listings-in-a-transactional-message)。

### 權限與品牌化 {#permissions-and-branding}

在 [品牌](../../administration/using/branding.md) 管理方面，交易式訊息提供的彈性比標準訊息要小。Adobe 建議將交易式訊息中使用的所有品牌連結至 **[!UICONTROL All]** [組織單位](../../administration/using/organizational-units.md)。如需詳細資訊，請閱讀以下詳細說明。

編輯交易式訊息時，您可以將訊息連結至品牌，以自動套用一些參數，例如品牌名稱或品牌標誌。預設情況下，在交易式訊息屬性中將選中 **[!UICONTROL Default brand]**。

![](assets/message-center_branding.png)

交易式訊息使用的所有對象（包括品牌）都必須從 **[!UICONTROL Message Center]** 組織單位中可見，這表示這些對象必須位於 **[!UICONTROL Message Center]** 或 **[!UICONTROL All]** 組織單位中。

但是，如果訊息屬性中選取的品牌連結到與 **[!UICONTROL Message Center]** 或 **[!UICONTROL All]**&#x200B;不同的組織單位，則會導致錯誤，您將無法發送交易式訊息。

因此，如果您想在交易式訊息中使用多品牌，您應將所有品牌連結至 **[!UICONTROL Message Center]** 組織單位或 **[!UICONTROL All]** 組織單位。

### 匯出和匯入交易式訊息 {#exporting-and-importing-transactional-messages}

* 要匯出交易式訊息，在[建立封包匯出](../../automating/using/managing-packages.md#creating-a-package)時需要包含相應的事件配置。
* 透過封包[匯入交易式訊息後](../../automating/using/managing-packages.md#importing-a-package)，交易式訊息清單中不會顯示該訊息。您需要[發佈事件設定](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)，才能使關聯的交易式訊息可用。

