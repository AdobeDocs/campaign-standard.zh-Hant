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

您只能透過標準傳送來回應地標資料。 [交易式](../../channels/using/getting-started-with-transactional-msg.md) 訊息無法使用位置資料。

最早的反應是10分鐘。

在此情況下，您會決定傳送電子郵件給過去兩週內造訪過您波士頓商店的所有訂閱者。

1. 建立電子郵件行銷活動。
1. 定義傳送的對象時，將&#x200B;**[!UICONTROL Subscriptions to an application]**&#x200B;元素拖放至工作區中。

   ![](assets/poi_subscriptions_app.png)

   在[定義對象](../../audiences/using/creating-audiences.md)區段中會詳細說明管理對象。

1. 在&#x200B;**[!UICONTROL Add a rule - Profile/Subscriptions to an application]**&#x200B;視窗中，將&#x200B;**[!UICONTROL POI Location Subscription]**&#x200B;元素拖放至工作區。

   ![](assets/poi_add_rule_profile_subscription.png)

1. 在&#x200B;**[!UICONTROL Add a rule - POI Location Subscription]**&#x200B;窗口中，輸入要使用的地標的標籤。

   ![](assets/poi_location_subscription.png)

1. 在 **[!UICONTROL Filter type]** 欄位中，選取 **[!UICONTROL Relative]**。
1. 核取&#x200B;**[!UICONTROL Preceding days]**&#x200B;選項，並在對應欄位中輸入&#x200B;**[!UICONTROL 15]**。
1. 定義使用者必須造訪地標的次數。
1. 按一下&#x200B;**[!UICONTROL Confirm]**&#x200B;以儲存您的對象。

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
