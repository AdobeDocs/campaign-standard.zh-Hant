---
title: 設定 Microsoft Dynamics 365 以進行 Campaign 整合
description: 了解如何設定Microsoft Dynamics 365以進行Campaign整合。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: 57e85f8e-65b4-44ea-98e6-0c555acf6dee
source-git-commit: bee4da592e0b3727949bc44c6e41b81d4e7e73d4
workflow-type: tm+mt
source-wordcount: '913'
ht-degree: 1%

---

# 設定Microsoft Dynamics 365以與Adobe Campaign Standard整合

了解如何設定Microsoft Dynamics 365整合，並在與Adobe Campaign Standard的跨通道通訊時啟用您的CRM資料。

## 概覽

如需Adobe Campaign Standard與Microsoft Dynamics 365整合的一般說明，請參閱 [本頁](../../integrating/using/d365-acs-get-started.md).

需要配置多個應用程式以啟用整合，但本文將重點介紹Dynamics 365中所需的步驟。

## 必要條件

在本檔案中執行預先整合設定之前，我們假設您已布建，且擁有貴組織Microsoft Dynamics 365例項的管理員存取權。  如果尚未發生此情況，則您需要與Microsoft客戶支援聯絡，以完成Dynamics 365布建。

如果您要為測試環境和生產環境配置整合，則需要對您的測試和生產Dynamics 365執行個體執行下列步驟。 如果要配置舞台或生產Dynamics 365實例，則下面的幾個說明會稍有不同(例如，對於生產實例，請為 `<stage or prod>`)

## 設定應用程式和權限

OAuth存取權杖可讓整合工具透過Web API與您的Microsoft Dynamics 365執行個體驗證，以便將Campaign Standard體驗事件張貼至Microsoft Dynamics 365介面的時間軸檢視。

以下影片概述主要步驟：

