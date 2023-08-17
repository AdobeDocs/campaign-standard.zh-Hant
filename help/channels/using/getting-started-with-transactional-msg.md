---
title: 開始使用異動訊息
description: 探索什麼是交易式訊息，並瞭解在Adobe Campaign Standard中設定交易式訊息的主要步驟。
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
feature: Transactional Messaging
role: User
level: Beginner
exl-id: 49fba1af-3c99-45b7-bcbb-b9b9678eedcd
source-git-commit: 0e486e87c94e273442de23d6eb65c99f065e5a71
workflow-type: tm+mt
source-wordcount: '988'
ht-degree: 9%

---

# 開始使用異動訊息 {#getting-started-with-transactional-messaging}

交易式訊息是個別且唯一的通訊，由提供者（例如網站）即時傳送。 此為特別預期行為，因為它包含收件者要檢查或確認的重要資訊。

* **何時到期？** 由於此訊息包含重要資訊，使用者預期會即時傳送。 因此，觸發的事件與到達的訊息之間的延遲必須非常短。

* **為什麼這很重要？** 一般而言，交易式訊息具有高開啟率。 因此，應謹慎設計，因為它在定義使用者端關係時可能對客戶行為產生強烈影響。

* **例如？** 可能是建立帳戶後的歡迎訊息、確認訂單已出貨、發票、確認密碼變更的訊息，或客戶瀏覽您的網站後的通知等。

Adobe Campaign可讓您將此功能與資訊系統整合，資訊系統會將要轉換為自訂交易式訊息的事件傳送出去。

交易式訊息可透過電子郵件、簡訊或 [推播通知](../../channels/using/transactional-push-notifications.md)，視您的選項而定。 請檢查您的授權合約。

>[!NOTE]
>
>Adobe Campaign會優先處理交易式訊息，而非其他傳送。

<!--Guidelines to implement transactional messaging capabilities in your website are detailed in [this section](../../api/using/managing-transactional-messages.md).-->

開始進行異動訊息傳送前，請務必閱讀與 [最佳作法和限制](../../channels/using/transactional-messaging-limitations.md).

## 交易式訊息傳遞操作原則 {#transactional-messaging-operating-principle}

交易式訊息傳遞整體程式的說明如下：

![](assets/message-center-process.png)

例如，假設您是一間擁有網站的公司，客戶可以在其中購買產品。

Adobe Campaign可讓您傳送通知電子郵件給已將產品新增至購物車的客戶。 當其中一人離開您的網站而未完成購買（觸發促銷活動事件的外部事件）時，就會自動傳送購物車放棄電子郵件給他們（交易式訊息傳送）。

