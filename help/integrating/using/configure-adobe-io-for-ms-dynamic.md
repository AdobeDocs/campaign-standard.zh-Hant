---
title: 設定 Adobe IO for Microsoft Dynamics 365 整合
description: 瞭解如何設定Adobe IO for Microsoft Dynamics 365整合。
page-status-flag: never-activated
uuid: effa1028-66b2-4bef-b5e4-7319dbb23d5d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
discoiquuid: eb3639f5-7246-46c4-8ddb-da9413b40c32
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0ce73bf7e250c5e88bbb525854e81ef27662ab06
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 3%

---


# 設定 Adobe IO for Microsoft Dynamics 365 整合

在跨通道通訊中啟用您的CRM資料：瞭解在預先整合設定期間建立新Adobe IO專案並針對Microsoft Dynamics 365整合進行設定所需的步驟。

## 概觀

Adobe Campaign Standard - Microsoft Dynamics 365整合在本頁 [中說明](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md)。

在本文中執行預先整合設定之前，我們假定您已布建，並擁有組織「促銷活動標準」例項的管理員存取權。  如果未發生此情況，則您需要聯絡Adobe客戶服務以完成促銷活動布建。

>[!CAUTION]
>
>管理員需要執行下列步驟。

## 設定

您需要建立新的Adobe IO專案，並加以設定以進行整合。

### 建立新專案

若要達成此目的，請依照下列程式：

1. 導覽至 [Adobe IO Console](https://console.adobe.io/home#) ，然後從畫面右上角的下拉式選單中選取您的Adobe IMS組織ID。

1. 然後按一下 **[!UICONTROL Create new project]** 下方 **[!UICONTROL Quick Start]**。

![](assets/adobeIO1.png)

1. 在下 **[!UICONTROL Get started with your new project]**&#x200B;方，按一下 **[!UICONTROL Add API]**。

![](assets/adobeIO2.png)

1. 選取Adobe Campaign API（您可能需要捲動至底部），然後按一下「下一步」。

![](assets/adobeIO3.png)

1. 在下一個畫面中，您可以選擇上傳您自己的公開金鑰，或讓Adobe IO為您產生金鑰對。 這些指示將遵循後一個選項。 如果您決定讓Adobe IO產生金鑰對，請按一下選項1;然後按一下「產生關鍵配對」按鈕。

![](assets/adobeIO4.png)

1. 在下一個畫面中，系統會提示您命名並選取金鑰對zip檔案的下載位置。

下載後，您就可以解壓縮檔案，以顯示公開和私密金鑰。 Adobe IO已將公開金鑰套用至您的Adobe IO專案。 您以後需要保留您的私密金鑰；在整合工具的預先整合設定期間，將會使用私密金鑰。

1. 按一下「下一步」繼續

![](assets/adobeIO5.png)

1. 在下一個畫面中，您將選取要與此專案關聯的產品設定檔。

1. 選取標題中包含的產品設定檔：您的促銷活動例項的租用戶ID - [!UICONTROL Administrators] -範例：Campaign Standard - your-campaign-tenantID —— 管理員

1. 按一下 [!UICONTROL Save configured API]。

![](assets/adobeIO6.png)

1. 在下一個畫面中，您會看到新Adobe IO專案的詳細資訊。

1. 按一下畫面左上角的「新增至專案」，然後從下拉式清單中選取「API」。

![](assets/adobeIO7.png)

1. 在下一個畫面中，您需要選取I/O事件API，然後按一下「下一步」。

1. 在下一個畫面上按一下「儲存已設定的API」。  您將會回到專案詳細資訊畫面。

1. 現在按一下畫面左上角的「新增至專案」，然後從下拉式清單中選取「API」，就像您先前所做的一樣。

1. 在下一個畫面中，您需要選擇I/O管理API，然後按一下「下一步」。

1. 在下一個畫面上按一下「儲存已設定的API」。

促銷活動中的預先整合設定現在已完成。  繼續完成 [Microsoft Dynamics 365的預先整合設定](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md)。

**相關主題**

* [Adobe IO —— 服務帳戶整合](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)
* [促銷活動標準- API存取設定](../../api/using/setting-up-api-access.md)
* [Campaign Standard - Dynamics 365整合](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md)