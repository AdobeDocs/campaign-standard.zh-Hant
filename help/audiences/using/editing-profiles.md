---
title: 編輯設定檔
description: 瞭解如何編輯現有設定檔並存取聯絡資訊、偏好的管道、追蹤記錄、訂閱等。
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

若要編輯現有設定檔並查閱與其相關的資料，或修改該設定檔，步驟如下：

1. 在 Adobe Campaign 首頁，按一下 **[!UICONTROL Customer profiles]** 資訊卡或 **[!UICONTROL Profiles]** 索引標籤。
1. 選取聯絡人。
1. 按一下 **[!UICONTROL Edit profile properties]** 圖示來存取設定檔的詳細資訊。

   ![](assets/profile_creation2.png)

   設定檔的屬性視窗提供數個標籤，可讓您存取所有設定檔資訊。

   其他標籤也會根據Adobe Campaign中建立或擴充的自訂資源而顯示。 如需自訂資源的詳細資訊，請參閱 [關於自訂資源](../../developing/using/data-model-concepts.md).

   >[!NOTE]
   >
   >您只能修改 **[!UICONTROL General]** 標籤 — 除了 **[!UICONTROL Traceability]** 區段。

您也可以使用Adobe Campaign Standard API編輯設定檔。 如需詳細資訊，請參閱[專屬文件](../../api/using/updating-profiles.md)。

相關主題：

* [整合式客戶設定檔](../../audiences/using/integrated-customer-profile.md)
* [在收件者的時區傳送](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)

## 一般設定檔資料 {#general-profile-data}

此 **[!UICONTROL General]** 索引標籤會將有關設定檔的下列資訊分組：

* 連絡資訊，包含收件者的名字、姓氏、出生日期、像片、慣用語言(適用於 [多語言電子郵件](../../channels/using/creating-a-multilingual-email.md))等。
* 可連絡設定檔的頻道，包含收件者的電子郵件地址、行動電話號碼、選擇退出資訊。
* 郵寄地址(適用於 [直接郵件](../../channels/using/about-direct-mail.md))，以及連絡人的時區(至 [以時區排程訊息](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md))。
* 存取授權，可指出收件者的組織單位(至 [管理許可權](../../administration/using/about-access-management.md))。 也請參閱[分割設定檔](../../administration/using/organizational-units.md#partitioning-profiles)。

![](assets/profile_creation4.png)

## 傳送和追蹤記錄 {#sending-and-tracking-logs}

此 **[!UICONTROL Sending logs]** 和 **[!UICONTROL Tracking logs]** 索引標籤會將傳送到設定檔的傳遞清單以及所有相關追蹤資料分組。

如需傳送和追蹤記錄的詳細資訊，請參閱 [傳遞記錄](../../sending/using/monitoring-a-delivery.md#delivery-logs) 和 [追蹤訊息](../../sending/using/tracking-messages.md) 區段。

## 訂閱 {#subscriptions}

聯絡人的訂閱會列在對應索引標籤中。 如需訂閱服務的詳細資訊，請參閱 [本節](../../audiences/using/about-subscriptions.md).

此 **[!UICONTROL Mobile App Subscriptions]** 索引標籤參考推播通知。 如需詳細資訊，請參閱 [推播通知](../../channels/using/about-push-notifications.md) 頻道。
