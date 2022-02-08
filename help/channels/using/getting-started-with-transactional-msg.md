---
title: 開始使用異動訊息
description: 瞭解事務性消息傳遞是什麼，並瞭解在Adobe Campaign Standard設定事務性消息的主要步驟。
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
feature: Transactional Messaging
role: User
level: Beginner
exl-id: 49fba1af-3c99-45b7-bcbb-b9b9678eedcd
source-git-commit: 0538958289ce19982889f76ed195090a8455fdeb
workflow-type: tm+mt
source-wordcount: '963'
ht-degree: 8%

---

# 開始使用異動訊息 {#getting-started-with-transactional-messaging}

## 概覽 {#overview}

<img src="assets/do-not-localize/icon_transactional.svg" width="60px">

事務性消息是由諸如網站的提供者即時發送的單獨且唯一的通信。 特別需要它，因為它包含收件人要檢查或確認的重要資訊。

* **什麼時候到期？** 由於此消息包含重要資訊，因此用戶希望該消息能夠即時發送。 因此，觸發事件和消息到達之間的延遲必須非常短。

* **為什麼這很重要？** 通常，事務性消息的開啟速率較高。 因此，它應該經過精心設計，因為它在定義客戶關係時會對客戶行為產生很大影響。

* **比如說？** 它可能是建立帳戶後的歡迎消息、訂單已發運的確認、發票、確認密碼更改的消息或客戶瀏覽您的網站後的通知等。

Adobe Campaign允許您將此功能與資訊系統整合，該資訊系統發送要轉換為自定義事務性消息的事件。

事務性消息可通過電子郵件、簡訊或 [推送通知](../../channels/using/transactional-push-notifications.md)，具體取決於您的選項。 請檢查您的授權合約。

>[!NOTE]
>
>Adobe Campaign優先處理事務性消息，而不是任何其他傳遞。

<!--Guidelines to implement transactional messaging capabilities in your website are detailed in [this section](../../api/using/managing-transactional-messages.md).-->

在開始事務性消息傳遞之前，請確保您已讀取相應的 [最佳做法和限制](../../channels/using/transactional-messaging-limitations.md)。

## 交易式訊息傳遞操作原則 {#transactional-messaging-operating-principle}

事務性消息傳遞整個過程可描述如下：

![](assets/message-center-process.png)

例如，假設您是一家擁有網站的公司，客戶可以在該網站上購買產品。

Adobe Campaign允許您向已將產品添加到購物車的客戶發送通知電子郵件。 當其中一個人離開您的網站而未完成其購買（觸發市場活動事件的外部事件）時，將自動向他們發送購物車放棄電子郵件（事務性消息傳遞）。

