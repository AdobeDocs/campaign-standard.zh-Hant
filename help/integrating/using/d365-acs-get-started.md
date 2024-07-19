---
title: 開始使用Microsoft Dynamics 365整合
description: 瞭解如何開始使用Microsoft Dynamics 365整合
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
source-wordcount: '874'
ht-degree: 4%

---

# 開始使用Microsoft Dynamics 365整合

在跨管道通訊上啟用您的CRM資料：瞭解如何將聯絡人從Microsoft Dynamics 365傳遞到Adobe Campaign，並從Adobe Campaign將行銷活動效能資料（傳送、開啟、點按和退回）分享回Microsoft Dynamics 365。

此整合需要下列軟體版本：

* Microsoft Dynamics 365 for Sales Online，最新版本

* Adobe Campaign Standard，最新版本

>[!CAUTION]
>
>這項功能無法立即在產品中使用。此實作需要 Adobe Consulting 參與。請洽詢您的 Adobe 代表以瞭解更多資訊。
>

## 原則

Adobe Campaign Standard與Microsoft Dynamics 365的整合可同步CRM系統中所有可用的聯絡資料，讓所有相關的聯絡資料都可用於行銷活動。

相反地，當Adobe Campaign Standard中的設定檔與訊息互動時，這些資料（例如：傳送、開啟、點按和跳出）會自動流入Microsoft Dynamics 365，以一併保持聯絡記錄與行銷活動完整。

整合也支援啟用Dynamics 365中的[自訂實體](../../integrating/using/d365-acs-self-service-app-settings.md)，以同步處理至Campaign中對應的&#x200B;**自訂資源**。

此整合旨在支援四個主要使用案例：

1. 將聯絡人從Dynamics 365同步至Campaign，以便在行銷活動中定位他們
1. 將自訂實體從Dynamics 365同步至Campaign，以便用於細分和個人化
1. 從Campaign傳送電子郵件行銷事件（傳送、開啟、點按、跳出）至Dynamics 365，以便顯示在Dynamics 365介面的銷售存放庫
1. 在Dynamics 365和Campaign之間同步選擇退出（例如不透過電子郵件）狀態，以維護客戶隱私權偏好設定。

主要優點包括：

* 銷售與行銷之間有一致的訊息：Adobe Campaign Standard與Dynamics 365整合可讓兩個系統存取客戶分析以及電子郵件行銷記錄，讓所有傳送給客戶的訊息能夠共用相同的一致訊息。

* 所有潛在客戶和客戶資料的整體檢視：透過將Adobe Campaign Standard與Dynamics 365整合，可以從CRM系統內共用和存取每個連絡人的電子郵件行銷記錄。

* 在任何頻道上啟用Dynamics 365資料：有了同步至Adobe Campaign的連絡人資料，您便可以在任何使用Campaign的線上或離線頻道上傳送通訊，包括行動推播、應用程式內、電子郵件或直接郵件。 Campaign「已涵蓋範圍」，無論每個連絡人的偏好頻道為何。

>[!CAUTION]
>
>此整合會將Dynamics 365視為連絡人和自訂實體同步處理的信任來源。  同步屬性的任何變更應在Dynamics 365中進行，而非在Adobe Campaign Standard中進行。  如果在Campaign中進行變更，最終可能會在同步期間覆寫這些變更。
>

## 實作Microsoft Dynamics 365整合的關鍵步驟{#request-and-implement-this-integration}

若要布建此整合，您必須依照下列步驟操作。

請依照下方的流程圖和流程圖詳細資訊，請求並設定整合。

![](assets/provisioning-wf.png)

流程圖詳細資料（對應至上述步驟）：

* **步驟1** — 假設您已擁有或正在取得Microsoft Dynamics 365 for Sales和Adobe Campaign Standard的授權。
* **步驟2** — 標準整合服務可供所有客戶免費使用；不過，可能會根據您的需求支付額外費用。 深入瞭解[最佳實務和限制](../../integrating/using/d365-acs-notices-and-recommendations.md)。 如果原始銷售訂單(SO)中未包含新銷售訂單(SO)，則必須簽署新銷售訂單，才能利用整合。
* **步驟3** — 完成Dynamics 365和Campaign的預先整合步驟。 請參閱[設定此整合](#configure-this-integration)。
* **步驟4** -Adobe入門團隊將讓您存取整合應用程式使用者介面(UI)。
* **步驟5** — 您將能夠設定資料對應、取代、篩選器等。 並從整合應用程式UI內測試您的整合。

  >[!IMPORTANT]
  >
  > 如果您需要雙向或Campaign to Dynamics 365選擇退出設定，您必須向Adobe技術連絡人提出要求，才能在Campaign執行個體上設定選擇退出工作流程。 [了解更多](../../integrating/using/d365-acs-notices-and-recommendations.md#opt-out)。

### 設定此整合 {#configure-this-integration}

針對這項整合需要布建和設定三個系統：

* **Adobe Campaign Standard**：您必須設定API存取許可權，並為整合工具設定新的整合。 若要完成此專案，請參閱[本文章](../../integrating/using/d365-acs-configure-adobe-io.md)。
* **Microsoft Dynamics 365**：您必須建立新的應用程式註冊，並讓應用程式使用者能夠使用整合。  若要針對這項整合設定Microsoft Dynamics 365，請參閱[本文章](../../integrating/using/d365-acs-configure-d365.md)。
* **Adobe Campaign Standard與Microsoft Dynamics 365自助式應用程式整合**：您需要依照[本文章](../../integrating/using/d365-acs-self-service-app-control-access.md)中的步驟操作。

>[!IMPORTANT]
>
>對於每個系統，這些步驟必須由&#x200B;**管理員**&#x200B;執行。
>
>本檔案中的步驟將指導您建立涉及指派許可權和/或管理員存取權的整合/註冊。  您有責任在執行前確保這些步驟符合貴公司的政策，並仔細執行。
>

### 要求支援

支援票證可透過Adobe客戶服務進行記錄。

若有任何整合資料流程的問題，請務必加入下列資訊：

* **處理序擁有者**：工程架構師
* **ES處理序ID**：在上線處理序期間提供
* **處理程式標題**： Microsoft Dynamics 365 / Adobe Campaign Standard整合
* **問題說明**：問題說明

整合支援涵蓋範圍目前是24x5 (週一至週五提供，不包括Adobe假日和休息期間)。
