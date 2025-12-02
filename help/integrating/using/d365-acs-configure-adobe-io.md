---
title: 設定Adobe Developer以進行Microsoft Dynamics 365整合
description: 瞭解如何設定Adobe Developer以進行Microsoft Dynamics 365整合
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
feature: Microsoft CRM Integration
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: ab21b694-d05c-4ba4-b828-936803651b82
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '568'
ht-degree: 0%

---

# Microsoft Dynamics 365整合的Adobe Campaign Standard和Adobe Developer設定

本文會說明如何設定Adobe Campaign Standard和Adobe I/O，讓整合應用程式可存取資料。

## 設定Adobe Campaign Standard {#campaign-standard}

### 設定檔擴充功能

請在Adobe Campaign Standard中啟用「設定檔擴充功能」。   這是為了使設定檔資源中的自訂欄位從Microsoft Dynamics 365同步。   啟用步驟如下：

1. 請至[設定] -> [管理] -> [開發] -> [發佈]。
1. 按一下「準備出版物」以準備出版物。
1. 準備完成後，請勾選「建立設定檔與服務擴充功能API」，然後按一下「發佈」。

## 設定Adobe I/O {#adobe-io}

Adobe I/O可讓您啟用Adobe Campaign Standard及其他Adobe產品的API存取權。   本文會詳細說明如何設定Adobe I/O，以授予Adobe Campaign Standard整合與Microsoft Dynamics 365的存取權，進而同步資料。

### 概觀

執行本文中的預先整合設定前，假設您已布建並擁有貴組織的Campaign Standard執行個體的管理員存取權。  如果尚未發生此情況，則您需要聯絡Adobe客戶服務以完成Campaign布建。

>[!CAUTION]
>
>管理員需要執行下述步驟。

### 設定

您需要建立新的Adobe Developer專案，並設定以進行整合。

#### 建立新專案

請依照下列程式來達成此目的：

1. 導覽至[Adobe Developer Console](https://console.adobe.io/home#)，並從畫面右上方的下拉式選單中選取您的Adobe組織ID。

1. 然後按一下&#x200B;**[!UICONTROL Create new project]**&#x200B;下的&#x200B;**[!UICONTROL Quick Start]**。

   ![](assets/adobeIO1.png)

1. 在&#x200B;**[!UICONTROL Get started with your new project]**&#x200B;底下，按一下&#x200B;**[!UICONTROL Add API]**。

   ![](assets/adobeIO2.png)

1. 選取Adobe Campaign並按一下&#x200B;**[!UICONTROL Next]**。

   ![](assets/adobeIO3.png)

1. 在下一個畫面中，您可以選擇驗證型別。 您可以選擇OAuth伺服器對伺服器或服務帳戶(JWT)。 請注意，系統不再建議將服務帳戶(JWT)認證用於新專案，並且已取代使用較新的OAuth伺服器對伺服器認證。 本指南提供的指示僅適用於OAuth伺服器對伺服器驗證。

   ![](assets/adobeIO4.png)

1. 在下一個畫面中，您將選取要與此專案關聯的產品設定檔。 選取標題中包含的產品設定檔：您Campaign執行個體的租使用者ID - [!UICONTROL Administrators]

   範例： Campaign Standard - your-campaign-tenantID — 管理員

1. 按一下 **[!UICONTROL Save configured API]**。

   ![](assets/adobeIO5.png)

1. 在下一個畫面中，您將會看到新Adobe Developer專案的詳細資料。 按一下畫面左上方的&#x200B;**[!UICONTROL Add to Project]**，然後從下拉式清單中選取&#x200B;**API**。

   ![](assets/adobeIO6.png)

1. 在下一個畫面中，您必須選取I/O Events API，然後按一下&#x200B;**[!UICONTROL Next]**。

1. 在下一個畫面中按一下&#x200B;**[!UICONTROL Save the configured API]**。  系統將會帶您返回專案詳細資訊畫面。

1. 現在，請按一下畫面左上方的&#x200B;**[!UICONTROL Add to Project]**，並從下拉式清單中選取&#x200B;**API**，就像您先前所做的一樣。

1. 在下一個畫面中，您必須選取I/O Management API，然後按一下&#x200B;**[!UICONTROL Next]**。

1. 在下一個畫面中按一下&#x200B;**[!UICONTROL Save the configured API]**。

Campaign中的預先整合設定現已完成。

**相關主題**

* [設定Adobe Developer以進行Microsoft Dynamics 365整合](../../integrating/using/d365-acs-configure-adobe-io.md)是設定整合的下一個步驟
* [整合自助應用程式概述](../../integrating/using/d365-acs-self-service-app-quick-start-guide.md)包含啟動並執行整合的完整步驟清單。
* [Adobe Developer — 服務帳戶整合](https://developer.adobe.com/developer-console/docs/guides/#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)
* [Campaign Standard - API存取設定](../../api/using/setting-up-api-access.md)
* [Campaign Standard - Dynamics 365整合](../../integrating/using/d365-acs-configure-d365.md)
* [將認證從JWT移轉至OAuth伺服器對伺服器](../../integrating/using/d365-acs-self-service-app-migrate-credentials.md)包含將認證從JWT移轉至OAuth伺服器對伺服器的步驟。
