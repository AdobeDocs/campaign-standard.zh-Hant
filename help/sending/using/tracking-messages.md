---
title: 追蹤訊息
seo-title: 追蹤訊息
description: 追蹤訊息
seo-description: 瞭解如何追蹤傳送收件者的行為。
page-status-flag: 從未啓動
uuid: c3721647-0663-4614-a9 c9-3b3 a40 af328 a
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 傳送
content-type: reference
topic-tags: 傳送與追蹤訊息
discoiquuid: 6fa50f0d-3df-4a9e-bcc-1eda2 bfb449
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a12df43de55dedf388a397fbf4670d99e3ea7f3d

---


# Tracking messages{#tracking-messages}

## About tracking {#about-tracking}

Adobe Campaign具備追蹤功能，可讓您追蹤傳送收件者的行為。若要這麼做，Adobe Campaign會使用作業Cookie和永久性Cookie。

您可以通知使用者您的網站已透過授權要求(例如在頁面上出現)提供網頁追蹤工具(例如在頁面上啓用)，以授權使用Cookie，或在登陸第一頁上方新增橫幅廣告等等。應避免快顯視窗，因為它們通常被瀏覽器封鎖。

Adobe Campaign使用兩種Cookie類型：

* 作業Cookie(nld)。其中包含傳送給聯絡人(BroadLogID)的電子郵件識別碼，以及訊息範本(傳送ID)的識別碼。當聯絡人按一下Adobe Campaign傳送的電子郵件中所包含的URL，並讓您追蹤他們在網頁上的行為時，就會新增此資訊。當瀏覽器關閉時，此作業Cookie會自動清除。聯絡人可以設定其瀏覽器拒絕Cookie。
* Adobe Experience Cloud解決方案之間共用的Cookie。這可讓您識別使用者造訪網站時與Experience Cloud解決方案互動的使用者。The description of this cookie is available here: [https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_mc.html](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_mc.html).

Tracking information are available for each contact of your database into **[!UICONTROL integrated customer profiles]**. For more on this, refer to [this section](../../audiences/using/integrated-customer-profile.md).

## Tracking logs {#tracking-logs}

**[!UICONTROL Tracking logs]** 此標籤會列出此傳送的追蹤記錄。此標籤會顯示傳送訊息的追蹤資訊，例如所有已由Adobe Campaign追蹤的URL。此標籤中的追蹤資訊每10分鐘更新一次。

>[!NOTE]
>
>如果未針對傳送啓用追蹤，則不會顯示此標籤。Tracking logs are available for the **email** and **push notification** channels only.

![](assets/tracking_logs.png)

在上方範例中，收件者：

* 開啓訊息。
* 按一下「瞭解更多」自訂連結。
* 點按取消訂閱和鏡像頁面連結。

**[!UICONTROL Type]** 在欄中，可能的值為：

* **[!UICONTROL Email click]**：收件者點按了自訂連結。
* **[!UICONTROL Mirror page]**：收件者點按了鏡像頁面的連結。
* **[!UICONTROL Open]**：收件者開啓電子郵件。
* **[!UICONTROL Opt-out]**：收件者點按取消訂閱連結。

>[!NOTE]
>
>**對於推播通知** 頻道，只會追蹤行動通知上的點按。**[!UICONTROL Click on mobile notification]**&#x200B;在這種情況下，值將會是。

For more on how to insert tracking links, refer to [this page](../../designing/using/inserting-a-link.md).

## Tracked URLs {#tracked-urls}

**[!UICONTROL Tracked URLs]** 標籤會重新整理傳送的訊息中包含的URL，包括其URL類型及其來源URL。

![](assets/sending_delivery6.png)

For more on tracking links, refer to [this section](../../designing/using/about-tracked-urls.md).
