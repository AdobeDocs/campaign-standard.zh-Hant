---
solution: Campaign Standard
product: campaign
title: 編輯設定檔
description: 瞭解如何編輯現有的設定檔並存取聯絡資訊、偏好的頻道、追蹤記錄、訂閱等。
audience: audiences
content-type: reference
topic-tags: managing-profiles
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 11%

---


# 編輯設定檔{#editing-profiles}

## 訪問配置檔案屬性 {#accessing-profile-properties}

要編輯現有配置式並咨詢與其關聯的資料，或修改它，請執行以下步驟：

1. 在 Adobe Campaign 首頁，按一下 **[!UICONTROL Customer profiles]** 資訊卡或 **[!UICONTROL Profiles]** 索引標籤。
1. 選取聯絡人。
1. 按一下 **[!UICONTROL Edit profile properties]** 圖示以存取描述檔的詳細資訊。

   ![](assets/profile_creation2.png)

   描述檔的屬性視窗提供數個標籤，可讓您存取所有描述檔資訊。

   其他標籤也可能會根據已在Adobe Campaign中建立或擴充的自訂資源而顯示。 如需自訂資源的詳細資訊，請參 [閱關於自訂資源](../../developing/using/data-model-concepts.md)。

   >[!NOTE]
   >
   >您只能修改頁籤中的 **[!UICONTROL General]** 資訊——除部分之 **[!UICONTROL Traceability]** 外。

您也可以使用Adobe Campaign Standard API來建立描述檔版本。 如需詳細資訊，請參閱[專屬文件](../../api/using/updating-profiles.md)。

相關主題：

* [整合式客戶設定檔](../../audiences/using/integrated-customer-profile.md)
* [在收件者的時區傳送](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)

## 一般描述檔資料 {#general-profile-data}

該選 **[!UICONTROL General]** 項卡將以下有關配置檔案的資訊分組：

* 聯絡資訊，其中包含收件者的名字、姓氏、出生日期、像片、慣用語言(適用於多語 [言電子郵](../../channels/using/creating-a-multilingual-email.md)件)等。
* 可連絡描述檔的渠道，其中包含收件者的電子郵件地址、行動電話號碼和退出資訊。
* 郵遞區號( [用於直郵](../../channels/using/about-direct-mail.md))和連絡人的時區(以排 [程其時區的訊息](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md))。
* 存取授權，指出收件者的組織單位(以管 [理權限](../../administration/using/about-access-management.md))。 也請參閱[分割設定檔](../../administration/using/organizational-units.md#partitioning-profiles)。

![](assets/profile_creation4.png)

## Sending and tracking logs {#sending-and-tracking-logs}

此和 **[!UICONTROL Sending logs]** 標籤 **[!UICONTROL Tracking logs]** 會將傳送至描述檔的傳送清單以及所有相關追蹤資料分組。

如需傳送和追蹤記錄檔的詳細資訊，請參 [閱傳送記錄](../../sending/using/monitoring-a-delivery.md#delivery-logs)[檔和追蹤訊息](../../sending/using/tracking-messages.md) 。

## 訂閱 {#subscriptions}

聯繫人的預訂列在相應的頁籤中。 有關訂閱服務的詳細資訊，請參 [閱本節](../../audiences/using/about-subscriptions.md)。

標籤 **[!UICONTROL Mobile App Subscriptions]** 會參照推播通知。 如需詳細資訊，請參閱推 [播通知頻道](../../channels/using/about-push-notifications.md) 。