>[!VIDEO](https://video.tv.adobe.com/v/27637)

若要產生OAuth存取權杖，請依照下列步驟操作。

### 註冊新應用程式 {#register-a-new-app}

1. 在管理員登入下，登入 [portal.azure.com](https://portal.azure.com){target="_blank"}.

1. 按一下 **[!UICONTROL Azure Active Directory]** 左側功能表；然後按一下 **[!UICONTROL App registrations]** 的子菜單上。

1. 按一下 **[!UICONTROL New registration]** 在螢幕頂端。

1. 填寫應用程式註冊畫面：

   * 名稱：adobe campaign `<stage or prod>`
   * 支援的帳戶類型： **[!UICONTROL Accounts in this organizational directory only]** （預設值）

有關建立新應用程式的詳細資訊，請參閱 [本節](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app){target="_blank"}.

>[!NOTE]
>
>Microsoft Azure Directory將唯一應用程式（用戶端）ID指派給您的應用程式。 您稍後在設定Dynamics 365以及執行整合工具設定時，都需要此ID。

### 產生用戶端密碼 {#generate-a-client-secret}

1. 在應用程式概述畫面左側的子功能表中，按一下 **[!UICONTROL Certificates and Secrets > New client secret]**

1. 輸入說明、設定持續時間，然後按一下 **[!UICONTROL OK]**.

您的用戶端密碼現在已建立。 暫時保留值，以完成整合工具的預整合設定。

>[!CAUTION]
>
>視需要保留此值，以完成整合工具的預先整合設定。 之後無法擷取。


### 設定權限

1. 在此畫面或應用程式概述畫面中，按一下 **[!UICONTROL API permissions]** 的子功能表。  按一下 **[!UICONTROL Add a permission]**，您需要選取 **[!UICONTROL Dynamics CRM]** 的下界。

1. 然後勾選 **[!UICONTROL user_impersonation]**，然後按一下 **[!UICONTROL Add permissions]** 按鈕。

有關權限設定的詳細資訊，請參閱 [本節](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-configure-app-access-web-apis#add-permissions-to-access-web-apis){target="_blank"}.

### 建立應用程式使用者

此新使用者是一般使用者。 應用程式將使用：此使用者將會執行使用API對Microsoft Dynamics 365的任何變更。 若要建立，請遵循下列步驟：

1. 導覽至您的Dynamics 365執行個體並以管理員身分登入。

1. 按一下右上角的齒輪圖示，然後按一下 **[!UICONTROL Advanced Settings]**. 在頂端橫幅中，按一下旁邊的下拉式清單 **[!UICONTROL Settings]**，按一下 **[!UICONTROL Security > Users]**.

1. 按一下下拉式功能表，前往 **[!UICONTROL Application Users]**. 按一下&#x200B;**[!UICONTROL New]**。

1. 確保使用者圖示旁的下拉式清單顯示 **[!UICONTROL USER:APPLICATION USER]**.

   為新用戶填寫螢幕。  參數建議：

   * **[!UICONTROL User Name]** （電子郵件）:adobe_api_`<stage-or-prod>`@`<your-d365-hostname>`&quot;(例如， adobe_api_stage@some-company.crm.dynamics.com)
   * **[!UICONTROL Application ID]**:您在Azure AD中註冊的應用程式ID（此為必要項）
   * 您可以保留空白 **[!UICONTROL Application ID URI]** 和 **[!UICONTROL Azure AD Object ID]**
   * **[!UICONTROL Full Name]**:AdobeAPI `<stage or prod>`
   * **[!UICONTROL Email]**:與 **[!UICONTROL User Name]** (或管理員的電子郵件（如果您願意）

   如需建立應用程式使用者的詳細資訊，請參閱 [本節](https://docs.microsoft.com/en-gb/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user){target="_blank"}.

1. 按一下使用者圖示並上傳Adobe Campaign圖示；這是當Dynamics 365中出現新Adobe事件時，將顯示在時間軸視圖中的表徵圖。

1. 按一下「 」，開啟使用者角色清單 **[!UICONTROL MANAGE ROLES]** 在頂部的絲帶里。

1. 向下捲動並選取 **[!UICONTROL System administrator]** 此使用者的存取權。

1. 按一下&#x200B;**[!UICONTROL OK]**。

### 取得租用戶ID {#get-the-tenant-id}

遵循指示 [在本頁](https://docs.microsoft.com/en-us/onedrive/find-your-office-365-tenant-id) 找到您的租用戶ID。  在整合工具的預先整合設定期間，您將需要此ID。

## 安裝Microsoft Dynamics 365的Campaign Standard {#install-appsource-app}

要將Dynamics 365應用程式整合到您的Campaign Standard環境，請執行以下步驟：

1. 導覽至下列連結： [https://appsource.microsoft.com/en-us/marketplace/apps](https://appsource.microsoft.com/en-us/marketplace/apps) 和搜索 _Adobe Campaign for Dynamics 365_ 的下一頁。
或者，您也可以導覽至此 [連結](https://appsource.microsoft.com/en-us/product/dynamics-365/adobecampaign.re4snj-a4n7-5t6y-a14br-d5d1b?flightCodes=adobesignhide&amp;tab=Overview)
{target="_blank"}.
1. 請依照指示安裝Dynamics 365執行個體的應用程式。
1. 安裝後，導航至Dynamics 365實例並以管理員身份登錄。
1. 按一下右上角的齒輪圖示，然後按一下 **[!UICONTROL Advanced Settings]**. 在頂端橫幅中，按一下旁邊的下拉式清單 **[!UICONTROL Settings]**，按一下 **[!UICONTROL Processes]** 在 **[!UICONTROL Process Center]**.
1. 搜尋 **[!UICONTROL Adobe Campaign Email Bounce]** 任務並按一下。
1. 在 **[!UICONTROL Administration]** 標籤中，將擁有者變更為先前建立的AdobeAPI應用程式使用者，方法是按一下 **[!UICONTROL Actions]** 從頂端功能區，然後選取 **[!UICONTROL Assign to another User]** 選項，選擇 **[!UICONTROL Adobe API application user]** 從下拉式清單中指派。
1. 重新啟用程式。
1. 對 **[!UICONTROL Adobe Campaign Email Click]** 任務。

>[!NOTE]
>
>如果您隨時想停用這些程式，可以在此中停用 **[!UICONTROL Processes]** 螢幕。

**相關主題**

* [設定Adobe Developer for Microsoft Dynamics 365整合](../../integrating/using/d365-acs-configure-adobe-io.md) 是設定整合的下一步
* [開始使用自助服務整合應用程式](../../integrating/using/d365-acs-self-service-app-quick-start-guide.md) 包含啟動及執行整合的完整步驟清單。
