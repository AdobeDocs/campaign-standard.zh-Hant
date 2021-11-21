---
title: 使用 Point of Interest 資料個人化 Campaign 訊息
description: 了解如何透過興趣點資料整合，根據訂閱者的位置建立個人化訊息。
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

在Adobe Campaign中，您可以使用從行動應用程式訂閱者收集的地標資料，傳送個人化行銷訊息，例如電子郵件。

您只能透過標準傳送來回應地標資料。 [交易式訊息](../../channels/using/getting-started-with-transactional-msg.md) 無法使用位置資料。

最早的反應是10分鐘。

在此情況下，您會決定傳送電子郵件給過去兩週內造訪過您波士頓商店的所有訂閱者。

1. 建立電子郵件行銷活動。
1. 定義傳送的對象時，請拖放 **[!UICONTROL Subscriptions to an application]** 元素。

   ![](assets/poi_subscriptions_app.png)

   管理對象在 [定義對象](../../audiences/using/creating-audiences.md) 區段。

1. 在 **[!UICONTROL Add a rule - Profile/Subscriptions to an application]** 窗口，拖放 **[!UICONTROL POI Location Subscription]** 元素。

   ![](assets/poi_add_rule_profile_subscription.png)

1. 在 **[!UICONTROL Add a rule - POI Location Subscription]** 窗口，輸入要使用的地標標籤。

   ![](assets/poi_location_subscription.png)

1. 在 **[!UICONTROL Filter type]** 欄位中，選取 **[!UICONTROL Relative]**。
1. 檢查 **[!UICONTROL Preceding days]** 選項，然後輸入 **[!UICONTROL 15]** 在對應欄位中。
1. 定義使用者必須造訪地標的次數。
1. 按一下 **[!UICONTROL Confirm]** 以儲存您的對象。

   ![](assets/poi_subscriptions_app_audience_defined.png)

1. 將內容新增至您的電子郵件。

   ![](assets/poi_email_content.png)

1. 確認建立活動以檢視電子郵件的控制面板。
1. 傳送您的訊息。

系統會傳送含有10%折扣優惠的電子郵件給以下訂閱者：

* 過去兩週內，你至少去過一次波士頓商店。
* 造訪期間，您的行動應用程式在前景中至少執行一次。

**相關主題：**

* [建立電子郵件](../../channels/using/creating-an-email.md)
* [定義內容](../../designing/using/personalization.md#example-email-personalization)
* [傳送訊息](../../sending/using/confirming-the-send.md)
