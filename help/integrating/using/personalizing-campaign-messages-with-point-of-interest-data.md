---
title: 使用 Point of Interest 資料個人化 Campaign 訊息
description: 瞭解如何透過興趣點資料整合，根據訂閱者的位置建立個人化訊息。
page-status-flag: 從未激活
uuid: d74c3e55-f130-441b-bc2a-06ddcd5d9784
contentOwner: 紹維亞
products: SG_CAMPAIGN/STANDARD
audience: 整合
content-type: 參考
topic-tags: 使用促銷活動和分析功能以建立行動裝置
discoiquuid: a1736ba3-5121-4d01-bf04-ebb7e701e2e0
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 使用 Point of Interest 資料個人化 Campaign 訊息{#personalizing-campaign-messages-with-point-of-interest-data}

在Adobe Campaign中，您可以使用從行動應用程式用戶收集到的地標資料，傳送個人化行銷訊息，例如電子郵件。

您只能對興趣點資料與標準傳送進行回應。 [事務性消息](../../channels/using/about-transactional-messaging.md) 無法使用位置資料。

你最早能做出反應的時間是10分鐘。

在這種情況下，您決定在過去兩週內，傳送電子郵件給所有造訪過您波士頓商店的訂閱者。

1. 建立電子郵件行銷活動。
1. 定義傳送的對象時，將元素拖放 **[!UICONTROL Subscriptions to an application]** 至工作區。

   ![](assets/poi_subscriptions_app.png)

   「定義觀眾」區段中會詳細 [說明管理觀](../../audiences/using/creating-audiences.md) 眾。

1. 在視窗 **[!UICONTROL Add a rule - Profile/Subscriptions to an application]** 中，將元素拖放 **[!UICONTROL POI Location Subscription]** 至工作區中。

   ![](assets/poi_add_rule_profile_subscription.png)

1. 在窗 **[!UICONTROL Add a rule - POI Location Subscription]** 口中，輸入您要使用的地標標籤。

   ![](assets/poi_location_subscription.png)

1. 在欄位 **[!UICONTROL Filter type]** 中，選擇 **[!UICONTROL Relative]**。
1. 選中該 **[!UICONTROL Preceding days]** 選項並在 **[!UICONTROL 15]** 相應欄位中輸入。
1. 定義使用者必須瀏覽地標的次數。
1. 按一 **[!UICONTROL Confirm]** 下以儲存您的觀眾。

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

