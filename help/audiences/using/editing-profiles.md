---
title: 編輯設定檔
description: 了解如何編輯現有的設定檔及存取聯絡資訊、慣用管道、追蹤記錄、訂閱等。
audience: audiences
content-type: reference
topic-tags: managing-profiles
feature: Profiles
role: User
level: Intermediate
exl-id: d0c7dc09-6f2b-4336-b545-7afe3a704164
source-git-commit: 13d419c5fc51845ee14f8a3b288f4c467e0a60d9
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 12%

---

# 編輯設定檔{#editing-profiles}

## 存取設定檔屬性 {#accessing-profile-properties}

若要編輯現有設定檔並查詢與其相關聯的資料，或加以修改，步驟如下：

1. 在 Adobe Campaign 首頁，按一下 **[!UICONTROL Customer profiles]** 資訊卡或 **[!UICONTROL Profiles]** 索引標籤。
1. 選取聯絡人。
1. 按一下 **[!UICONTROL Edit profile properties]** 圖示來存取設定檔的詳細資訊。

   ![](assets/profile_creation2.png)

   設定檔的屬性視窗提供數個索引標籤，供您存取所有設定檔資訊。

   其他標籤也可能會根據在Adobe Campaign中建立或擴充的自訂資源而顯示。 如需自訂資源的詳細資訊，請參閱 [關於自訂資源](../../developing/using/data-model-concepts.md).

   >[!NOTE]
   >
   >您只能修改 **[!UICONTROL General]** 標籤 — 除 **[!UICONTROL Traceability]** 區段。

您也可以使用Adobe Campaign Standard API來編輯設定檔。 如需詳細資訊，請參閱[專屬文件](../../api/using/updating-profiles.md)。

相關主題：

* [整合式客戶設定檔](../../audiences/using/integrated-customer-profile.md)
* [在收件者的時區傳送](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)

## 一般設定檔資料 {#general-profile-data}

此 **[!UICONTROL General]** 索引標籤會將下列設定檔的相關資訊分組：

* 聯繫資訊，包含收件者的名字、姓氏、出生日期、照片、首選語言(例如 [多語言電子郵件](../../channels/using/creating-a-multilingual-email.md))等
* 可聯絡設定檔的管道，包含收件者的電子郵件地址、行動電話號碼、選擇退出資訊。
* 郵遞區號( [直接郵件](../../channels/using/about-direct-mail.md))和連絡人的時區(至 [在其時區中排程訊息](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md))。
* 存取授權，指出收件者的組織單位(至 [管理權限](../../administration/using/about-access-management.md))。 也請參閱[分割設定檔](../../administration/using/organizational-units.md#partitioning-profiles)。

![](assets/profile_creation4.png)

## 傳送和追蹤記錄檔 {#sending-and-tracking-logs}

此 **[!UICONTROL Sending logs]** 和 **[!UICONTROL Tracking logs]** 索引標籤會將已傳送至設定檔的傳送清單以及所有相關的追蹤資料分組。

如需傳送和追蹤記錄檔的詳細資訊，請參閱 [傳遞記錄](../../sending/using/monitoring-a-delivery.md#delivery-logs) 和 [追蹤訊息](../../sending/using/tracking-messages.md) 區段。

## 訂閱 {#subscriptions}

聯繫人的訂閱將列在相應的頁簽中。 有關訂閱服務的詳細資訊，請參閱 [本節](../../audiences/using/about-subscriptions.md).

此 **[!UICONTROL Mobile App Subscriptions]** 索引標籤會指推播通知。 如需詳細資訊，請參閱 [推播通知](../../channels/using/about-push-notifications.md) 頻道。
