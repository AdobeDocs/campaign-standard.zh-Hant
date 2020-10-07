---
title: 開始使用 Microsoft Dynamics 365 整合
description: 瞭解如何開始使用Microsoft Dynamics 365整合
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 開始使用 Microsoft Dynamics 365 整合

在跨通道通訊中啟用您的CRM資料：瞭解如何將Microsoft Dynamics 365的連絡人傳送至Adobe Campaign，並將促銷活動績效資料（傳送、開啟、點按和彈回）從Adobe Campaign共用回Microsoft Dynamics 365。

本節列出支援 [的版本](#support-software-versions)。

>[!CAUTION]
>
>這項功能無法立即在產品中使用。此實作需要 Adobe Consulting 參與。請洽詢您的 Adobe 代表以瞭解更多資訊。

## 原則

Adobe Campaign與Microsoft Dynamics 365整合可同步CRM系統中所有可用的連絡人資料，讓所有相關的連絡人資料都可用於促銷活動。

相反地，當Adobe Campaign中的描述檔與訊息互動時，這些資料(例如：傳送、開啟、點按和彈回數)會自動流入Microsoft Dynamics 365，以便將連絡人記錄與行銷活動一起保存。

整合也支援自訂實體，讓 [Dynamics](../../integrating/using/map-campaign-custom-resources-and-dynamics-365-custom-entities.md) 365中的自訂實體與促銷活動中的對應自訂實體同步。

此整合旨在支援4個主要使用案例：

1. 將Dynamics 365的連絡人同步至Campaign，以便在行銷促銷活動中鎖定他們
1. 將自訂實體從Dynamics 365同步至Campaign，以便用於細分和個人化
1. 將電子郵件行銷事件（傳送、開啟、點按、彈回）從Campaign傳送至Dynamics 365，以顯示至Dynamics 365介面中的銷售儲存庫
1. 在Dynamics 365和ACS之間同步選擇退出（例如，請勿以電子郵件傳送）狀態，以維持客戶的隱私偏好設定。

## 主要優點

* 銷售與行銷之間的一致訊息

Adobe Campaign和Microsoft Dynamics 365整合可讓系統存取客戶見解和電子郵件行銷記錄，讓所有傳送給客戶的訊息都能共用相同的一致訊息。

* 全面瞭解所有潛在客戶和客戶資料

透過將Adobe Campaign與Dynamics 365整合，您可以在CRM系統內的每個連絡人上，分享及存取電子郵件行銷記錄。

* 在任何通道上啟動Dynamics 365資料

透過與Adobe Campaign同步的連絡人資料，您可以透過Campaign透過任何線上或離線通道傳送通訊，包括行動推播、應用程式內、電子郵件或直效郵件。 不論每個連絡人偏好的渠道為何，Campaign都會為您提供服務。

>[!CAUTION]
>
>對於連絡人和自訂實體同步，此整合會將Dynamics 365視為真相來源。  對同步屬性所做的任何變更應在Dynamics 365中進行，而非在促銷活動中。  如果在促銷活動中進行變更，在同步期間最終會覆寫變更。

## 支援軟體版本 {#support-software-versions}

此整合需要下列軟體版本：

* 僅限Microsoft Dynamics 365 for Sales Online，最新版本

* Adobe Campaign Standard，最新版本
