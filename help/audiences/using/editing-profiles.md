---
title: 編輯設定檔
description: 瞭解如何編輯現有配置檔案並訪問聯繫資訊、首選渠道、跟蹤日誌、訂閱等。
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

## 訪問配置檔案屬性 {#accessing-profile-properties}

要編輯現有配置檔案並參考與其關聯的資料或修改它，請執行以下步驟：

1. 在 Adobe Campaign 首頁，按一下 **[!UICONTROL Customer profiles]** 資訊卡或 **[!UICONTROL Profiles]** 索引標籤。
1. 選取聯絡人。
1. 按一下 **[!UICONTROL Edit profile properties]** 表徵圖以訪問配置檔案的詳細資訊。

   ![](assets/profile_creation2.png)

   配置檔案的屬性窗口提供了幾個頁籤，可訪問所有配置檔案資訊。

   其它頁籤也會根據在Adobe Campaign建立或擴展的自定義資源而出現。 有關自定義資源的詳細資訊，請參見 [關於自定義資源](../../developing/using/data-model-concepts.md)。

   >[!NOTE]
   >
   >您只能修改 **[!UICONTROL General]** 頁籤 **[!UICONTROL Traceability]** 的子菜單。

也可以使用Adobe Campaign StandardAPI進行配置式版本。 如需詳細資訊，請參閱[專屬文件](../../api/using/updating-profiles.md)。

相關主題：

* [整合式客戶設定檔](../../audiences/using/integrated-customer-profile.md)
* [在收件人的時區發送](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)

## 一般配置檔案資料 {#general-profile-data}

的 **[!UICONTROL General]** 頁籤將以下有關配置檔案的資訊分組：

* 聯繫資訊，包含收件人的名字、姓氏、出生日期、照片、首選語言(對於 [多語言電子郵件](../../channels/using/creating-a-multilingual-email.md))等。
* 可以聯繫配置檔案的渠道，其中包含收件人的電子郵件地址、手機號碼和退出選擇資訊。
* 郵政地址(用於 [直接郵件](../../channels/using/about-direct-mail.md))和聯繫人的時區(到 [調度其時區中的消息](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md))。
* 訪問授權，指示收件人的組織單位(到 [管理權限](../../administration/using/about-access-management.md))。 也請參閱[分割設定檔](../../administration/using/organizational-units.md#partitioning-profiles)。

![](assets/profile_creation4.png)

## 發送和跟蹤日誌 {#sending-and-tracking-logs}

的 **[!UICONTROL Sending logs]** 和 **[!UICONTROL Tracking logs]** 頁籤將發送到配置檔案的交貨清單以及所有相關跟蹤資料分組。

有關發送和跟蹤日誌的詳細資訊，請參閱 [交貨日誌](../../sending/using/monitoring-a-delivery.md#delivery-logs) 和 [跟蹤消息](../../sending/using/tracking-messages.md) 的下界。

## 訂閱 {#subscriptions}

聯繫人的訂閱列在相應的頁籤中。 有關訂閱服務的詳細資訊，請參閱 [此部分](../../audiences/using/about-subscriptions.md)。

的 **[!UICONTROL Mobile App Subscriptions]** 頁籤，請參閱推式通知。 有關詳細資訊，請參閱 [推送通知](../../channels/using/about-push-notifications.md) 頻道。
