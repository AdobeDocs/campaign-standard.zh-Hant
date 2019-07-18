---
title: 編輯描述檔
seo-title: 編輯描述檔
description: 編輯描述檔
seo-description: 瞭解如何編輯現有的設定檔和存取聯絡資訊、偏好的頻道、追蹤記錄、訂閱等。
page-status-flag: 從未啓動
uuid: 6fcdb719-6149-48fc-b400-64c24 a51487 f
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 受眾
content-type: reference
topic-tags: 管理描述檔
discoiquuid: 8d3ba7ff-90ae-4c6d-aaebe@-@a48572 a69 f2 f
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6df0e764750a31f29d6fe3ec4d92e19b3f07f728

---


# Editing profiles{#editing-profiles}

## Accessing profile properties {#accessing-profile-properties}

若要編輯現有描述檔並參考與其相關聯的資料，或加以修改，步驟如下：

1. From the Adobe Campaign home page, click the **[!UICONTROL Customer profiles]** card or the **[!UICONTROL Profiles]** tab.
1. 選取聯絡人。
1. Click the **[!UICONTROL Edit profile properties]** icon to access the profile's detailed information.

   ![](assets/profile_creation2.png)

   描述檔的屬性視窗提供幾個標籤，可讓您存取所有描述檔資訊。

   也可能會顯示其他標籤，視已在Adobe Campaign中建立或擴充的自訂資源而定。For more information about custom resources, see [About custom resources](../../developing/using/data-model-concepts.md).

   >[!NOTE]
   >
   >You can only modify the information in the **[!UICONTROL General]** tab - except for the **[!UICONTROL Traceability]** section.

您也可以使用Adobe Campaign Standard API來建立Profiles Edition。For more on this, refer to the [dedicated documentation](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#updating-profiles) .

相關主題：

* [整合式客戶個人檔案](../../audiences/using/integrated-customer-profile.md)
* [在收件者的時區傳送](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)

## General profile data {#general-profile-data}

**[!UICONTROL General]** 此標籤會將下列資訊分組：

* Contact information, which contains the recipient's first name, last name, date of birth, photo, preferred language (for [multilingual emails](../../channels/using/creating-a-multilingual-email.md)), etc.
* 可與該描述檔連絡的頻道，其中包含收件者的電子郵件地址、行動電話號碼、選擇退出資訊。
* Postal address (for [direct mail](../../channels/using/about-direct-mail.md)), and the contact's time zone (to [schedule messages in its time zone](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)).
* Access authorization, which indicates the recipient's organisational unit (to [manage permissions](../../administration/using/about-access-management.md)). See also [Partitioning profiles](../../administration/using/organizational-units.md#partitioning-profiles).

![](assets/profile_creation4.png)

## Sending and tracking logs {#sending-and-tracking-logs}

**[!UICONTROL Sending logs]****[!UICONTROL Tracking logs]** 標籤群組會群組傳送至描述檔的傳送清單，以及所有相關的追蹤資料。

For more on sending and tracking logs, refer to the [delivery logs](../../sending/using/monitoring-a-delivery.md#delivery-logs) and the [tracking messages](../../sending/using/tracking-messages.md) sections.

## Subscriptions {#subscriptions}

聯絡的訂閱會列在對應的索引標籤中。For more on subscribing to a service, refer to [this section](../../audiences/using/about-subscriptions.md).

**[!UICONTROL Mobile App Subscriptions]** 此標籤參考推播通知。For more information, refer to the [Push notification](../../channels/using/about-push-notifications.md) channel.
