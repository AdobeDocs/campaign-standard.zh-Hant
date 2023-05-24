---
title: 使用 Point of Interest 資料個人化 Campaign 訊息
description: 瞭解如何通過興趣點資料整合根據訂閱者的位置建立個性化消息。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics-for-mobile
feature: Audiences
role: Data Architect
level: Intermediate
exl-id: fcc79829-902d-4547-87c5-8a213e1257b7
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '260'
ht-degree: 10%

---

# 使用 Point of Interest 資料個人化 Campaign 訊息{#personalizing-campaign-messages-with-point-of-interest-data}

在Adobe Campaign，您可以使用從移動應用程式訂閱者收集的興趣點資料向他們發送個性化營銷資訊，如電子郵件。

您只能對興趣點資料採用標準交貨進行反應。 [事務性消息](../../channels/using/getting-started-with-transactional-msg.md) 無法使用位置資料。

你最早能做出反應大約10分鐘。

在這種情況下，您決定在過去兩週內向所有訪問過您波士頓商店的訂戶發送電子郵件。

1. 建立電子郵件營銷活動。
1. 在定義交付內容的受眾時，拖放 **[!UICONTROL Subscriptions to an application]** 元素。

   ![](assets/poi_subscriptions_app.png)

   管理受眾的詳細資訊 [定義受眾](../../audiences/using/creating-audiences.md) 的子菜單。

1. 在 **[!UICONTROL Add a rule - Profile/Subscriptions to an application]** 窗口，拖放 **[!UICONTROL POI Location Subscription]** 元素。

   ![](assets/poi_add_rule_profile_subscription.png)

1. 在 **[!UICONTROL Add a rule - POI Location Subscription]** 窗口，輸入要使用的興趣點標籤。

   ![](assets/poi_location_subscription.png)

1. 在 **[!UICONTROL Filter type]** 欄位中，選取 **[!UICONTROL Relative]**。
1. 檢查 **[!UICONTROL Preceding days]** 選項，輸入 **[!UICONTROL 15]** 的子菜單。
1. 定義用戶必須訪問興趣點的次數。
1. 按一下 **[!UICONTROL Confirm]** 來拯救你的觀眾。

   ![](assets/poi_subscriptions_app_audience_defined.png)

1. 將內容添加到電子郵件。

   ![](assets/poi_email_content.png)

1. 確認建立活動以查看電子郵件的儀表板。
1. 發送您的消息。

折扣優惠為10%的電子郵件將發送給以下用戶：

* 在過去兩週內至少訪問過你在波士頓的商店一次。
* 在訪問期間，將您的移動應用程式至少置於前台一次。

**相關主題：**

* [建立電子郵件](../../channels/using/creating-an-email.md)
* [定義內容](../../designing/using/personalization.md#example-email-personalization)
* [傳送訊息](../../sending/using/confirming-the-send.md)
