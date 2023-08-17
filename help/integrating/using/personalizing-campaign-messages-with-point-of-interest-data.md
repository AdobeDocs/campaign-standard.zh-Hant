---
title: 使用 Point of Interest 資料個人化 Campaign 訊息
description: 瞭解如何透過Point of Interest資料整合，根據訂閱者的位置建立個人化訊息。
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

在Adobe Campaign中，您可以使用從行動應用程式訂閱者收集的Points of Interest資料，傳送個人化行銷訊息（例如電子郵件）給他們。

您只能對Point of Interest資料使用標準傳遞做出反應。 [異動訊息](../../channels/using/getting-started-with-transactional-msg.md) 無法使用位置資料。

您最快的反應時間約為10分鐘。

在此情況下，您決定傳送電子郵件給過去兩週內造訪您波士頓商店的所有訂閱者。

1. 建立電子郵件行銷活動。
1. 定義傳送的對象時，拖放 **[!UICONTROL Subscriptions to an application]** 元素加入工作區。

   ![](assets/poi_subscriptions_app.png)

   管理受眾的詳細資訊請參閱 [定義對象](../../audiences/using/creating-audiences.md) 區段。

1. 在 **[!UICONTROL Add a rule - Profile/Subscriptions to an application]** 視窗，拖放 **[!UICONTROL POI Location Subscription]** 元素加入工作區。

   ![](assets/poi_add_rule_profile_subscription.png)

1. 在 **[!UICONTROL Add a rule - POI Location Subscription]** 視窗，輸入您要使用之地標的標籤。

   ![](assets/poi_location_subscription.png)

1. 在 **[!UICONTROL Filter type]** 欄位中，選取 **[!UICONTROL Relative]**。
1. 檢查 **[!UICONTROL Preceding days]** 選項並輸入 **[!UICONTROL 15]** 在對應欄位中。
1. 定義使用者必須已造訪興趣點的次數。
1. 按一下 **[!UICONTROL Confirm]** 以儲存您的對象。

   ![](assets/poi_subscriptions_app_audience_defined.png)

1. 新增內容至您的電子郵件。

   ![](assets/poi_email_content.png)

1. 確認建立活動以檢視電子郵件的控制面板。
1. 傳送您的訊息。

包含10%折扣優惠的電子郵件將傳送給以下訂閱者：

* 過去兩週內至少造訪過您位於波士頓的店舖一次。
* 造訪期間至少將行動應用程式置於前景一次。

**相關主題：**

* [建立電子郵件](../../channels/using/creating-an-email.md)
* [定義內容](../../designing/using/personalization.md#example-email-personalization)
* [傳送訊息](../../sending/using/confirming-the-send.md)
