---
title: 關於追蹤的URL
seo-title: 關於追蹤的URL
description: 關於追蹤的URL
seo-description: 瞭解如何管理將追蹤的所有內容URL。
page-status-flag: 從未啓動
uuid: dfe5146b-5256-431c-87b3-3c54817ea36
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: design
content-type: reference
topic-tags: 管理連結
discoiquuid: d9b0b3c2-874b-4cb4-bce9-c0144 a19 f25 f
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# About tracked URLs{#about-tracked-urls}

Adobe Campaign可讓您追蹤收件者點按電子郵件中包含的URL時的行為。For more on tracking, see [this section](../../sending/using/tracking-messages.md#about-tracking).

The **[!UICONTROL Links]** icon in the action bar automatically displays the list of all the URLs of your content that will be tracked.

![](assets/des_links.png)

>[!NOTE]
>
>預設會啓用追蹤。如果追蹤已在Adobe Campaign中啓動，則此功能僅適用於電子郵件。For more on the tracking parameters, refer to [this section](../../administration/using/configuring-email-channel.md#tracking-parameters).

可從清單中修改每個連結的URL、類別、標籤和追蹤類型。若要編輯連結，請按一下對應的鉛筆圖示。

![](assets/des_links_tracking.png)

對於每個追蹤的URL，您可以將追蹤模式設定為其中一個值：

* **追蹤**：啓用追蹤此URL。
* **Mirror頁面**：將此URL視為鏡像頁面URL。
* **永不**：絕不會啓動追蹤此URL。儲存此資訊：如果URL再次出現在未來的訊息中，則會自動停用其追蹤。
* **選擇退出**：將此URL視為退出或取消訂閱URL。

![](assets/des_link_tracking_type.png)

您也可以停用或啓用每個URL的追蹤。

>[!NOTE]
>
>By default in Adobe Campaign, all content URLs are tracked except **Mirror page URL** and **Unsubscription** link.

You can regroup your URLs by editing the **[!UICONTROL Category]** field, depending on the URLs used in the message. These categories can be displayed reports, as for example in [URLs and click streams](../../reporting/using/urls-and-click-streams.md).

![](assets/des_link_tracking_category.png)

When building a report, from the **[!UICONTROL Components]** tab, select **[!UICONTROL Dimension]** and scroll down the list to access the tracking components. For example, drag and drop **[!UICONTROL Tracking URL Category]** into the workspace to display results according to the tracking category of each clicked URL.

![](assets/des_link_tracking_report.png)

For more on building customized reports, see [this section](../../reporting/using/about-dynamic-reports.md).