設定此專案的主要步驟詳載於下文： [本節](#key-steps).

## 異動訊息型別 {#transactional-message-types}

Adobe Campaign提供兩種型別的交易式訊息。

**事件交易式訊息** 事件本身包含的目標資料。 這些訊息：
* 不包含設定檔資訊，因此無法包含取消訂閱連結。
* 與疲勞規則不相容（即使在具有設定檔的擴充的情況下）。
* 讓事件本身包含的資料定義其傳遞目標。

例如，您可能需要將事件交易式訊息傳送給需要擷取忘記密碼的客戶，或確認訂單。 事實上，您不希望收件者取消訂閱此類通訊，且此通知不應新增至行銷訊息的計數器，作為疲勞規則的一部分。

**設定檔交易式訊息** 從Campaign行銷資料庫定位設定檔。 使用此型別的訊息，您可以：
* 運用Adobe Campaign資料庫中包含的資料。
* 新增個人化訊息，使用設定檔資訊 [擴充](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content) 至事件設定。
* 套用 [行銷型別規則](../../sending/using/managing-typology-rules.md) 或 [疲勞規則](../../sending/using/fatigue-rules.md).
* 在訊息中包含取消訂閱連結。
* 將交易式訊息新增至全域傳送報告。
* 在客戶歷程中善用交易式訊息。

例如，當客戶在您的網站上放棄購物車後，您可在聯絡客戶時使用此型別的訊息，以鼓勵他們繼續購買。 這樣一來，您就可以更輕鬆地個人化訊息，直接存取設定檔資料庫中的所有資訊、套用行銷規則，並將此訊息納入全球客戶歷程及報告，以便更妥善地檢視客戶行為。

在配置將轉換為交易式訊息的事件時定義訊息類型。請參閱 [事件交易式訊息](../../channels/using/configuring-transactional-event.md#event-based-transactional-messages) 和 [設定檔交易式訊息](../../channels/using/configuring-transactional-event.md#profile-based-transactional-messages) 設定區段。

## 主要步驟 {#key-steps}

下列結構描述會摘要在Adobe Campaign中建立和管理個人化交易式訊息的主要步驟。

![](assets/message-center-overview.png)

以下會詳細說明每個步驟。

>[!IMPORTANT]
>
>僅限具有下列專案的使用者： [管理](../../administration/using/users-management.md#functional-administrators) 角色可以設定異動事件並存取異動訊息。

### 步驟1 — 建立和發佈事件設定 {#create-event-configuration}

<!--<img src="assets/do-not-localize/icon_config.svg" width="60px">-->

| 建立事件 | 使用者 | 動作 | 結果 |
| --- |--- |--- |--- |
| <img src="assets/do-not-localize/icon_config.svg" width="60px"> | 此步驟必須由管理員執行，該管理員必須持有 [管理許可權](../../administration/using/users-management.md#functional-administrators). | 設定將命名為「購物車放棄」的事件，並發佈此事件設定。 | 將部署您的網站開發人員使用的API，並自動建立交易式訊息。 |

建立和發佈事件的過程會顯示在 [設定異動事件](../../channels/using/configuring-transactional-event.md) 和 [發佈異動事件](../../channels/using/publishing-transactional-event.md) 區段。

### 步驟2 — 編輯並發佈交易式訊息 {#create-transactional-message}

<!--<img src="assets/do-not-localize/icon_notification.svg" width="40px">-->

| 編輯訊息 | 使用者 | 動作 | 結果 |
| --- |--- |--- |--- |
| <img src="assets/do-not-localize/icon_notification.svg" width="40px"> | 此步驟可由行銷使用者執行，該使用者需持 [管理許可權](../../administration/using/users-management.md#functional-administrators). | 編輯及個人化交易式訊息、測試訊息，然後發佈。 | 然後，交易式訊息就準備好可以傳送。 |

有關編輯和發佈交易式訊息的詳細資訊，請參閱 [編輯異動訊息](../../channels/using/editing-transactional-message.md) 和 [異動訊息生命週期](../../channels/using/publishing-transactional-message.md).

### 步驟3 — 整合事件觸發 {#integrate-event-trigger}

<!--<img src="assets/do-not-localize/icon_api.svg" width="55px">-->

建立事件後，您需要將此事件的觸發專案整合至您的網站。<!--In this example, you want a "Cart abandonment" event to be triggered whenever one of your clients leaves your website before purchasing the products in their cart.--> 若要這麼做，您的網站網站開發人員必須使用 **ADOBE CAMPAIGN STANDARD REST API**.

| 實作觸發器 | 使用者 | 動作 | 結果 |
| --- |--- |--- |--- |
| <img src="assets/do-not-localize/icon_api.svg" width="55px"> | 此步驟由您網站的開發人員執行。 | 使用REST異動訊息API將事件整合至您的網站。 | 當使用者端捨棄購物車時，就會觸發此事件。 |

如需使用Campaign REST API管理異動訊息的詳細資訊，請參閱 [REST API檔案](../../api/using/managing-transactional-messages.md).

### 步驟4 — 訊息傳送 {#message-delivery}

<!--<img src="assets/do-not-localize/icon_channels.svg" width="60px">-->

執行上述所有步驟後，即可傳送訊息。

| 傳遞訊息 | 使用者 | 動作 | 結果 |
| --- |--- |--- |--- |
| <img src="assets/do-not-localize/icon_channels.svg" width="60px"> | 此步驟由造訪您網站的客戶執行。 | 當使用者離開網站而未訂購購物車中的產品時，就會觸發對應的Campaign事件。 | 使用者會自動收到通知電子郵件。 |

## 相關主題

* [傳送訊息的重要步驟](../../channels/using/key-steps-to-send-a-message.md)
* [開始使用通訊頻道](../../channels/using/get-started-communication-channels.md)
* [異動推送通知](../../channels/using/transactional-push-notifications.md)
* [後續追蹤訊息](../../channels/using/follow-up-messages.md)
