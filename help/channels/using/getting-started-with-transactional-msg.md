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
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 429142610b969f3bd1460a8ba401c7e83acb7dea
workflow-type: tm+mt
source-wordcount: '753'
ht-degree: 27%

---


# 交易式訊息快速入門 {#getting-started-with-transactional-messaging}

## 概觀


<img src="assets/do-not-localize/icon_transactional.svg" width="60px">

交易式訊息可讓您 <b>即時傳送個別和獨特的訊息</b> ，給客戶。 可以是歡迎訊息、訂購發運確認、密碼修改等。

Adobe Campaign可讓您將這項功能與資訊系統整合，該資訊系統會傳送要轉換為自訂交易訊息的事件。

>[!NOTE]
>
>交易式訊息可透過電子郵件、簡訊或推播通知傳送，視您的選項而定。請檢查您的授權合約。

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

<!--[Event transactional messages](../../channels/using/event-transactional-messages.md) targeting an **event**. The data contained in the event itself is used to define the delivery target.-->

<table>
<tr>
<td align="center"><img src="assets/do-not-localize/icon_event.svg" width="60px"><br><p><a href="../../channels/using/event-transactional-messages.md">事件事務</a><br>性訊息建立事 <b>件</b></p></td>
<td><p><ul><li>它們不包含描述檔資訊。</li><li>它們與疲勞規 <a href="../../sending/using/fatigue-rules.md">則不相容</a> （即使是具有輪廓的富集）。</li><li>傳送目標是由事件本身所包含的資料所定義。</li></ul></p></td>
</tr>
<tr>
<td align="center"><img src="assets/do-not-localize/icon_profile.svg" width="60px"><br><p><a href="../../channels/using/profile-transactional-messages.md">從Adobe Campaign行</a><br>銷資料 <b>庫設定檔交易訊息收集設定檔</b></p></td>
<td><p>配置檔案事務性消息允許您：<ul><li>套用行銷類型學規則，例如 <b>區塊清單上的位址</b><a href="../../sending/using/fatigue-rules.md">或疲勞規則</a>。</li><li>在訊息中包含取消訂閱連結。</li><li>將交易式訊息新增至全域傳送報告。</li><li>在客戶歷程中善用交易式訊息。</li></ul></p></td>
</tr>
</table>

<!--[Profile transactional messages](../../channels/using/profile-transactional-messages.md) targeting **profiles from the Adobe Campaign marketing database**. You can use information from the Adobe Campaign database to send a transactional message based on customer marketing profiles.-->

在配置將轉換為交易式訊息的事件時定義訊息類型。請參閱[交易式訊息配置](../../administration/using/configuring-transactional-messaging.md)。

>[!IMPORTANT]
>
>To access all transactional messages, you must be part of the **[!UICONTROL Administrators (all units)]** security group.

<!--Event transactional messages do not contain profile information, therefore they are not compatible with fatigue rules (even in the case of an enrichment with profiles). However, profile transactional messages are compatible. For more on fatigue rules, see [this section](../../sending/using/fatigue-rules.md#choosing-the-channel).-->

## 交易式訊息傳遞操作原則 {#transactional-messaging-operating-principle}

讓我們舉一個有網站的公司為例，其客戶可以在此網站上購買產品。

Adobe Campaign 可讓您傳送通知電子郵件給已將產品新增至購物車的網站使用者：當其中一人離開網站而未完成購買時，就會自動傳送購物車放棄電子郵件給他們。

將其放置到位的步驟如下。

### 步驟1 —— 建立和發佈事件設定 {#create-event-configuration}

<!--<img src="assets/do-not-localize/icon_config.svg" width="60px">

Configure an event that will be named "Cart abandonment" and publish this event configuration.

The API that will be used by your website developer is deployed and a transactional message is automatically created.-->

<table>
<tr>
<td align="center"><img src="assets/do-not-localize/icon_config.svg" width="60px"><br><p>設定將命名為「購物車放棄」的事件，並發佈此事件設定。</p></td>
<td>網站開發人員將會使用的API會部署，並自動建立交易訊息。</td>
</tr>
</table>

在[設定事件以傳送事件交易式訊息](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message)區段中會顯示建立和發佈事件。

### 步驟2 —— 編輯和發佈交易訊息 {#create-transactional-message}

<!--<img src="assets/do-not-localize/icon_transactional.svg" width="60px">

Edit and personalize the transactional message, test it, and then publish it.-->

<table>
<tr>
<td align="center"><img src="assets/do-not-localize/icon_notification.svg" width="45px"><br><p>編輯並個人化交易訊息、進行測試，然後發佈。</p></td>
<td>事務性消息隨後將準備好發送。</td>
</tr>
</table>

For more on editing and publishing a transactional message, see [Event transactional messages](../../channels/using/event-transactional-messages.md).

### 步驟3 —— 整合事件觸發 {#integrate-event-trigger}

<!--<img src="assets/do-not-localize/icon_api.svg" width="60px">

Use the REST Transactional Messages API to integrate the event into your website.

The event will be triggered when a client abandons their cart.-->

<table>
<tr>
<td align="center"><img src="assets/do-not-localize/icon_api.svg" width="60px"><br><p>使用REST Transactional Messages API將事件整合到您的網站。</p></td>
<td>當客戶放棄購物車時，會觸發事件。</td>
</tr>
</table>

如需將事件整合至網站的詳細資訊，請參閱網 [站整合](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)。

### 步驟4 —— 訊息傳送 {#message-delivery}

<!--Once all of these steps have been carried out, the message can be delivered:

<img src="assets/do-not-localize/icon_notification.svg" width="40px">

As soon as a user leaves the site without ordering the products in their cart, they automatically receive a notification email.-->

<table>
<tr>
<td align="center"><img src="assets/do-not-localize/icon_channels.svg" width="60px"><br><p>完成所有這些步驟後，即可傳送訊息。</p></td>
<td>當使用者離開網站而未在購物車中訂購產品時，他們會自動收到通知電子郵件。</td>
</tr>
</table>

## 關鍵步驟 {#key-steps}

在Adobe Campaign中建立和管理個人化交易訊息的主要步驟在下表中概述。

![](assets/message-center-overview.png)

<!--## Transactional messaging publication process {#transactional-messaging-pub-process}

The chart below illustrates the whole transactional messaging publication process.

![](assets/message-center_pub-process.png)

For more on the event configuration steps, see [Transactional messaging configuration](../../administration/using/configuring-transactional-messaging.md).

Read more:

* [About transactional messaging](../../channels/using/about-transactional-messaging.md)
* [Event transactional messages](../../channels/using/event-transactional-messages.md)
* [Profile transactional messages](../../channels/using/profile-transactional-messages.md)
* [Transactional push notifications](../../channels/using/transactional-push-notifications.md)
* [Follow-up messages](../../channels/using/follow-up-messages.md)-->

**相關主題：**

* [傳送訊息的關鍵步驟](../../channels/using/key-steps-to-send-a-message.md)
* [開始使用通訊管道](../../channels/using/get-started-communication-channels.md)