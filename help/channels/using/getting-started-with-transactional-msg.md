---
title: 設定事務性消息的主要步驟
description: 瞭解什麼是交易式訊息，並瞭解在Adobe Campaign Standard中設定交易式訊息的主要步驟。
page-status-flag: never-activated
uuid: b316bf47-7d98-46fa-ab4f-67ff50de8095
contentOwner: lemaitre
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: landing-pages
discoiquuid: ca8d1698-6e8a-4f5a-b017-74a152e14286
context-tags: landingPage,wizard;landingPage,overview;landingPage,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 開始使用交易式訊息 {#getting-started-with-transactional-messaging}

## 概觀

<img src="assets/do-not-localize/icon_transactional.svg" width="60px">

介紹事務性消息傳 **遞的概念**

交易式訊息可讓您即時傳送個別和獨特的訊息給客戶。

它們可以是歡迎訊息、訂單運送確認、密碼更新等。
Adobe Campaign可讓您將這項功能與資訊系統整合，該資訊系統會傳送要轉換為自訂交易訊息的事件。

交易式訊息可透過電子郵件、簡訊或推播通知傳送，視您的選項而定。請檢查您的授權合約。

Adobe Campaign會優先處理交易訊息，而非其他傳送。

Adobe Campaign Standard API 也提供交易式訊息。如需詳細資訊，請參閱[詳細文件](../../api/using/managing-transactional-messages.md)。

>[!NOTE]
>
>現在，所有交易式訊息都會與 Adobe Campaign Enhanced MTA 一起傳送，以改善傳遞能力、總處理能力和彈回數處理。所有影響與標準行銷訊息的影響相同。如需詳細資訊，請參閱[本區段](../../administration/using/configuring-email-channel.md)。

## 交易式訊息定義 {#transactional-messaging-definition}

<table>
<tr>
<td align="center"><img src="assets/do-not-localize/icon_concepts.svg" width="60px"><br><p><b>什麼是交易訊息？</b></p></td>
<td><p>它是由網站等提供者所傳送的個人與獨特通訊。</p></td>
<td><p>特別需要，因為收件者想要檢查或確認的重要資訊。</p></td>
</tr>
<tr>
<td align="center"><img src="assets/do-not-localize/icon_channels.svg" width="60px"><br><p><b>什麼時候到期？</b></p></td>
<td><p> 由於此訊息包含重要資訊，因此使用者預期會即時傳送。</p></td>
<td><p>因此，觸發的事件和到達的消息之間的延遲必須非常短。</p></td>
</tr>
<tr>
<td align="center"><img src="assets/do-not-localize/icon_important.svg" width="60px"><br><p><b>為什麼這很重要？</b></p></td>
<td><p>一般而言，交易型訊息的公開率很高。 因此，它應當經過精心設計。</p></td>
<td><p>事實上，它定義了客戶關係，對客戶行為會產生很大影響。</p></td>
</tr>
<tr>
<td align="center"><img src="assets/do-not-localize/icon_example.svg" width="60px"><br><p><b>例如？</b></p></td>
<td><p>在建立帳戶、確認訂單已出貨、發票後，可能會是歡迎訊息……</p></td>
<td><p>也可以是確認密碼變更的訊息，或客戶瀏覽您的網站後的通知……</p></td>
</tr>
</table>

## 事務性消息類型

Adobe Campaign 提供兩種類型的交易式訊息：

<img src="assets/do-not-localize/icon_event.svg" width="60px">

[事件交易式訊息](../../channels/using/event-transactional-messages.md)以事件為目標。

* 事件事務性消息不包含配置檔案資訊。

* 它們與疲勞規 [則不相容](../../sending/using/fatigue-rules.md) （即使是具有輪廓的富集）。

* 傳送目標是由事件本身所包含的資料所定義。


<img src="assets/do-not-localize/icon_profile.svg" width="60px">

[從 Campaign 行銷資料庫](../../channels/using/profile-transactional-messages.md)，設定以設定檔為目標的交易式訊息。

使用配置式事務性消息，您可以：

* Apply [marketing typology rules](../../sending/using/managing-typology-rules.md) or [fatigue rules](../../sending/using/fatigue-rules.md)

* 在訊息中包含取消訂閱連結。

* 將交易式訊息新增至全域傳送報告。

* 在客戶歷程中善用交易式訊息。

在配置將轉換為交易式訊息的事件時定義訊息類型。請參閱[交易式訊息配置](../../administration/using/configuring-transactional-messaging.md)。

>[!IMPORTANT]
>
>To access all transactional messages, you must be part of the **[!UICONTROL Administrators (all units)]** security group.

## 交易式訊息傳遞操作原則 {#transactional-messaging-operating-principle}

讓我們舉一個有網站的公司為例，其客戶可以在此網站上購買產品。

Adobe Campaign 可讓您傳送通知電子郵件給已將產品新增至購物車的網站使用者：當其中一人離開網站而未完成購買時，就會自動傳送購物車放棄電子郵件給他們。

將其放置到位的步驟如下。

### 步驟1 —— 建立和發佈事件設定 {#create-event-configuration}

<img src="assets/do-not-localize/icon_config.svg" width="60px">

**事務性事件配置**:

* 設定將命名為「購物車放棄」的事件，並發佈此事件設定。

* 網站開發人員將會使用的API會部署，並自動建立交易訊息。

* 請注意，此步驟必須由具有管理權限的 [用戶執行](../../administration/using/users-management.md#functional-administrators)。

在[設定事件以傳送事件交易式訊息](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message)區段中會顯示建立和發佈事件。

### 步驟2 —— 編輯和發佈交易訊息 {#create-transactional-message}

<img src="assets/do-not-localize/icon_notification.svg" width="40px">

**交易式訊息版本**

* 編輯並個人化交易訊息、進行測試，然後發佈。

* 事務性消息隨後將準備好發送。

* 此步驟可由具有標準使用者存取權限的任何 [行銷使用者執行](../../administration/using/users-management.md#basic-users)。

For more on editing and publishing a transactional message, see [Event transactional messages](../../channels/using/event-transactional-messages.md).

### 步驟3 —— 整合事件觸發 {#integrate-event-trigger}

<img src="assets/do-not-localize/icon_api.svg" width="55px">

**事件觸發整合**

* 使用REST Transactional Messages API將事件整合到您的網站。&lt;

* 當客戶放棄購物車時，會觸發事件。

* 此步驟由您網站的開發人員執行。

如需將事件整合至網站的詳細資訊，請參閱網 [站整合](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)。

### 步驟4 —— 訊息傳送 {#message-delivery}

<img src="assets/do-not-localize/icon_channels.svg" width="60px">

**來自您網站的外部事件**

* 完成所有這些步驟後，即可傳送訊息。

* 當使用者離開網站而未在購物車中訂購產品時，就會觸發對應的促銷活動事件。

* 然後，使用者會自動收到通知電子郵件。

## 關鍵步驟 {#key-steps}

在Adobe Campaign中建立和管理個人化交易訊息的主要步驟在下表中概述。

![](assets/message-center-overview.png)

## 相關主題

* [傳送訊息的關鍵步驟](../../channels/using/key-steps-to-send-a-message.md)
* [開始使用通訊管道](../../channels/using/get-started-communication-channels.md)

<!--## Transactional messaging publication process {#transactional-messaging-pub-process}

The chart below illustrates the whole transactional messaging publication process.

![](assets/message-center_pub-process.png)

For more on the event configuration steps, see [Transactional messaging configuration](../../administration/using/configuring-transactional-messaging.md).

Read more:

* [Event transactional messages](../../channels/using/event-transactional-messages.md)
* [Profile transactional messages](../../channels/using/profile-transactional-messages.md)
* [Transactional push notifications](../../channels/using/transactional-push-notifications.md)
* [Follow-up messages](../../channels/using/follow-up-messages.md)-->