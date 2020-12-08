---
solution: Campaign Standard
product: campaign
title: 追蹤訊息
description: 瞭解如何追蹤您的遞送收件者的行為。
audience: sending
content-type: reference
topic-tags: sending-and-tracking-messages
translation-type: tm+mt
source-git-commit: 79e172d08557bfeebd088d8a0e8756c5965318cb
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 追蹤訊息{#tracking-messages}

## 關於追蹤{#about-tracking}

由於Adobe Campaign的追蹤功能，您可以追蹤遞送收件者的行為。 Adobe Campaign 透過工作階段 Cookie 和永久性 Cookie 實現上述功能。

您可以透過授權要求（例如頁面上出現的）通知使用者您的網站已配備網頁追蹤工具，並加上核取方塊來授權使用Cookie，或在其登陸的第一頁頂端新增橫幅等。 彈出式視窗通常會被瀏覽器封鎖，因此應避免出現。

您資料庫的每個連絡人都可取得追蹤資訊至&#x200B;**[!UICONTROL integrated customer profiles]**。 如需詳細資訊，請參閱[本章節](../../audiences/using/integrated-customer-profile.md)。

Adobe Campaign 使用兩種類型的 Cookie：

* 工作階段Cookie(nid)。 這包含傳送給連絡人的電子郵件識別碼(broadlogId)和訊息範本的識別碼(deliveryId)。 連絡人按一下由 Adobe Campaign 傳送的電子郵件中包含的 URL 後即可添加識別碼，並且允許您追蹤他們在網路上的行為。瀏覽器關閉時，將自動清除工作階段 Cookie。連絡人可以將其瀏覽器設定為拒絕 Cookie。
* Adobe Experience Cloud解決方案之間共用的Cookie。 這可讓您識別在使用者造訪網站時與Experience Cloud解決方案互動的使用者。 此Cookie的說明可在[這裡](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-mc.html)取得。

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

## 跟蹤日誌{#tracking-logs}

**[!UICONTROL Tracking logs]**&#x200B;標籤會列出此傳送的追蹤歷史記錄。 此標籤會顯示已傳送訊息的追蹤資訊，例如Adobe Campaign已追蹤的所有URL。 此標籤中的追蹤資訊會每10分鐘更新一次。

>[!NOTE]
>
>如果傳送未啟用追蹤，則不會顯示此標籤。 追蹤記錄檔僅適用於&#x200B;**email**&#x200B;和&#x200B;**推播通知**&#x200B;頻道。

![](assets/tracking_logs.png)

在上述範例中，收件者：

* 已開啟訊息。
* 已按一下鏡像頁連結。
* 按一下「瞭解詳細內容」自訂連結。

在&#x200B;**[!UICONTROL Type]**&#x200B;欄中，可能的值為：

* **[!UICONTROL Email click]**:收件者點按了自訂連結。
* **[!UICONTROL Mirror page]**:收件者點按了鏡像頁面的連結。
* **[!UICONTROL Open]**:收件者開啟電子郵件。
* **[!UICONTROL Opt-out]**:收件者按一下取消訂閱的連結。

>[!NOTE]
>
>對於&#x200B;**推播通知**&#x200B;頻道，僅追蹤行動通知的點按次數。 在這種情況下，值將為&#x200B;**[!UICONTROL Click on mobile notification]**。

如需如何插入追蹤連結的詳細資訊，請參閱[本頁](../../designing/using/links.md#inserting-a-link)。

**[!UICONTROL Tracking indicators]**&#x200B;報表包含在收到電子郵件訊息後追蹤行為的關鍵指標。 如需關於此項目的詳細資訊，請參閱此[頁面](../../reporting/using/tracking-indicators.md)。

## 追蹤的URL {#tracked-urls}

**[!UICONTROL Tracked URLs]**&#x200B;標籤會重新分組已傳送訊息中包含的URL，包括其URL類型及其來源URL。

![](assets/sending_delivery6.png)

如需追蹤連結的詳細資訊，請參閱[本節](../../designing/using/links.md#about-tracked-urls)。
