---
title: 使用Campaign Standard和Microsoft Dynamics 365
description: 瞭解如何使用Campaign Standard和Microsoft Dynamics 365
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 03009c47a66aa1a62c05f632e2a60141a98639d8

---


# 使用Campaign Standard和Microsoft Dynamics 365

在跨通道通訊中啟用您的CRM資料：瞭解如何將Microsoft Dynamics 365的連絡人傳送至Adobe Campaign，並將促銷活動績效資料（傳送、開啟、點按和彈回）從Adobe Campaign共用回Microsoft Dynamics 365。

>[!NOTE]
>
>Microsoft Dynamics 365 / Adobe Campaign Standard整合僅支援 **Microsoft Dynamics 365銷售應用程式** 。

## 優點與使用案例

### 原則

Adobe Campaign與Microsoft Dynamics 365整合可同步CRM系統中所有可用的連絡資料，讓所有相關的連絡資料都可用於促銷活動。

相反地，當Adobe Campaign中的描述檔與訊息互動時，這些資料(例如：傳送、開啟、點按和彈回數)會自動流入Microsoft Dynamics 365，讓連絡人記錄也能與行銷活動一起保存。

最新版整合也新增了對自訂實體的支援，讓Dynamics 365中的自訂實體與促銷活動中對應的自訂實體同步。

此整合旨在支援三個主要使用案例：

1. 將Dynamics 365的連絡人同步至Campaign，以便在行銷促銷活動中鎖定他們
1. 將電子郵件行銷事件（傳送、開啟、點按、彈回）從Campaign傳送至Dynamics 365，以顯示至Dynamics 365介面中的銷售儲存庫
1. 將自訂實體從Dynamics 365同步至Campaign，以便用於細分和個人化

在這裡觀看Dynamics 365-Campaign Standard整合功能 [影片](https://helpx.adobe.com/campaign/kt/acs/using/acs-ms-dynamics-crm-connector-tutorial.html)。

### 主要優點

* 銷售與行銷之間的一致訊息

Adobe Campaign和Microsoft Dynamics 365整合可讓系統存取客戶見解和電子郵件行銷記錄，讓所有傳送給客戶的訊息都能共用相同的一致訊息。

* 全面瞭解所有潛在客戶和客戶資料

透過將Adobe Campaign與Dynamics 365整合，您可以在CRM系統內的每個「連絡人」上分享及存取電子郵件行銷記錄。

* 在任何通道上啟動Dynamics 365資料

透過與Adobe Campaign同步的連絡人資料，您可以透過Campaign透過任何線上或離線通道傳送通訊，包括行動推播、應用程式內、電子郵件或直效郵件。 不論每個「連絡人」偏好的渠道為何，「促銷活動」都會涵蓋您。

>[!CAUTION]
>
>對於「聯繫人」同步，此整合將Dynamics 365視為真實來源。  對同步化連絡人屬性所做的任何變更，應在Dynamics 365中進行，而非在Campaign中。  如果在促銷活動中進行變更，在同步期間最終會覆寫變更。
