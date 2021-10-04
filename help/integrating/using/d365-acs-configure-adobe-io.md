---
title: 設定 Adobe IO for Microsoft Dynamics 365 整合
description: 了解如何配置AdobeIO for Microsoft Dynamics 365整合。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
feature: Microsoft CRM Integration
role: Data Architect
level: Intermediate
exl-id: ab21b694-d05c-4ba4-b828-936803651b82
source-git-commit: 7c34df594d4f649f259fb7edd946477f7b8d92d7
workflow-type: tm+mt
source-wordcount: '626'
ht-degree: 2%

---

# Adobe Campaign Standard和Adobe I/O設定，以進行Microsoft Dynamics 365整合

本文將說明如何設定Adobe Campaign Standard和Adobe I/O，讓整合應用程式能存取資料。

## 設定Adobe Campaign Standard {#campaign-standard}

### 設定檔擴充功能

請在Adobe Campaign Standard中啟用「設定檔擴充功能」。   這是從Microsoft Dynamics 365同步之設定檔資源中的自訂欄位所需的選項。   啟用這些功能的步驟如下：

1. 前往「設定 — >管理 — >開發 — >發佈」。
1. 按一下「準備出版物」以準備出版物。
1. 準備完成後，請勾選「建立設定檔與服務Ext API」，然後按一下「發佈」。

## 設定 Adobe I/O {#adobe-io}

Adobe I/O可讓您啟用Adobe Campaign Standard及其他Adobe產品的API存取。   本文將詳細說明如何設定Adobe I/O，以便讓Adobe Campaign Standard與Microsoft Dynamics 365整合具有同步資料的存取權。

### 概覽

在執行本文中的預先整合設定之前，我們假設您已布建，且擁有組織Campaign Standard例項的管理員存取權。  如果尚未發生此情況，則您需要與Adobe客戶服務聯絡，以完成Campaign布建。

>[!CAUTION]
>
>以下所述步驟需要由管理員執行。

### 設定

您需要建立新的AdobeIO項目，並為整合進行配置。

#### 建立新專案

若要這麼做，請遵循下列程式：

1. 導覽至[AdobeIO主控台](https://console.adobe.io/home#)，然後從畫面右上方的下拉式選單中選取您的Adobe IMS組織ID。

1. 然後按一下&#x200B;**[!UICONTROL Quick Start]**&#x200B;下的&#x200B;**[!UICONTROL Create new project]**。

   ![](assets/adobeIO1.png)

1. 在&#x200B;**[!UICONTROL Get started with your new project]**&#x200B;下，按一下&#x200B;**[!UICONTROL Add API]**。

   ![](assets/adobeIO2.png)

1. 選取Adobe Campaign API（您可能需要捲動至底部），然後按一下&#x200B;**[!UICONTROL Next]**。

   ![](assets/adobeIO3.png)

1. 在下一個螢幕上，您將可以選擇上載自己的公鑰，或者讓AdobeIO為您生成密鑰對。 這些指示將遵循後一選項。 如果您決定讓AdobeIO產生金鑰組，請按一下選項1;然後按一下&#x200B;**[!UICONTROL Generate keypair]**&#x200B;按鈕。

   ![](assets/adobeIO4.png)

1. 在下一個畫面中，系統會提示您命名，並選取金鑰組zip檔案的下載位置。

下載後，您可以將檔案解壓縮，以顯示公開和私密金鑰。 AdobeIO已將公鑰應用到AdobeIO項目。 您以後需要保留私密金鑰；在整合工具的預先整合設定期間，將使用私密金鑰。

1. 按一下&#x200B;**[!UICONTROL Next]**&#x200B;以繼續

   ![](assets/adobeIO5.png)

1. 在下一個畫面中，您將選取要與此專案關聯的產品設定檔。 選取標題中包含的產品設定檔：您的Campaign執行個體的租用戶ID - [!UICONTROL Administrators]

   範例：Campaign Standard- your-campaign-tenantID — 管理員

1. 按一下&#x200B;**[!UICONTROL Save configured API]**。

   ![](assets/adobeIO6.png)

1. 在下一個螢幕上，您將看到新AdobeIO項目的詳細資訊。 按一下螢幕左上角的&#x200B;**[!UICONTROL Add to Project]** ，然後從下拉式清單中選取&#x200B;**API**。

   ![](assets/adobeIO7.png)

1. 在下一個畫面中，您需要選取I/O Events API，然後按一下&#x200B;**[!UICONTROL Next]**。

1. 在下一個螢幕上，按一下&#x200B;**[!UICONTROL Save the configured API]**。  系統會將您帶回專案詳細資訊畫面。

1. 現在，按一下畫面左上角的&#x200B;**[!UICONTROL Add to Project]**，並像先前一樣，從下拉式清單中選取&#x200B;**API**。

1. 在下一個螢幕上，您需要選擇I/O管理API，然後按一下&#x200B;**[!UICONTROL Next]**。

1. 在下一個螢幕上，按一下&#x200B;**[!UICONTROL Save the configured API]**。

Campaign中的預先整合設定現在已完成。

**相關主題**

* [配置AdobeIO for Microsoft Dynamics 365整](../../integrating/using/d365-acs-configure-adobe-io.md) 合是設定整合的下一步
* [整合自助服務應用](../../integrating/using/d365-acs-self-service-app-quick-start-guide.md) 程式概述包含啟動及執行整合的完整步驟清單。


* [AdobeIO — 服務帳戶整合](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)
* [Campaign Standard- API存取設定](../../api/using/setting-up-api-access.md)
* [Campaign Standard- Dynamics 365整合](../../integrating/using/d365-acs-configure-d365.md)
