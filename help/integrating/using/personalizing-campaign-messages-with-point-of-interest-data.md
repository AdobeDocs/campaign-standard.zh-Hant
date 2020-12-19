---
solution: Campaign Standard
product: campaign
title: 使用 Point of Interest 資料個人化 Campaign 訊息
description: 瞭解如何透過興趣點資料整合，根據訂閱者的位置建立個人化訊息。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics-for-mobile
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '260'
ht-degree: 10%

---


# 使用 Point of Interest 資料個人化 Campaign 訊息{#personalizing-campaign-messages-with-point-of-interest-data}

在Adobe Campaign中，您可以使用從行動應用程式用戶收集到的地標資料，傳送個人化行銷訊息，例如電子郵件。

您只能對興趣點資料與標準傳送進行回應。 [事務](../../channels/using/getting-started-with-transactional-msg.md) 性消息不能使用位置資料。

你最早能做出反應的時間是10分鐘。

在這種情況下，您決定在過去兩週內，傳送電子郵件給所有造訪過您波士頓商店的訂閱者。

1. 建立電子郵件行銷活動。
1. 定義傳送的對象時，將&#x200B;**[!UICONTROL Subscriptions to an application]**&#x200B;元素拖放至工作區。

   ![](assets/poi_subscriptions_app.png)

   在[定義觀眾](../../audiences/using/creating-audiences.md)區段中會詳細說明管理觀眾。

1. 在&#x200B;**[!UICONTROL Add a rule - Profile/Subscriptions to an application]**&#x200B;窗口中，將&#x200B;**[!UICONTROL POI Location Subscription]**&#x200B;元素拖放到工作區中。

   ![](assets/poi_add_rule_profile_subscription.png)

1. 在&#x200B;**[!UICONTROL Add a rule - POI Location Subscription]**&#x200B;視窗中，輸入您要使用的地標標籤。

   ![](assets/poi_location_subscription.png)

1. 在 **[!UICONTROL Filter type]** 欄位中，選取 **[!UICONTROL Relative]**。
1. 選中&#x200B;**[!UICONTROL Preceding days]**&#x200B;選項，並在相應欄位中輸入&#x200B;**[!UICONTROL 15]**。
1. 定義使用者必須瀏覽地標的次數。
1. 按一下&#x200B;**[!UICONTROL Confirm]**&#x200B;以儲存您的觀眾。

   ![](assets/poi_subscriptions_app_audience_defined.png)

1. 將內容新增至您的電子郵件。

   ![](assets/poi_email_content.png)

1. 確認建立活動以檢視電子郵件的控制面板。
1. 傳送您的訊息。

將會傳送含有10%折扣優惠的電子郵件給下列訂閱者：

* 在過去兩週內，至少造訪過您的波士頓商店一次。
* 在瀏覽期間，將您的行動應用程式至少置於前景中一次。

**相關主題：**

* [建立電子郵件](../../channels/using/creating-an-email.md)
* [定義內容](../../designing/using/personalization.md#example-email-personalization)
* [傳送訊息](../../sending/using/confirming-the-send.md)

