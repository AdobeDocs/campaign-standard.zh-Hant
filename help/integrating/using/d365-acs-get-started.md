---
title: 開始使用 Microsoft Dynamics 365 整合
description: 瞭解如何開始整合MicrosoftDynamics 365
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

在跨通道通信中激活CRM資料：瞭解如何將聯繫人從MicrosoftDynamics 365傳遞到Adobe Campaign，並共用從Adobe Campaign到MicrosoftDynamics 365的活動績效資料（發送、開啟、按一下和回報）。

此整合需要以下軟體版本：

* MicrosoftDynamics 365僅用於Sales Online，最新版本

* Adobe Campaign Standard，最新版本

>[!CAUTION]
>
>這項功能無法立即在產品中使用。此實作需要 Adobe Consulting 參與。請洽詢您的 Adobe 代表以瞭解更多資訊。

## 原則

Adobe Campaign Standard與MicrosoftDynamics 365的整合使客戶關係管理系統中所有可用的聯繫資料能夠同步，使所有相關的聯繫資料都可用於促銷活動。

相反，當Adobe Campaign Standard內的資料與消息交互時，這些資料(例如：發送、開啟、按一下和退貨)自動流入MicrosoftDynamics 365，以保存與營銷活動相關的聯繫記錄。

整合還支援啟用 [自定義實體](../../integrating/using/d365-acs-self-service-app-settings.md) 在Dynamics 365中同步到 **自定義資源** 在競選中。

此整合旨在支援四個主要使用案例：

1. 將聯繫人從Dynamics 365同步到市場活動，以便在市場營銷活動中鎖定他們
1. 將自定義實體從Dynamics 365同步到市場活動，以便它們可用於細分和個性化
1. 將電子郵件營銷事件（發送、開啟、按一下、退貨）從市場活動發送到Dynamics 365，以顯示到Dynamics 365介面中的銷售儲存庫
1. 在Dynamics 365和「市場活動」之間同步選擇退出（例如，不發送電子郵件）狀態，以維護客戶隱私首選項。

主要好處是：

* 銷售和營銷之間的一致訊息：Adobe Campaign Standard與Dynamics 365整合使系統能夠訪問客戶洞察力和電子郵件營銷歷史，使所有發給客戶的消息能夠共用相同的一致消息。

* 所有潛在客戶和客戶資料的整體視圖：通過將Adobe Campaign Standard與Dynamics 365整合，可以在CRM系統內的每個聯繫人上共用和訪問電子郵件營銷歷史記錄。

* 在任何通道上激活Dynamics 365資料：如果聯繫人資料與Adobe Campaign同步，則可以通過活動（包括移動推送、應用內、電子郵件或直郵）的任何線上或離線渠道發送通信。 無論每個聯繫人的首選渠道如何，市場活動「已覆蓋」。

>[!CAUTION]
>
>此整合將Dynamics 365視為聯繫和自定義實體同步的真相來源。  對同步屬性的任何更改都應在Dynamics 365中完成，而不是在Adobe Campaign Standard。  如果在「市場活動」中進行了更改，則在同步過程中，這些更改最終會被覆蓋。

## 實施MicrosoftDynamics 365整合的關鍵步驟{#request-and-implement-this-integration}

為了配置此整合，您需要執行以下步驟。

請按照下面的流程圖和流程圖詳細資訊請求和配置整合。

![](assets/provisioning-wf.png)

流程圖詳細資訊（映射到上面的步驟）:

* **步驟1**  — 假定您已經或正在購買MicrosoftDynamics 365銷售和Adobe Campaign Standard的許可證。
* **步驟2**  — 標準整合產品對所有客戶免費；但是，可能會根據您的要求產生附加成本。 瞭解有關 [最佳做法和限制](../../integrating/using/d365-acs-notices-and-recommendations.md)。 如果新銷售訂單未包括在原始銷售訂單中，則需要簽署新銷售訂單(SO)以利用整合。
* **步驟3**  — 完成Dynamics 365和市場活動的整合前步驟。 請參閱 [配置此整合](#configure-this-integration)。
* **步驟4** -Adobe入門團隊將為您提供對整合應用程式用戶介面(UI)的訪問。
* **步驟5**  — 您將能夠配置資料映射、替換、篩選器等。 和test整合應用程式UI中的整合。

   >[!IMPORTANT]
   >
   > 如果您需要雙向或「市場活動到Dynamics 365退出選項」配置，則您需要向Adobe技術聯繫人請求在市場活動實例上設定退出工作流。 [了解更多](../../integrating/using/d365-acs-notices-and-recommendations.md#opt-out)。

### 配置此整合 {#configure-this-integration}

需要為此整合配置和配置三個系統：

* **Adobe Campaign Standard**:您需要設定API訪問並配置整合工具的新整合。 要實現此目標，請參閱 [這篇文章](../../integrating/using/d365-acs-configure-adobe-io.md)。
* **Microsoft動力365**:您需要建立新的應用程式註冊，並使應用程式用戶能夠使用整合。  要為此整合配置MicrosoftDynamics 365，請參閱 [這篇文章](../../integrating/using/d365-acs-configure-d365.md)。
* **Adobe Campaign Standard與MicrosoftDynamics 365自助服務應用整合**:您需要執行中的步驟 [這篇文章](../../integrating/using/d365-acs-self-service-app-control-access.md)。

>[!IMPORTANT]
>
>對於每個系統，這些步驟需要由 **管理員**。
>
>本文檔中的步驟將指導您建立涉及分配權限和/或管理員訪問的整合/註冊。  您有責任確保這些步驟在執行之前符合您的公司政策，並認真執行。

### 請求支援

支援票證可以通過Adobe客戶服務進行記錄。

對於整合資料流中的任何問題，請確保包括以下資訊：

* **進程所有者**:工程設計師
* **ES進程ID**:在登機過程中提供
* **流程標題**:MicrosoftDynamics 365/Adobe Campaign Standard整合
* **問題說明**:問題說明

整合支援服務範圍目前為24x5(週一至週五提供，不包括Adobe假日和休息時間)。
