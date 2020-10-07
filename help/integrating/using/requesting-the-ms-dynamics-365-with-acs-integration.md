---
title: 要求並設定 Microsoft Dynamics 365 整合
description: 瞭解如何透過Campaign Standard整合來請求及設定Microsoft Dynamics 365
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 要求並設定 Microsoft Dynamics 365 整合

若要布建此整合，您必須遵循下列步驟。

請依照下面的流程圖和流程圖詳細資訊要求並設定整合。

![](assets/provisioning-wf.png)

流程圖詳細資訊（映射至上述步驟）:

* **步驟1** —— 假設您已擁有或正在購買Microsoft Dynamics 365的銷售授權和Adobe Campaign Standard授權。

* **步驟2** —— 標準整合方案對所有客戶都是免費的；不過，視您的需求而定，可能會產生額外成本(請參閱 [整合護欄和界限](../../integrating/using/ms-dynamics-365-integration-guardrails.md))。 需要簽署新的銷售訂單，才能運用整合。

* **步驟3** - Dynamics 365和Campaign的完整整合前步驟。 請參 [閱設定此整合](#configure-this-integration)。

* **步驟4-7** - Adobe入門團隊將會與您合作完成入門程式。

## 設定此整合 {#configure-this-integration}

需要為此整合配置三個系統：Adobe Campaign Standard、Microsoft Dynamics 365 for Sales和整合工具。 設定文章會連結在下方。

>[!CAUTION]
>
>對於每個系統，這些步驟都需由管理員執行。
>
>下列文章中的步驟將引導您建立整合／註冊，其中涉及指派權限和／或管理存取權。  您有責任確保這些步驟在執行前符合您的公司政策，並謹慎執行。

在ADOBE CAMPAIGN中，您必須設定API存取權，並設定整合工具的新整合。 若要達成此目的，請參 [閱本文](../../integrating/using/configure-adobe-io-for-ms-dynamic.md)。

在MICROSOFT DYNAMICS 365中，您需要建立新的應用程式註冊，並讓應用程式使用者能夠使用整合。  若要針對此整合設定Microsoft Dynamics 365，請參閱 [本文](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md)。

您必須與Adobe入門團隊合作，以設定入口、出口和退出資料流的設定。


## 要求支援

支援票證可以照常使用Adobe Custom Care進行記錄；客戶服務將視需要引進支援人員。

對於整合資料流的任何問題，請務必將報表套裝納入問題說明以及下列資訊：

* **流程所有者**:工程設計師

* **ES進程ID**:在上線過程中提供

* **流程標題**:Dynamics 365 / Adobe Campaign Standard整合

* **問題說明**:問題說明

整合支援目前提供24x5（星期一至星期五提供，不包括Adobe節假日和中斷時段）。