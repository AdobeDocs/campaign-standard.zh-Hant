---
title: 追蹤訊息
description: 瞭解如何跟蹤交付收件人的行為。
audience: sending
content-type: reference
topic-tags: sending-and-tracking-messages
feature: Performance Monitoring
role: User
level: Intermediate
exl-id: fac29bc2-57fa-40f9-a160-cd75f695b91e
source-git-commit: affd4f9716235a283df20de5539e43c4832762f7
workflow-type: tm+mt
source-wordcount: '480'
ht-degree: 29%

---

# 追蹤訊息{#tracking-messages}

## 關於跟蹤 {#about-tracking}

由於其跟蹤功能，Adobe Campaign使您能夠跟蹤您的遞送收件人的行為。 Adobe Campaign 透過工作階段 Cookie 和永久性 Cookie 實現上述功能。

您可以通過授權請求（例如，在頁面上出現）通知用戶您的站點已配備了Web跟蹤工具，並帶有一個複選框來授權使用Cookie，或在其登錄的首頁頂部添加標題等。 快顯視窗通常會被瀏覽器封鎖，因此應避免使用。

跟蹤資訊可用於資料庫的每個聯繫人 **[!UICONTROL integrated customer profiles]**。 如需詳細資訊，請參閱[本章節](../../audiences/using/integrated-customer-profile.md)。

Adobe Campaign 使用兩種類型的 Cookie：

* 會話cookie(nlid)。 這包含發送到聯繫人的電子郵件的標識符(broadlogId)和消息模板的標識符(deliveryId)。 連絡人按一下由 Adobe Campaign 傳送的電子郵件中包含的 URL 後即可添加識別碼，並且允許您追蹤他們在網路上的行為。瀏覽器關閉時，將自動清除工作階段 Cookie。連絡人可以將其瀏覽器設定為拒絕 Cookie。
* Adobe Experience Cloud解決方案之間共用的Cookie。 此 可讓您識別在 Experience Cloud 解決方案造訪網站時與之互動的使用者。 此cookie的說明可用 [這裡](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-mc.html)。

通過Adobe Campaign Standard跟蹤，您可以訪問以下功能：

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
<td>電子郵件跟蹤</td>
<td>推式跟蹤</td>
<td>被追蹤的 URL</td>
<td>追蹤記錄</td>
<td>跟蹤報告</td>
</tr>
</table>

## 追蹤記錄 {#tracking-logs}

的 **[!UICONTROL Tracking logs]** 頁籤列出此交貨的跟蹤歷史記錄。 此頁籤顯示已發送消息的跟蹤資訊，如Adobe Campaign跟蹤的所有URL。 此頁籤中的跟蹤資訊每10分鐘更新一次。

>[!NOTE]
>
>如果未啟用傳遞追蹤，則不會顯示此索引標籤。跟蹤日誌可用於 **電子郵件** 和 **推送通知** 僅通道。

![](assets/tracking_logs.png)

在上例中，收件人：

* 已開啟郵件。
* 已按一下鏡像頁面連結。
* 已按一下「瞭解更多」自定義連結。

在 **[!UICONTROL Type]** 列中的可能值為：

* **[!UICONTROL Email click]**:收件人按一下了自定義連結。
* **[!UICONTROL Mirror page]**:收件人按一下了指向鏡像頁的連結。
* **[!UICONTROL Open]**:收件人開啟了電子郵件。
* **[!UICONTROL Opt-out]**:收件人按一下了取消訂閱連結。

>[!NOTE]
>
>對於 **推送通知** 頻道，只跟蹤移動通知的按一下。 在這種情況下， **[!UICONTROL Click on mobile notification]**。

有關如何插入跟蹤連結的詳細資訊，請參閱 [此頁](../../designing/using/links.md#inserting-a-link)。

的 **[!UICONTROL Tracking indicators]** 報告包含接收電子郵件後跟蹤行為的關鍵指標。 如需關於此項目的詳細資訊，請參閱此[頁面](../../reporting/using/tracking-indicators.md)。

## 被追蹤的 URL {#tracked-urls}

的 **[!UICONTROL Tracked URLs]** 頁籤重新組合已發送消息中包含的URL，包括其URL類型及其源URL。

![](assets/sending_delivery6.png)

有關跟蹤連結的詳細資訊，請參閱 [此部分](../../designing/using/links.md#about-tracked-urls)。
