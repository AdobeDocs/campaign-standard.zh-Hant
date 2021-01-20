---
title: 開始使用 Microsoft Dynamics 365 整合
description: 瞭解如何開始使用Microsoft Dynamics 365整合
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
translation-type: tm+mt
source-git-commit: fe5d40235abc33c0ea7e929cd2e69b7030cea0b1
workflow-type: tm+mt
source-wordcount: '854'
ht-degree: 5%

---


# 開始使用 Microsoft Dynamics 365 整合

在跨通道通訊中啟用您的CRM資料：瞭解如何將Microsoft Dynamics 365的連絡人傳送至Adobe Campaign，並將促銷活動績效資料（傳送、開啟、點按和彈回）從Adobe Campaign共用回Microsoft Dynamics 365。

此整合需要下列軟體版本：

* 僅限Microsoft Dynamics 365 for Sales Online，最新版本

* Adobe Campaign Standard，最新版本

>[!CAUTION]
>
>這項功能無法立即在產品中使用。此實作需要 Adobe Consulting 參與。請洽詢您的 Adobe 代表以瞭解更多資訊。


## 原則

Adobe Campaign Standard與Microsoft Dynamics 365的整合可讓CRM系統中所有可用的連絡人資料同步化，讓所有相關的連絡人資料都可用於促銷活動。

相反地，當Adobe Campaign Standard中的描述檔與訊息互動時，這些資料(例如：傳送、開啟、點按和彈回數)會自動流入Microsoft Dynamics 365，以便將連絡人記錄與行銷活動一起保存。

此整合也支援讓Dynamics 365中的[自訂實體](../../integrating/using/d365-acs-self-service-app-settings.md)與促銷活動中對應的&#x200B;**自訂資源**&#x200B;同步。

此整合旨在支援4個主要使用案例：

1. 將Dynamics 365的連絡人同步至Campaign，以便在行銷促銷活動中鎖定他們
1. 將自訂實體從Dynamics 365同步至Campaign，以便用於細分和個人化
1. 將電子郵件行銷事件（傳送、開啟、點按、彈回）從Campaign傳送至Dynamics 365，以顯示至Dynamics 365介面中的銷售儲存庫
1. 在Dynamics 365和Campaign之間同步退出（例如，請勿以電子郵件傳送）狀態，以維護客戶隱私權偏好設定。

主要優點包括：

* 銷售與行銷之間的一致訊息：adobe Campaign Standard與Dynamics 365整合，讓系統可存取客戶見解和電子郵件行銷記錄，讓所有傳送給客戶的訊息都能共用相同的一致訊息。

* 全面瞭解所有潛在客戶和客戶資料：透過將Adobe Campaign Standard與Dynamics 365整合，您就可以從CRM系統中分享和存取每位連絡人的電子郵件行銷記錄。

* 在任何通道上啟動Dynamics 365資料：透過與Adobe Campaign同步的連絡人資料，您可以透過Campaign透過任何線上或離線通道傳送通訊，包括行動推播、應用程式內、電子郵件或直效郵件。 促銷活動「已涵蓋您」，不論每個連絡人偏好的管道為何。

>[!CAUTION]
>
>此項整合將Dynamics 365視為連絡與自訂實體同步的真實來源。  對同步化屬性所做的任何變更都應在Dynamics 365中進行，而非在Adobe Campaign Standard中。  如果在促銷活動中進行變更，在同步期間最終會覆寫變更。


## 實施Microsoft Dynamics 365整合的關鍵步驟{#request-and-implement-this-integration}

若要布建此整合，您必須遵循下列步驟。

請依照下面的流程圖和流程圖詳細資訊要求並設定整合。

![](assets/provisioning-wf.png)

流程圖詳細資訊（映射至上述步驟）:

* **步驟1** -假設您已擁有或正在購買Microsoft Dynamics 365的銷售授權和Adobe Campaign Standard授權。
* **步驟2** -標準整合方案對所有客戶都是免費的；不過，視您的需求而定，可能會產生額外成本。進一步瞭解[最佳實務和限制](../../integrating/using/d365-acs-notices-and-recommendations.md)。 如果新銷售訂單未包含在原始SO中，則需要簽署新銷售訂單(SO)才能利用整合。
* **步驟3** - Dynamics 365和Campaign的完整整合前步驟。請參閱[設定此整合](#configure-this-integration)。
* **步驟4** - Adobe入門團隊將提供您整合應用程式使用者介面(UI)的存取權。
* **步驟5**  —— 您將能夠配置資料映射、替換、篩選器等。並在整合應用程式UI中測試您的整合。

   >[!IMPORTANT]
   >
   > 如果您需要Dynamics 365選擇退出設定的雙向或促銷活動，則需要向Adobe技術聯絡人提出要求，以便在您的促銷活動例項上設定選擇退出工作流程。 [進一步瞭解](../../integrating/using/d365-acs-notices-and-recommendations.md#opt-out)。

### 設定此整合{#configure-this-integration}

需要為此整合配置三個系統：

* **Adobe Campaign Standard**:您需要設定API存取權，並為整合工具設定新的整合。若要達成此目的，請參閱[本文](../../integrating/using/d365-acs-configure-adobe-io.md)。
* **Microsoft Dynamics 365**:您需要建立新的應用程式註冊，並讓應用程式使用者能夠使用整合。若要針對此整合設定Microsoft Dynamics 365，請參閱[本文](../../integrating/using/d365-acs-configure-d365.md)。
* **Adobe Campaign Standard與Microsoft Dynamics 365自助服務應用程式整合**:您必須遵循本文中的 [步驟](../../integrating/using/d365-acs-self-service-app-control-access.md)。

>[!IMPORTANT]
>
>對於每個系統，這些步驟都需由&#x200B;**管理員**&#x200B;執行。
>
>本檔案中的步驟將引導您建立整合／註冊，其中涉及指派權限和／或管理存取權。  您有責任確保這些步驟在執行前符合您的公司政策，並謹慎執行。


### 要求支援

您可以使用Adobe客戶服務來記錄支援票證。

對於整合資料流的任何問題，請務必將報表套裝納入問題說明以及下列資訊：

* **流程所有者**:工程設計師
* **ES進程ID**:在上線過程中提供
* **流程標題**:Microsoft Dynamics 365 / Adobe Campaign Standard整合
* **問題說明**:問題說明

整合支援目前提供24x5（星期一至星期五提供，不包括Adobe節假日和中斷時段）。
