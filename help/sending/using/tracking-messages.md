---
title: 追蹤訊息
seo-title: 追蹤訊息
description: 追蹤訊息
seo-description: 瞭解如何追蹤您的遞送收件者的行為。
page-status-flag: 從未激活
uuid: c3721647-0663-4614-a9c9-3b3a40af328a
contentOwner: 紹維亞
products: SG_CAMPAIGN/STANDARD
audience: 發送
content-type: 參考
topic-tags: 傳送和追蹤訊息
discoiquuid: 6fa50f0d-3dcf-4a9e-bcc-1ecda2bfb449
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 4084346b537bb483c5519c26d71880d3c57a7e44

---


# 追蹤訊息{#tracking-messages}

## 關於追蹤 {#about-tracking}

由於Adobe Campaign的追蹤功能，您可以追蹤遞送收件者的行為。 為此，Adobe Campaign會使用工作階段Cookie和永久Cookie。

您可以透過授權要求（例如頁面上出現的）通知使用者您的網站已配備網頁追蹤工具，並加上核取方塊來授權使用Cookie，或在其登陸的第一頁頂端新增橫幅等。 彈出式視窗通常會被瀏覽器封鎖，因此應避免出現。

Adobe Campaign使用兩種Cookie:

* 工作階段Cookie(nid)。 這包含傳送給連絡人的電子郵件識別碼(broadlogId)和訊息範本的識別碼(deliveryId)。 當連絡人點按Adobe Campaign所傳送電子郵件中包含的URL，並讓您追蹤其在網路上的行為時，就會加入此URL。 當瀏覽器關閉時，此作業Cookie會自動清除。 連絡人可設定其瀏覽器拒絕Cookie。
* Adobe Experience cloud解決方案之間共用的Cookie。 這可讓您識別在使用者造訪網站時與Experience cloud解決方案互動的使用者。 此Cookie的說明可從以下網址取得： [https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_mc.html](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_mc.html)。

您的資料庫的每個連絡人都可使用追蹤資訊 **[!UICONTROL integrated customer profiles]**。 For more on this, refer to [this section](../../audiences/using/integrated-customer-profile.md).

## 追蹤記錄檔 {#tracking-logs}

標籤 **[!UICONTROL Tracking logs]** 會列出此傳送的追蹤歷史記錄。 此標籤會顯示已傳送訊息的追蹤資訊，例如Adobe Campaign已追蹤的所有URL。 此標籤中的追蹤資訊會每10分鐘更新一次。

>[!NOTE]
>
>如果傳送未啟用追蹤，則不會顯示此標籤。 追蹤記錄檔僅適用於 **電子郵件****和推播** 通知通道。

![](assets/tracking_logs.png)

在上述範例中，收件者：

* 已開啟訊息。
* 按一下「瞭解詳細內容」自訂連結。
* 已按一下取消訂閱和鏡像頁面連結。

在該列 **[!UICONTROL Type]** 中，可能的值為：

* **[!UICONTROL Email click]**:收件者點按了自訂連結。
* **[!UICONTROL Mirror page]**:收件者點按了鏡像頁面的連結。
* **[!UICONTROL Open]**:收件者開啟電子郵件。
* **[!UICONTROL Opt-out]**:收件者按一下取消訂閱的連結。

>[!NOTE]
>
>對於推播 **通知頻道** ，只會追蹤行動通知的點按。 在這種情況下，值將是 **[!UICONTROL Click on mobile notification]**。

如需如何插入追蹤連結的詳細資訊，請參 [閱本頁](../../designing/using/links.md#inserting-a-link)。

## 追蹤的URL {#tracked-urls}

此標 **[!UICONTROL Tracked URLs]** 簽會重新分組傳送訊息中包含的URL，包括其URL類型及其來源URL。

![](assets/sending_delivery6.png)

For more on tracking links, refer to [this section](../../designing/using/links.md#about-tracked-urls).
