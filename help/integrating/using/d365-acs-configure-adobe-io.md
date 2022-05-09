---
title: 設定 Adobe IO for Microsoft Dynamics 365 整合
description: 瞭解如何為MicrosoftDynamics 365整合配置AdobeIO。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
feature: Microsoft CRM Integration
role: Data Architect
level: Intermediate
exl-id: ab21b694-d05c-4ba4-b828-936803651b82
source-git-commit: 602878233e919d01f3972167cb6d3a1acc4cfc02
workflow-type: tm+mt
source-wordcount: '625'
ht-degree: 2%

---

# Adobe Campaign Standard與MicrosoftDynamics 365整合Adobe I/O配置

本文將介紹如何配置Adobe Campaign Standard和Adobe I/O，使整合應用程式能夠訪問資料。

## 配置Adobe Campaign Standard {#campaign-standard}

### 配置檔案擴展

請在Adobe Campaign Standard啟用「配置檔案擴展」。   這是從MicrosoftDynamics 365同步配置檔案資源中的自定義欄位所必需的。   啟用這些功能的步驟包括：

1. 轉至「設定」 — >「管理」 — >「開發」 — >「發佈」。
1. 按一下「準備發佈」準備發佈。
1. 準備完成後，選中「建立配置檔案和服務Ext API」，然後按一下「發佈」。

## 設定 Adobe I/O {#adobe-io}

Adobe I/O允許您啟用對Adobe Campaign Standard及其他Adobe產品的API訪問。   本文將詳細介紹如何配置Adobe I/O，以便讓Adobe Campaign Standard與MicrosoftDynamics 365整合，以同步資料。

### 概覽

在執行本文中的預整合設定之前，假定您已設定並擁有對組織Campaign Standard實例的管理員訪問權限。  如果沒有發生這種情況，則您需要與Adobe客戶服務部門聯繫以完成市場活動設定。

>[!CAUTION]
>
>以下描述的步驟需要由管理員執行。

### 設定

您需要建立新的AdobeIO項目並配置它以進行整合。

#### 建立新項目

要實現此目標，請按照以下步驟操作：

1. 導航到 [AdobeIO控制台](https://console.adobe.io/home#) 並從螢幕右上角的下拉菜單中選擇Adobe組織ID。

1. 然後按一下 **[!UICONTROL Create new project]** 在 **[!UICONTROL Quick Start]**。

   ![](assets/adobeIO1.png)

1. 下 **[!UICONTROL Get started with your new project]**&#x200B;按一下 **[!UICONTROL Add API]**。

   ![](assets/adobeIO2.png)

1. 選擇Adobe CampaignAPI（您可能需要向下滾動），然後按一下 **[!UICONTROL Next]**。

   ![](assets/adobeIO3.png)

1. 在下一個螢幕上，您可以選擇上載自己的公鑰，或者讓AdobeIO為您生成密鑰對。 這些說明將遵循後一個選項。 如果您決定讓AdobeIO生成密鑰對，請按一下選項1;然後按一下 **[!UICONTROL Generate keypair]** 按鈕

   ![](assets/adobeIO4.png)

1. 在下一螢幕上，系統將提示您命名並選擇密鑰對zip檔案的下載位置。

下載後，您可以解壓縮檔案以顯示公共和私鑰。 AdobeIO已將公鑰應用於您的AdobeIO項目。 您以後需要保留您的私鑰；在整合工具的預整合設定期間將使用私鑰。

1. 按一下 **[!UICONTROL Next]** 繼續

   ![](assets/adobeIO5.png)

1. 在下一個螢幕上，您將選擇要與此項目關聯的產品配置檔案。 選擇標題中包含的產品配置檔案：您的市場活動實例的租戶ID - [!UICONTROL Administrators]

   示例：Campaign Standard — 您的活動 — 租戶ID — 管理員

1. 按一下&#x200B;**[!UICONTROL Save configured API]**。

   ![](assets/adobeIO6.png)

1. 在下一個螢幕中，您將看到新AdobeIO項目的詳細資訊。 按一下 **[!UICONTROL Add to Project]** 在螢幕左上角選擇 **API** 下拉。

   ![](assets/adobeIO7.png)

1. 在下一個螢幕上，您需要選擇I/O事件API，然後按一下 **[!UICONTROL Next]**。

1. 在下一螢幕上按一下 **[!UICONTROL Save the configured API]**。  您將返回到項目詳細資訊螢幕。

1. 現在按一下 **[!UICONTROL Add to Project]** 在螢幕左上角選擇 **API** 像你之前那樣。

1. 在下一個螢幕上，您需要選擇I/O管理API，然後按一下 **[!UICONTROL Next]**。

1. 在下一螢幕上按一下 **[!UICONTROL Save the configured API]**。

市場活動中的預整合設定現已完成。

**相關主題**

* [配置AdobeIO，用於MicrosoftDynamics 365整合](../../integrating/using/d365-acs-configure-adobe-io.md) 是設定整合的下一步
* [整合自助應用程式概述](../../integrating/using/d365-acs-self-service-app-quick-start-guide.md) 包含獲取整合啟動和運行的完整步驟清單。


* [AdobeIO — 服務帳戶整合](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)
* [Campaign Standard- API訪問設定](../../api/using/setting-up-api-access.md)
* [Campaign Standard- Dynamics 365整合](../../integrating/using/d365-acs-configure-d365.md)
