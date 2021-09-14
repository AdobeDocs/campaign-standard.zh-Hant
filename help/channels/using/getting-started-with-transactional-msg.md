---
title: 開始使用異動訊息
description: 探索什麼是交易式訊息，並了解在Adobe Campaign Standard中設定交易式訊息的主要步驟。
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
feature: Transactional Messaging
role: User
level: Beginner
exl-id: 49fba1af-3c99-45b7-bcbb-b9b9678eedcd
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '963'
ht-degree: 8%

---

# 開始使用異動訊息 {#getting-started-with-transactional-messaging}

## 概覽 {#overview}

<img src="assets/do-not-localize/icon_transactional.svg" width="60px">

交易式訊息是由諸如網站的提供者即時傳送的個別和唯一通訊。 此變數尤其值得期待，因為其中包含收件者要檢查或確認的重要資訊。

* **什麼時候到？** 因為此訊息包含重要資訊，使用者預期會即時傳送。因此，觸發的事件與到達的訊息之間的延遲必須非常短。

* **為什麼這很重要？** 一般而言，交易式訊息的開放率很高。因此，應謹慎設計，因為它定義客戶關係時，可能對客戶的行為產生重大影響。

* **例如？** 這可能是建立帳戶後的歡迎訊息、訂單已出貨的確認、發票、確認密碼變更的訊息，或客戶瀏覽您的網站後的通知等。

Adobe Campaign可讓您將此功能與資訊系統整合，該資訊系統會傳送要轉換為自訂交易式訊息的事件。

交易式訊息可以透過電子郵件、SMS或[推播通知](../../channels/using/transactional-push-notifications.md)傳送，視您的選項而定。 請檢查您的授權合約。

>[!NOTE]
>
>Adobe Campaign會優先處理交易式訊息，而非其他傳送。

<!--Guidelines to implement transactional messaging capabilities in your website are detailed in [this section](../../api/using/managing-transactional-messages.md).-->

開始使用交易式訊息之前，請務必閱讀對應的[最佳作法和限制](../../channels/using/transactional-messaging-limitations.md)。

## 交易式訊息傳遞操作原則 {#transactional-messaging-operating-principle}

交易式訊息整體程式可說明如下：

![](assets/message-center-process.png)

例如，假設您是一家有網站的公司，客戶可在此購買產品。

Adobe Campaign可讓您傳送通知電子郵件給已將產品新增至購物車的客戶。 當其中一個使用者離開您的網站而未進行購買時（觸發促銷活動事件的外部事件），購物車放棄率電子郵件會自動傳送給他們（交易式訊息傳送）。

