---
title: 設定Adobe Developer以進行Microsoft Dynamics 365整合
description: 瞭解如何設定Adobe Developer以進行Microsoft Dynamics 365整合
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
feature: Microsoft CRM Integration
role: Data Architect
level: Intermediate
exl-id: ab21b694-d05c-4ba4-b828-936803651b82
source-git-commit: bee4da592e0b3727949bc44c6e41b81d4e7e73d4
workflow-type: tm+mt
source-wordcount: '625'
ht-degree: 1%

---

# 適用於Microsoft Dynamics 365整合的Adobe Campaign Standard和Adobe Developer設定

本文會說明如何設定Adobe Campaign Standard和Adobe I/O，讓整合應用程式可存取資料。

## 設定Adobe Campaign Standard {#campaign-standard}

### 設定檔擴充功能

請在Adobe Campaign Standard中啟用「設定檔擴充功能」。   若要從Microsoft Dynamics 365同步設定檔資源中的自訂欄位，則需要此專案。   啟用步驟如下：

1. 請至[設定] -> [管理] -> [開發] -> [發佈]。
1. 按一下「準備出版物」以準備出版物。
1. 準備完成後，請勾選「建立設定檔與服務擴充功能API」，然後按一下「發佈」。

## 設定 Adobe I/O {#adobe-io}

Adobe I/O可讓您啟用Adobe Campaign Standard及其他Adobe產品的API存取權。   本文會詳細說明如何設定Adobe I/O，以授予Adobe Campaign Standard整合與Microsoft Dynamics 365的存取權，進而同步資料。

### 概覽

執行本文中的預先整合設定前，假設您已布建且擁有貴組織Campaign Standard例項的管理員存取權。  如果尚未發生此情況，則您必須聯絡Adobe客戶服務，以完成Campaign布建。

>[!CAUTION]
>
>管理員需要執行下述步驟。

### 設定

您需要建立新的Adobe Developer專案，並設定以進行整合。

#### 建立新專案

請依照下列程式來達成此目的：

1. 瀏覽至 [Adobe Developer Console](https://console.adobe.io/home#) 並從畫面右上方的下拉式選單中選取您的Adobe組織ID 。

1. 然後按一下 **[!UICONTROL Create new project]** 在 **[!UICONTROL Quick Start]**.

   ![](assets/adobeIO1.png)

1. 在 **[!UICONTROL Get started with your new project]**，按一下 **[!UICONTROL Add API]**.

   ![](assets/adobeIO2.png)

1. 選取Adobe Campaign API （您可能需要捲動到底部）並按一下 **[!UICONTROL Next]**.

   ![](assets/adobeIO3.png)

1. 在下一個畫面中，您可以選擇上傳自己的公開金鑰或讓Adobe Developer為您產生金鑰組。 這些指示將遵循後一個選項。 如果您決定讓Adobe Developer產生金鑰組，請按一下選項1，然後按一下 **[!UICONTROL Generate keypair]** 按鈕。

   ![](assets/adobeIO4.png)

1. 在下一個畫面中，系統會提示您命名並選取金鑰組zip檔案的下載位置。

下載後，您可以解壓縮檔案以顯示公開和私密金鑰。 Adobe Developer已將公開金鑰套用至您的Adobe Developer專案。 您稍後將需要保留私密金鑰；在整合工具的預先整合設定期間，將會使用私密金鑰。

1. 按一下 **[!UICONTROL Next]** 以繼續

   ![](assets/adobeIO5.png)

1. 在下一個畫面中，您將選取要與此專案關聯的產品設定檔。 選取標題中包含的產品設定檔：您的Campaign執行個體的租使用者ID - [!UICONTROL Administrators]

   範例：Campaign Standard- your-campaign-tenantID — 管理員

1. 按一下&#x200B;**[!UICONTROL Save configured API]**。

   ![](assets/adobeIO6.png)

1. 在下一個畫面中，您將會看到新Adobe Developer專案的詳細資料。 按一下 **[!UICONTROL Add to Project]** ，然後選取「 」 **API** 從下拉式清單。

   ![](assets/adobeIO7.png)

1. 在下一個畫面中，您必須選取I/O Events API ，然後按一下 **[!UICONTROL Next]**.

1. 在下一個畫面中按一下 **[!UICONTROL Save the configured API]**.  系統將會帶您返回專案詳細資訊畫面。

1. 現在按一下 **[!UICONTROL Add to Project]** ，然後選取「 」 **API** 從下拉式清單中（就像您先前做的那樣）。

1. 在下一個畫面中，您必須選取I/O管理API ，然後按一下 **[!UICONTROL Next]**.

1. 在下一個畫面中按一下 **[!UICONTROL Save the configured API]**.

Campaign中的預先整合設定現已完成。

**相關主題**

* [設定Adobe Developer以進行Microsoft Dynamics 365整合](../../integrating/using/d365-acs-configure-adobe-io.md) 是設定整合的下一個步驟
* [整合自助應用程式概述](../../integrating/using/d365-acs-self-service-app-quick-start-guide.md) 包含啟動並執行整合的完整步驟清單。


* [Adobe Developer — 服務帳戶整合](https://developer.adobe.com/developer-console/docs/guides/#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)
* [Campaign Standard- API存取設定](../../api/using/setting-up-api-access.md)
* [Campaign Standard- Dynamics 365整合](../../integrating/using/d365-acs-configure-d365.md)
