---
title: 使用興趣點資料個人化促銷活動訊息
seo-title: 使用興趣點資料個人化促銷活動訊息
description: 使用興趣點資料個人化促銷活動訊息
seo-description: 瞭解如何根據客戶的興趣點資料整合，建立個人化訊息。
page-status-flag: 從未啓動
uuid: d74c3e55-f130-441b-bc2 a-06ddcd5 d9784
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 整合
content-type: reference
topic-tags: 使用促銷活動與分析-行動-行動
discoiquuid: a1736ba3-512-1d01-bb04-eb7 e701 e2 e0
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 698466596fdacd005dc4d72b8071208c8c39f77d

---


# Personalizing Campaign messages with Point of Interest data{#personalizing-campaign-messages-with-point-of-interest-data}

在Adobe Campaign中，您可以使用從行動應用程式訂閱者收集到的地標資料，傳送個人化行銷訊息，例如電子郵件。

您只能對興趣點資料與標準傳送進行回應。[交易訊息](../../channels/using/about-transactional-messaging.md) 無法使用位置資料。

您最早可以反應10分鐘。

在此情況下，您會決定傳送電子郵件給在過去兩周內瀏覽過您波士頓商店的所有訂閱者。

1. 建立電子郵件行銷活動。
1. When defining the delivery's audience, drag and drop the **[!UICONTROL Subscriptions to an application]** element into the workspace.

   ![](assets/poi_subscriptions_app.png)

   Managing audiences is detailed in the [Defining audiences](../../audiences/using/creating-audiences.md) section.

1. **[!UICONTROL Add a rule - Profile/Subscriptions to an application]** 在視窗中，將 **[!UICONTROL POI Location Subscription]** 元素拖放到工作區中。

   ![](assets/poi_add_rule_profile_subscription.png)

1. **[!UICONTROL Add a rule - POI Location Subscription]** 在視窗中，輸入您想要使用的地標標籤。

   ![](assets/poi_location_subscription.png)

1. In the **[!UICONTROL Filter type]** field, select **[!UICONTROL Relative]**.
1. Check the **[!UICONTROL Preceding days]** option and enter **[!UICONTROL 15]** in the corresponding field.
1. 定義使用者瀏覽地標的次數。
1. Click **[!UICONTROL Confirm]** to save your audience.

   ![](assets/poi_subscriptions_app_audience_defined.png)

1. 將內容新增至您的電子郵件。

   ![](assets/poi_email_content.png)

1. 確認建立活動以檢視電子郵件的控制面板。
1. 傳送您的訊息。

10%折扣優惠的電子郵件將會傳送給下列用戶：

* 在過去兩周內，瀏覽您的波士頓市集至少一次。
* 在此次瀏覽期間，您至少在前景上有一次行動應用程式。

**相關主題：**

* [建立電子郵件](../../channels/using/creating-an-email.md)
* [定義內容](../../designing/using/example--email-personalization.md)
* [傳送訊息](../../sending/using/confirming-the-send.md)

