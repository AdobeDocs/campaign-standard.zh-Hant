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
source-git-commit: 00032b1a8bfef301d1a87750695ba1670b2eed6c
workflow-type: tm+mt
source-wordcount: '831'
ht-degree: 17%

---


# 開始使用交易式訊息 {#getting-started-with-transactional-messaging}

## 概觀 {#overview}

### 什麼是交易訊息？

它是由網站等供應商即時傳送的個人與獨特通訊。 特別需要，因為收件者想要檢查或確認的重要資訊。

* **什麼時候到期？** 由於此訊息包含重要資訊，因此使用者預期會即時傳送。因此，觸發的事件和到達的消息之間的延遲必須非常短。

* **為什麼這很重要？** 一般而言，交易型訊息的公開率很高。因此，應謹慎設計它，因為它定義客戶關係時，會對客戶的行為產生強烈影響。

* **例如？** 這可能是建立帳戶後的歡迎訊息、確認訂單已出貨、發票、確認密碼變更的訊息，或客戶瀏覽您的網站後的通知……

### 事務性消息發送

Adobe Campaign可讓您將這項功能與資訊系統整合，該資訊系統會傳送要轉換為自訂交易訊息的事件。

交易式訊息可透過電子郵件、簡訊或推播通知傳送，視您的選項而定。請檢查您的授權合約。

>[!NOTE]
>
>Adobe Campaign會優先處理交易訊息，而非其他傳送。

Adobe Campaign Standard API 也提供交易式訊息。有關詳細資訊，請參閱[專用文檔](../../api/using/managing-transactional-messages.md)。

>[!NOTE]
>
>現在，所有交易式訊息都會與 Adobe Campaign Enhanced MTA 一起傳送，以改善傳遞能力、總處理能力和彈回數處理。所有影響與標準行銷訊息的影響相同。如需詳細資訊，請參閱[本節](../../administration/using/configuring-email-channel.md)。

### 事務性消息類型{#transactional-message-types}

Adobe Campaign 提供兩種類型的交易式訊息：

**事件交易** 訊息會鎖定事件：
* 它們不包含描述檔資訊。
* 它們與疲勞規則不相容（即使是具有輪廓的富集）。
* 傳送目標是由事件本身所包含的資料所定義。

**描述檔交** 易訊息是定位來自促銷活動行銷資料庫的描述檔。使用此類消息，您可以：
* 套用[行銷類型學規則](../../sending/using/managing-typology-rules.md)或[疲勞規則](../../sending/using/fatigue-rules.md)。
* 在訊息中包含取消訂閱連結。
* 將交易式訊息新增至全域傳送報告。
* 在客戶歷程中善用交易式訊息。

在配置將轉換為交易式訊息的事件時定義訊息類型。請參閱[本節](../../channels/using/configuring-transactional-event.md#transactional-event-specific-configurations)。

>[!IMPORTANT]
>
>要訪問所有事務性消息，您必須是&#x200B;**[!UICONTROL Administrators (all units)]**&#x200B;安全組的一部分。

## 交易式訊息傳遞操作原則 {#transactional-messaging-operating-principle}

事務性消息傳遞整個過程可描述如下：

![](assets/message-center-process.png)

例如，假設您是有網站的公司，客戶可在此購買產品。

Adobe Campaign可讓您傳送通知電子郵件給已將產品新增至購物車的客戶：當其中一人離開您的網站而未完成購買（觸發促銷活動事件的外部事件）時，會自動傳送購物車放棄電子郵件給他們（交易式訊息傳送）。

<!--The steps for putting this into place are detailed below.-->

### 關鍵步驟{#key-steps}

在Adobe Campaign中建立和管理個人化交易訊息的主要步驟在下表中概述。

![](assets/message-center-overview.png)

以下將進一步詳述這些步驟。

### 步驟1 —— 建立和發佈事件配置{#create-event-configuration}

<img src="assets/do-not-localize/icon_config.svg" width="60px">

| 使用者 | 動作 | 結果 |
|--- |--- |--- |
| 此步驟必須由具有[管理權限](../../administration/using/users-management.md#functional-administrators)的用戶執行。 | 設定將命名為「購物車放棄」的事件，並發佈此事件設定。 | 網站開發人員將會使用的API會部署，並自動建立交易訊息。 |

建立和發佈事件顯示在[配置事務事件](../../channels/using/configuring-transactional-event.md)和[發佈事務事件](../../channels/using/publishing-transactional-event.md)部分中。

### 步驟2 —— 編輯和發佈事務性消息{#create-transactional-message}

<img src="assets/do-not-localize/icon_notification.svg" width="40px">

| 使用者 | 動作 | 結果 |
|--- |--- |--- |
| 此步驟可由具有[標準使用者存取權限](../../administration/using/users-management.md#basic-users)的任何行銷使用者執行。 | 編輯並個人化交易訊息、進行測試，然後發佈。 | 事務性消息隨後就可以發送。 |

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
