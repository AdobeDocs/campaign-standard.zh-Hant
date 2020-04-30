---
title: 追蹤訊息
description: 瞭解如何追蹤您的遞送收件者的行為。
page-status-flag: never-activated
uuid: c3721647-0663-4614-a9c9-3b3a40af328a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: sending-and-tracking-messages
discoiquuid: 6fa50f0d-3dcf-4a9e-bccc-1ecda2bfb449
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b8c3569fc3965f463a06ae8375a623553037e248

---


# 追蹤訊息{#tracking-messages}

## 關於追蹤 {#about-tracking}

由於Adobe Campaign的追蹤功能，您可以追蹤遞送收件者的行為。 Adobe Campaign 透過工作階段 Cookie 和永久性 Cookie 實現上述功能。

您可以透過授權要求（例如頁面上出現的）通知使用者您的網站已配備網頁追蹤工具，並加上核取方塊來授權使用Cookie，或在其登陸的第一頁頂端新增橫幅等。 彈出式視窗通常會被瀏覽器封鎖，因此應避免出現。

您的資料庫的每個連絡人都可使用追蹤資訊 **[!UICONTROL integrated customer profiles]**。 如需詳細資訊，請參閱[本小節](../../audiences/using/integrated-customer-profile.md)。

Adobe Campaign 使用兩種類型的 Cookie：

* 工作階段Cookie(nid)。 這包含傳送給連絡人的電子郵件識別碼(broadlogId)和訊息範本的識別碼(deliveryId)。 連絡人按一下由 Adobe Campaign 傳送的電子郵件中包含的 URL 後即可添加識別碼，並且允許您追蹤他們在網路上的行為。瀏覽器關閉時，將自動清除工作階段 Cookie。連絡人可以將其瀏覽器設定為拒絕 Cookie。
* Adobe Experience Cloud解決方案之間共用的Cookie。 這可讓您識別在使用者造訪網站時與Experience Cloud解決方案互動的使用者。 此處提供此Cookie的說 [明](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_mc.html)。

使用Adobe Campaign Standard進行追蹤可讓您存取下列功能：

<table>
<tr>
    <td valign="top">
        <a href="../../administration/using/configuring-email-channel.md#tracking-parameters"><img width="60px" alt="條件" src="assets/icon_email_parameters.png"/></a>
    </td>
    <td valign="top">
        <a href="https://helpx.adobe.com/campaign/kb/push-tracking.html"><img width="60px" alt="條件" src="assets/icon_push_parameters.png"/></a>
    </td>
    <td valign="top">
        <a href="../../designing/using/links.md#about-tracked-urls"><img width="60px" alt="條件" src="assets/icon_url.png"/></a>
    </td>
        <td valign="top">
          <a href="../../sending/using/tracking-messages.md#tracking-logs"><img width="60px" alt="條件" src="assets/icon_log.png"/></a>
    </td>
    </td>
    <td valign="top">
          <a href="../../reporting/using/tracking-indicators.md"><img width="60px" alt="條件" src="assets/icon_report.png"/></a>
</tr>
<tr>
<td>電子郵件追蹤</td>
<td>推播追蹤</td>
<td>追蹤的URL</td>
<td>追蹤記錄檔</td>
<td>追蹤報表</td>
</tr>
</table>

## Tracking logs {#tracking-logs}

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
