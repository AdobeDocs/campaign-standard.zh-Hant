---
solution: Campaign Standard
product: campaign
title: 設定事務性消息的主要步驟
description: 瞭解什麼是交易式訊息，並瞭解在Adobe Campaign Standard中設定交易式訊息的主要步驟。
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
translation-type: tm+mt
source-git-commit: c276c468627208b584a0342414cdbe382e349f50
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 開始使用交易式訊息 {#getting-started-with-transactional-messaging}

## 概觀 {#overview}

<img src="assets/do-not-localize/icon_transactional.svg" width="60px">

交易式訊息是由網站等提供者即時傳送的個人與唯一通訊。 特別需要，因為收件者想要檢查或確認的重要資訊。

* **什麼時候到期？** 由於此訊息包含重要資訊，因此使用者預期會即時傳送。因此，觸發的事件和到達的消息之間的延遲必須非常短。

* **為什麼這很重要？** 一般而言，交易型訊息的公開率很高。因此，應謹慎設計它，因為它定義客戶關係時，會對客戶的行為產生強烈影響。

* **例如？** 它可能是建立帳戶後的歡迎訊息、確認訂單已出貨、發票、確認密碼變更的訊息，或客戶瀏覽您的網站後的通知等。

Adobe Campaign可讓您將這項功能與資訊系統整合，該資訊系統會傳送要轉換為自訂交易訊息的事件。

交易訊息可以透過電子郵件、SMS或[推播通知](../../channels/using/transactional-push-notifications.md)傳送，視您的選項而定。 請檢查您的授權合約。

>[!NOTE]
>
>Adobe Campaign會優先處理交易訊息，而非其他傳送。

<!--Guidelines to implement transactional messaging capabilities in your website are detailed in [this section](../../api/using/managing-transactional-messages.md).-->

<!--All transactional messages are now sent with the Adobe Campaign Enhanced MTA for improved deliverability, throughput, and bounce handling. All impacts are the same as for standard marketing messages. For more on this, see [this section](../../administration/using/configuring-email-channel.md).-->

在開始使用事務性消息傳遞之前，請務必閱讀相應的[最佳實踐和限制](../../channels/using/transactional-messaging-limitations.md)。

## 交易式訊息傳遞操作原則 {#transactional-messaging-operating-principle}

事務性消息傳遞整個過程可描述如下：

![](assets/message-center-process.png)

例如，假設您是一家有網站的公司，客戶可以在那裡購買產品。

Adobe Campaign可讓您傳送通知電子郵件給已將產品新增至購物車的客戶。 當其中一人離開您的網站而未完成購買（觸發促銷活動事件的外部事件）時，會自動傳送購物車放棄電子郵件給他們（交易式訊息傳送）。

[本節](#key-steps)中將此功能放置到位的主要步驟如下。

## 事務性消息類型{#transactional-message-types}

Adobe Campaign提供兩種交易訊息。

**事件事務** 性消息包含事件本身中的資料。這些訊息：
* 不包含描述檔資訊，因此不能包含取消訂閱連結。
* 與疲勞規則不相容（即使在具有輪廓的富集情況下）。
* 讓其傳送目標由事件本身包含的資料所定義。

您可能想要傳送事件交易訊息給需要擷取忘記密碼（例如）或確認訂單的客戶。 事實上，您不希望收件者取消訂閱此類通訊，而且此通知不應新增至行銷訊息的計數器，做為疲勞規則的一部分。

**從Campaign行銷資** 料庫設定交易式訊息收集設定檔。使用此類消息，您可以：
* 運用Adobe Campaign資料庫中的資料。
* 將[enrichment](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content)新增至事件設定，以個人化您的訊息。
* 套用[行銷類型學規則](../../sending/using/managing-typology-rules.md)或[疲勞規則](../../sending/using/fatigue-rules.md)。
* 在訊息中包含取消訂閱連結。
* 將交易式訊息新增至全域傳送報告。
* 在客戶歷程中善用交易式訊息。

例如，當客戶在網站上放棄購物車後與他們聯絡時，您可以使用此類訊息，以鼓勵他們繼續購買。 如此一來，您就可以透過直接存取個人檔案資料庫中的所有資訊，更輕鬆地個人化您的訊息、套用行銷規則，並將此訊息納入全球客戶歷程和報告，以便更好地瞭解客戶行為。

在配置將轉換為交易式訊息的事件時定義訊息類型。請參閱[基於事件的事務消息](../../channels/using/configuring-transactional-event.md#event-based-transactional-messages)和[基於概要的事務消息](../../channels/using/configuring-transactional-event.md#profile-based-transactional-messages)配置部分。

## 關鍵步驟{#key-steps}

在Adobe Campaign中建立和管理個人化交易訊息的主要步驟在以下結構中進行概述。

![](assets/message-center-overview.png)

以下將進一步詳述這些步驟。

>[!IMPORTANT]
>
>只有[Administration](../../administration/using/users-management.md#functional-administrators)角色的用戶才能配置事務事件並訪問事務消息。

### 步驟1 —— 建立和發佈事件配置{#create-event-configuration}

<img src="assets/do-not-localize/icon_config.svg" width="60px">

| 使用者 | 動作 | 結果 |
|--- |--- |--- |
| 此步驟必須由持有[管理權限](../../administration/using/users-management.md#functional-administrators)的管理員執行。 | 設定將命名為「購物車放棄」的事件，並發佈此事件設定。 | 網站開發人員將會使用的API會部署，並自動建立交易訊息。 |

建立和發佈事件顯示在[配置事務事件](../../channels/using/configuring-transactional-event.md)和[發佈事務事件](../../channels/using/publishing-transactional-event.md)部分中。

### 步驟2 —— 編輯和發佈事務性消息{#create-transactional-message}

<img src="assets/do-not-localize/icon_notification.svg" width="40px">

| 使用者 | 動作 | 結果 |
|--- |--- |--- |
| 此步驟可由持有[管理權限](../../administration/using/users-management.md#functional-administrators)的行銷使用者執行。 | 編輯並個人化交易訊息、進行測試，然後發佈。 | 事務性消息隨後就可以發送。 |

有關編輯和發佈事務性消息的詳細資訊，請參閱[編輯事務性消息](../../channels/using/editing-transactional-message.md)和[事務性消息生命週期](../../channels/using/publishing-transactional-message.md)。

### 步驟3 —— 整合觸發{#integrate-event-trigger}的事件

<img src="assets/do-not-localize/icon_api.svg" width="55px">

<!--**Event triggering integration**-->

| 使用者 | 動作 | 結果 |
|--- |--- |--- |
| 此步驟由您網站的開發人員執行。 | 使用REST Transactional Messages API將事件整合到您的網站。 | 當客戶放棄購物車時，會觸發事件。 |

建立事件後，您必須將觸發此事件整合到您的網站中。<!--In this example, you want a "Cart abandonment" event to be triggered whenever one of your clients leaves your website before purchasing the products in their cart.--> 若要這麼做，您的網站網頁開發人員必須使 **用Adobe Campaign Standard REST API**。

如需有關使用Campaign REST API管理交易訊息的詳細資訊，請參閱[REST API檔案](../../api/using/managing-transactional-messages.md)。

### 步驟4 —— 消息傳遞{#message-delivery}

<img src="assets/do-not-localize/icon_channels.svg" width="60px">

完成所有這些步驟後，即可傳送訊息。

當使用者離開網站而未在購物車中訂購產品時，就會觸發對應的促銷活動事件。 使用者會自動收到通知電子郵件。

## 相關主題

* [傳送訊息的關鍵步驟](../../channels/using/key-steps-to-send-a-message.md)
* [開始使用通訊管道](../../channels/using/get-started-communication-channels.md)
* [交易式推播通知](../../channels/using/transactional-push-notifications.md)
* [後續訊息](../../channels/using/follow-up-messages.md)