實施此項措施的主要步驟如下 [此部分](#key-steps)。

## 事務性消息類型 {#transactional-message-types}

Adobe Campaign提供兩種類型的事務性消息。

**事件事務消息** 事件本身中包含的目標資料。 以下消息：
* 不包含配置檔案資訊，因此不能包含取消訂閱連結。
* 與疲勞規則不相容（即使在富集輪廓的情況下）。
* 由事件本身中包含的資料定義其傳送目標。

您可能希望將事件事務性消息發送給需要檢索忘記的密碼或確認訂單的客戶。 實際上，您不希望您的收件人取消訂閱此類通信，並且此通知不應作為疲勞規則的一部分添加到市場營銷消息的計數器中。

**配置檔案事務性消息** 市場活動市場營銷資料庫中的目標配置檔案。 使用此類消息，您可以：
* 利用Adobe Campaign資料庫中包含的資料。
* 通過添加 [濃縮](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content) 到事件配置。
* 應用 [營銷類型規則](../../sending/using/managing-typology-rules.md) 或 [疲勞規則](../../sending/using/fatigue-rules.md)。
* 在訊息中包含取消訂閱連結。
* 將交易式訊息新增至全域傳送報告。
* 在客戶歷程中善用交易式訊息。

例如，在客戶放棄您網站上的購物車後，在聯繫他們時，您可以使用此類消息，以鼓勵他們繼續購買。 通過這樣做，您可以更輕鬆地個性化您的消息，直接訪問您的配置檔案資料庫中的所有資訊，應用營銷規則並將此消息包括到全球客戶行程和報告中，以便更好地查看您的客戶行為。

在配置將轉換為交易式訊息的事件時定義訊息類型。查看 [基於事件的事務性消息](../../channels/using/configuring-transactional-event.md#event-based-transactional-messages) 和 [基於配置檔案的事務性消息](../../channels/using/configuring-transactional-event.md#profile-based-transactional-messages) 配置部分。

## 主要步驟 {#key-steps}

在以下架構中概述了在Adobe Campaign建立和管理個性化事務性消息的主要步驟。

![](assets/message-center-overview.png)

下面將進一步詳細介紹這些步驟。

>[!IMPORTANT]
>
>僅具有 [管理](../../administration/using/users-management.md#functional-administrators) 角色可以配置事務事件並訪問事務消息。

### 步驟1 — 建立和發佈事件配置 {#create-event-configuration}

<!--<img src="assets/do-not-localize/icon_config.svg" width="60px">-->

| 用戶 | 動作 | 結果 |
|--- |--- |--- |
| 此步驟必須由管理員執行， [管理權限](../../administration/using/users-management.md#functional-administrators)。 | 配置名為「購物車放棄」的事件並發佈此事件配置。 | 將部署網站開發人員將使用的API，並自動建立事務性消息。 |

建立和發佈事件顯示在 [配置事務事件](../../channels/using/configuring-transactional-event.md) 和 [發佈事務性事件](../../channels/using/publishing-transactional-event.md) 的下界。

### 步驟2 — 編輯和發佈事務性消息 {#create-transactional-message}

<!--<img src="assets/do-not-localize/icon_notification.svg" width="40px">-->

| 用戶 | 動作 | 結果 |
|--- |--- |--- |
| 該步驟可由市場用戶保持執行 [管理權限](../../administration/using/users-management.md#functional-administrators)。 | 編輯並個性化事務性消息，test它，然後發佈它。 | 事務性消息隨後準備發送。 |

有關編輯和發佈事務性消息的詳細資訊，請參見 [編輯事務性消息](../../channels/using/editing-transactional-message.md) 和 [事務性消息生命週期](../../channels/using/publishing-transactional-message.md)。

### 步驟3 — 整合事件觸發 {#integrate-event-trigger}

<!--<img src="assets/do-not-localize/icon_api.svg" width="55px">-->

<!--**Event triggering integration**-->

| 用戶 | 動作 | 結果 |
|--- |--- |--- |
| 此步驟由網站的開發人員執行。 | 使用REST事務性消息API將事件整合到您的網站中。 | 當客戶端放棄其購物車時，將觸發該事件。 |

建立事件後，您需要將觸發此事件的操作整合到您的網站中。<!--In this example, you want a "Cart abandonment" event to be triggered whenever one of your clients leaves your website before purchasing the products in their cart.--> 要執行此操作，您的網站開發人員必須使用 **Adobe Campaign StandardREST API**。

有關使用市場活動REST API管理事務性消息的詳細資訊，請參閱 [REST API文檔](../../api/using/managing-transactional-messages.md)。

### 步驟4 — 消息傳遞 {#message-delivery}

<!--<img src="assets/do-not-localize/icon_channels.svg" width="60px">-->

一旦執行了所有這些步驟，就可以傳遞消息。

一旦用戶離開站點而未在其購物車中訂購產品，就會觸發相應的市場活動事件。 用戶自動接收通知電子郵件。

## 相關主題

* [傳送訊息的重要步驟](../../channels/using/key-steps-to-send-a-message.md)
* [開始使用通訊頻道](../../channels/using/get-started-communication-channels.md)
* [異動推送通知](../../channels/using/transactional-push-notifications.md)
* [後續追蹤訊息](../../channels/using/follow-up-messages.md)