在[本節](#key-steps)中詳細說明了實施此操作的主要步驟。

## 交易式訊息類型 {#transactional-message-types}

Adobe Campaign提供兩種交易式訊息。

**事件本** 身包含的事件交易式訊息Get資料。這些訊息：
* 不包含設定檔資訊，因此不能包含取消訂閱連結。
* 與疲勞規則不相容（即使在擴充設定檔的情況下亦然）。
* 由事件本身包含的資料來定義其傳送目標。

您可能想要傳送事件交易式訊息給需要擷取忘記密碼（例如，或確認訂單）的客戶。 事實上，您不希望收件者取消訂閱此類通訊，且您不應將此通知新增至行銷訊息的計數器，作為疲勞規則的一部分。

**從Campaign行銷** 資料庫設定交易式訊息get設定檔。使用此類型的訊息，您可以：
* 運用Adobe Campaign資料庫中包含的資料。
* 將[excrent](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content)新增至事件設定，使用設定檔資訊個人化您的訊息。
* 套用[行銷類型規則](../../sending/using/managing-typology-rules.md)或[疲勞規則](../../sending/using/fatigue-rules.md)。
* 在訊息中包含取消訂閱連結。
* 將交易式訊息新增至全域傳送報告。
* 在客戶歷程中善用交易式訊息。

例如，在客戶放棄在您網站上的購物車後與他們聯絡時，您可以使用這類訊息，以鼓勵他們繼續購買。 這麼做，您就可以透過直接存取設定檔資料庫中的所有資訊，更輕鬆地個人化您的訊息、套用行銷規則，並將此訊息納入全域客戶歷程和報告，以便更清楚地了解您的客戶行為。

在配置將轉換為交易式訊息的事件時定義訊息類型。請參閱[事件交易式訊息](../../channels/using/configuring-transactional-event.md#event-based-transactional-messages)和[設定檔交易式訊息](../../channels/using/configuring-transactional-event.md#profile-based-transactional-messages)設定區段。

## 主要步驟 {#key-steps}

在Adobe Campaign中建立及管理個人化交易式訊息的主要步驟摘要於以下結構中。

![](assets/message-center-overview.png)

以下將詳細說明這些步驟。

>[!IMPORTANT]
>
>只有具有[Administration](../../administration/using/users-management.md#functional-administrators)角色的使用者才能設定交易事件並存取交易式訊息。

### 步驟1 — 建立並發佈事件設定 {#create-event-configuration}

<img src="assets/do-not-localize/icon_config.svg" width="60px">

| 使用者 | 動作 | 結果 |
|--- |--- |--- |
| 此步驟必須由擁有[管理權限](../../administration/using/users-management.md#functional-administrators)的管理員執行。 | 設定將命名為「購物車放棄」的事件，並發佈此事件設定。 | 系統會部署網站開發人員將使用的API，並自動建立交易式訊息。 |

在[設定交易式事件](../../channels/using/configuring-transactional-event.md)和[發佈交易式事件](../../channels/using/publishing-transactional-event.md)區段中會顯示建立和發佈事件。

### 步驟2 — 編輯和發佈交易式訊息 {#create-transactional-message}

<img src="assets/do-not-localize/icon_notification.svg" width="40px">

| 使用者 | 動作 | 結果 |
|--- |--- |--- |
| 此步驟可由擁有[管理權限](../../administration/using/users-management.md#functional-administrators)的行銷使用者執行。 | 編輯並個人化交易式訊息、測試，然後發佈。 | 交易式訊息便會準備好傳送。 |

有關編輯和發佈交易式訊息的詳細資訊，請參閱[編輯交易式訊息](../../channels/using/editing-transactional-message.md)和[交易式訊息生命週期](../../channels/using/publishing-transactional-message.md)。

### 步驟3 — 整合事件觸發 {#integrate-event-trigger}

<img src="assets/do-not-localize/icon_api.svg" width="55px">

<!--**Event triggering integration**-->

| 使用者 | 動作 | 結果 |
|--- |--- |--- |
| 此步驟由您網站的開發人員執行。 | 使用REST交易式訊息API將事件整合至您的網站。 | 當用戶端放棄購物車時，就會觸發事件。 |

建立事件後，您必須將此事件的觸發整合至您的網站。<!--In this example, you want a "Cart abandonment" event to be triggered whenever one of your clients leaves your website before purchasing the products in their cart.--> 若要這麼做，您的網站網頁開發人員必須使 **用Adobe Campaign Standard REST API**。

如需使用Campaign REST API管理交易式訊息的詳細資訊，請參閱[REST API檔案](../../api/using/managing-transactional-messages.md)。

### 步驟4 — 訊息傳送 {#message-delivery}

<img src="assets/do-not-localize/icon_channels.svg" width="60px">

執行完所有這些步驟後，即可傳送訊息。

當使用者離開網站而未在購物車中訂購產品時，就會觸發對應的促銷活動事件。 使用者會自動收到通知電子郵件。

## 相關主題

* [傳送訊息的重要步驟](../../channels/using/key-steps-to-send-a-message.md)
* [開始使用通訊頻道](../../channels/using/get-started-communication-channels.md)
* [異動推送通知](../../channels/using/transactional-push-notifications.md)
* [後續追蹤訊息](../../channels/using/follow-up-messages.md)
