---
title: 編輯設定檔
seo-title: 編輯設定檔
description: 編輯設定檔
seo-description: 瞭解如何編輯現有的設定檔並存取聯絡資訊、偏好的頻道、追蹤記錄、訂閱等。
page-status-flag: 從未激活
uuid: 6fcdb719-6149-48fc-b400-64c24a51487f
contentOwner: 紹維亞
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: 參考
topic-tags: 管理配置檔案
discoiquuid: 8d3ba7bf-90ae-4c6d-aeb-a48572a69f2f
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 94c7649448aff859daaf2bbe9a4d17a5187ac71f

---


# 編輯設定檔{#editing-profiles}

## 訪問配置檔案屬性 {#accessing-profile-properties}

要編輯現有配置式並咨詢與其關聯的資料，或修改它，請執行以下步驟：

1. 在Adobe Campaign首頁中，按一下卡 **[!UICONTROL Customer profiles]** 片或標 **[!UICONTROL Profiles]** 簽。
1. 選擇聯繫人。
1. 按一下 **[!UICONTROL Edit profile properties]** 圖示以存取描述檔的詳細資訊。

   ![](assets/profile_creation2.png)

   描述檔的屬性視窗提供數個標籤，可讓您存取所有描述檔資訊。

   其他標籤也可能會根據已在Adobe Campaign中建立或擴充的自訂資源而顯示。 如需自訂資源的詳細資訊，請參 [閱關於自訂資源](../../developing/using/data-model-concepts.md)。

   >[!NOTE]
   >
   >您只能修改頁籤中的 **[!UICONTROL General]** 資訊——除部分之 **[!UICONTROL Traceability]** 外。

您也可以使用Adobe Campaign Standard API來建立描述檔版本。 如需詳細資訊，請參閱專用 [檔案](https://final-docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#updating-profiles) 。

相關主題：

* [經整合的客戶用戶檔案](../../audiences/using/integrated-customer-profile.md)
* [在收件者的時區傳送](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)

## 一般描述檔資料 {#general-profile-data}

該選 **[!UICONTROL General]** 項卡將以下有關配置檔案的資訊分組：

* 聯絡資訊，其中包含收件者的名字、姓氏、出生日期、像片、慣用語言(適用於多語 [言電子郵](../../channels/using/creating-a-multilingual-email.md)件)等。
* 可連絡描述檔的渠道，其中包含收件者的電子郵件地址、行動電話號碼和退出資訊。
* 郵遞區號( [用於直郵](../../channels/using/about-direct-mail.md))和連絡人的時區(以排 [程其時區的訊息](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md))。
* 存取授權，指出收件者的組織單位(以管 [理權限](../../administration/using/about-access-management.md))。 另請參見 [Partitioning profiles](../../administration/using/organizational-units.md#partitioning-profiles)。

![](assets/profile_creation4.png)

## 傳送和追蹤記錄檔 {#sending-and-tracking-logs}

此和 **[!UICONTROL Sending logs]** 標籤 **[!UICONTROL Tracking logs]** 會將傳送至描述檔的傳送清單以及所有相關追蹤資料分組。

如需傳送和追蹤記錄檔的詳細資訊，請參 [閱傳送記錄](../../sending/using/monitoring-a-delivery.md#delivery-logs)[檔和追蹤訊息](../../sending/using/tracking-messages.md) 。

## 訂閱 {#subscriptions}

聯繫人的預訂列在相應的頁籤中。 有關訂閱服務的詳細資訊，請參 [閱本節](../../audiences/using/about-subscriptions.md)。

標籤 **[!UICONTROL Mobile App Subscriptions]** 會參照推播通知。 如需詳細資訊，請參閱推 [播通知頻道](../../channels/using/about-push-notifications.md) 。
