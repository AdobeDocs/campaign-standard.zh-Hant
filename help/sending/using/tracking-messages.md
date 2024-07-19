---
title: 追蹤訊息
description: 瞭解如何追蹤傳遞收件者的行為。
audience: sending
content-type: reference
topic-tags: sending-and-tracking-messages
feature: Performance Monitoring
role: User
level: Intermediate
exl-id: fac29bc2-57fa-40f9-a160-cd75f695b91e
source-git-commit: affd4f9716235a283df20de5539e43c4832762f7
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 23%

---

# 追蹤訊息{#tracking-messages}

## 關於追蹤 {#about-tracking}

藉由Adobe Campaign的追蹤功能，您可以追蹤傳遞收件者的行為。 Adobe Campaign 透過工作階段 Cookie 和永久性 Cookie 實現上述功能。

您可以透過授權請求（有時出現在網站頁面中）告知使用者，網站已配備網路追蹤工具並要求使用者點按核取方塊授權使用Cookie，或在使用者登陸的首頁頂端新增橫幅等。 快顯視窗通常會被瀏覽器封鎖，因此應避免使用。

**[!UICONTROL integrated customer profiles]**&#x200B;中每個資料庫連絡人都有追蹤資訊。 如需詳細資訊，請參閱[本章節](../../audiences/using/integrated-customer-profile.md)。

Adobe Campaign 使用兩種類型的 Cookie：

* 工作階段Cookie (nlid)。 這包含傳送到聯絡人之電子郵件的識別碼(broadlogId)，以及訊息範本的識別碼(deliveryId)。 連絡人按一下由 Adobe Campaign 傳送的電子郵件中包含的 URL 後即可添加識別碼，並且允許您追蹤他們在網路上的行為。瀏覽器關閉時，將自動清除工作階段 Cookie。連絡人可以將其瀏覽器設定為拒絕 Cookie。
* 在Adobe Experience Cloud解決方案之間共用的Cookie。 這可讓您識別在Experience Cloud解決方案造訪網站時與之互動的使用者。 此Cookie的說明可在[這裡](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-mc.html)取得。

使用Adobe Campaign Standard進行追蹤可讓您存取下列功能：

<table>
<tr>
    <td valign="top">
        <a href="../../administration/using/configuring-email-channel.md#tracking-parameters"><img width="60px" alt="條件" src="assets/icon_email_parameters.png"/></a>
    </td>
    <td valign="top">
        <a href="../../administration/using/push-tracking.md"><img width="60px" alt="條件" src="assets/icon_push_parameters.png"/></a>
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
<td>被追蹤的 URL</td>
<td>追蹤記錄</td>
<td>追蹤報告</td>
</tr>
</table>

## 追蹤記錄 {#tracking-logs}

**[!UICONTROL Tracking logs]**&#x200B;索引標籤會列出此傳遞的追蹤記錄。 此索引標籤會顯示已傳送訊息的追蹤資訊，例如Adobe Campaign已追蹤的所有URL。 此標籤中的追蹤資訊每10分鐘更新一次。

>[!NOTE]
>
>如果沒有為傳送啟用追蹤，此索引標籤就不會顯示。 追蹤記錄僅適用於&#x200B;**電子郵件**&#x200B;及&#x200B;**推播通知**&#x200B;頻道。

![](assets/tracking_logs.png)

在上述範例中，收件者：

* 已開啟訊息。
* 按一下映象頁面連結。
* 按一下「瞭解更多」自訂連結。

在&#x200B;**[!UICONTROL Type]**&#x200B;欄中，可能的值為：

* **[!UICONTROL Email click]**：收件者點選自訂連結。
* **[!UICONTROL Mirror page]**：收件者按一下映象頁面的連結。
* **[!UICONTROL Open]**：收件者已開啟電子郵件。
* **[!UICONTROL Opt-out]**：收件者已點選取消訂閱連結。

>[!NOTE]
>
>對於&#x200B;**推播通知**&#x200B;頻道，僅追蹤行動通知的點按。 在此情況下，值為&#x200B;**[!UICONTROL Click on mobile notification]**。

如需如何插入追蹤連結的詳細資訊，請參閱[此頁面](../../designing/using/links.md#inserting-a-link)。

**[!UICONTROL Tracking indicators]**&#x200B;報告包含接收電子郵件訊息後追蹤行為的關鍵指標。 如需關於此項目的詳細資訊，請參閱此[頁面](../../reporting/using/tracking-indicators.md)。

## 被追蹤的 URL {#tracked-urls}

**[!UICONTROL Tracked URLs]**&#x200B;索引標籤會重新分組已傳送訊息中包含的URL，包括其URL型別和來源URL。

![](assets/sending_delivery6.png)

如需追蹤連結的詳細資訊，請參閱[本節](../../designing/using/links.md#about-tracked-urls)。
