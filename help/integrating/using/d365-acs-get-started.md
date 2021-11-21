---
title: 開始使用 Microsoft Dynamics 365 整合
description: 了解如何開始使用Microsoft Dynamics 365整合
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
feature: Microsoft CRM Integration
role: Data Architect
level: Intermediate
exl-id: fa0f790d-6a4d-4b83-a51f-f565e9545a1a
source-git-commit: e7fdaa4b1d77afdae8004a88bbe41bbbe75a3f3c
workflow-type: tm+mt
source-wordcount: '842'
ht-degree: 5%

---

# 開始使用 Microsoft Dynamics 365 整合

在跨通道通訊時啟動您的CRM資料：了解如何將連絡人從Microsoft Dynamics 365傳回Adobe Campaign，以及將行銷活動績效資料（傳送、開啟、點按和退信）從Adobe Campaign傳回Microsoft Dynamics 365。

此整合需要下列軟體版本：

* Microsoft Dynamics 365（僅限Sales Online），最新版本

* Adobe Campaign Standard，最新版本

>[!CAUTION]
>
>這項功能無法立即在產品中使用。此實作需要 Adobe Consulting 參與。請洽詢您的 Adobe 代表以瞭解更多資訊。

## 原則

Adobe Campaign Standard與Microsoft Dynamics 365的整合可同步CRM系統中所有可用的聯絡資料，讓所有相關的聯絡資料都可用於促銷活動。

相反地，當Adobe Campaign Standard中的設定檔與訊息互動時，這些資料(例如：傳送、開啟、點按和退信)會自動流入Microsoft Dynamics 365，以保留連絡記錄與行銷活動一併完成。

整合也支援啟用 [自訂實體](../../integrating/using/d365-acs-self-service-app-settings.md) 在Dynamics 365中同步到 **自訂資源** 在Campaign中。

此整合旨在支援四種主要使用案例：

1. 將連絡人從Dynamics 365同步至Campaign，以便在行銷活動中鎖定他們
1. 將自訂實體從Dynamics 365同步至Campaign，以便用於細分和個人化
1. 從Campaign傳送電子郵件行銷事件（傳送、開啟、點按、退信）至Dynamics 365，以顯示至Dynamics 365介面的銷售存放庫
1. 在Dynamics 365和Campaign之間同步選擇退出（例如，請勿傳送電子郵件）狀態，以維護客戶隱私權偏好設定。

主要優點包括：

* 銷售與行銷之間的一致報文傳送：Adobe Campaign Standard與Dynamics 365整合可讓系統存取客戶分析和電子郵件行銷記錄，讓所有傳送給客戶的訊息共用相同的一致訊息。

* 全面了解所有潛在客戶和客戶資料：將Adobe Campaign Standard與Dynamics 365整合後，就能從CRM系統內的每個連絡人共用及存取電子郵件行銷記錄。

* 在任何通道上啟用Dynamics 365資料：透過同步至Adobe Campaign的連絡人資料，可透過Campaign在任何線上或離線頻道上傳送通訊，包括行動推播、應用程式內、電子郵件或直接郵件。 無論每個連絡人偏好的管道為何，促銷活動「已涵蓋您」。

>[!CAUTION]
>
>此整合會將Dynamics 365視為連絡和自訂實體同步的真偽來源。  同步屬性的任何變更應在Dynamics 365中完成，而非在Adobe Campaign Standard中。  如果在Campaign中進行變更，在同步期間最終可能會遭到覆寫。

## 實作Microsoft Dynamics 365整合的關鍵步驟{#request-and-implement-this-integration}

若要布建此整合，您需要遵循下列步驟。

請依照下方的流程圖和流程圖詳細資訊要求並設定整合。

![](assets/provisioning-wf.png)

流程圖詳細資訊（映射到上述步驟）:

* **步驟1**  — 假設您已擁有或正在購買Microsoft Dynamics 365的銷售授權和Adobe Campaign Standard授權。
* **步驟2**  — 標準整合服務對所有客戶免費；但是，可能會根據您的需求產生額外成本。 深入了解 [最佳實務和限制](../../integrating/using/d365-acs-notices-and-recommendations.md). 如果新銷售訂單未包含在原始銷售訂單中，則需要簽署新銷售訂單(SO)，以便利用整合。
* **步驟3** - Dynamics 365和Campaign的完整整合前步驟。 請參閱 [設定此整合](#configure-this-integration).
* **步驟4** -Adobe入門團隊將提供您整合應用程式使用者介面(UI)的存取權。
* **步驟5**  — 您將能夠配置資料映射、替換項、篩選器等。 和從整合應用程式UI中測試您的整合。

   >[!IMPORTANT]
   >
   > 如果您需要Dynamics 365選擇退出設定的雙向或Campaign，則需要向Adobe技術聯絡人提出要求，以便在您的Campaign執行個體上設定選擇退出工作流程。 [深入瞭解](../../integrating/using/d365-acs-notices-and-recommendations.md#opt-out)。

### 設定此整合 {#configure-this-integration}

需要為此整合布建和配置三個系統：

* **Adobe Campaign Standard**:您必須設定API存取權，並設定整合工具的新整合。 若要達成此目標，請參閱 [這篇文章](../../integrating/using/d365-acs-configure-adobe-io.md).
* **Microsoft Dynamics 365**:您需要建立新應用程式註冊，並讓應用程式使用者使用整合。  若要針對此整合設定Microsoft Dynamics 365，請參閱 [這篇文章](../../integrating/using/d365-acs-configure-d365.md).
* **Adobe Campaign Standard與Microsoft Dynamics 365自助應用程式整合**:您需要遵循 [這篇文章](../../integrating/using/d365-acs-self-service-app-control-access.md).

>[!IMPORTANT]
>
>對於每個系統，這些步驟需由 **管理員**.
>
>本檔案中的步驟將引導您建立與指派權限和/或管理員存取權相關的整合/註冊。  您有責任在執行前確保這些步驟符合您的公司政策，並謹慎執行。

### 要求支援

可以透過Adobe客戶服務記錄支援票證。

針對整合資料流程的任何問題，請務必包含下列資訊：

* **進程所有者**:工程架構師
* **ES進程ID**:在上線過程中提供
* **程式標題**:Microsoft Dynamics 365 / Adobe Campaign Standard整合
* **問題說明**:問題說明

整合支援服務目前為24x5(星期一至星期五，不包括Adobe節假日和休息期間)。
