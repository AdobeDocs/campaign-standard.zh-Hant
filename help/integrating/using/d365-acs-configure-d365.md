---
title: 設定Microsoft Dynamics 365以進行Campaign整合
description: 瞭解如何設定Microsoft Dynamics 365以進行Campaign整合。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: 57e85f8e-65b4-44ea-98e6-0c555acf6dee
source-git-commit: 6947d163119dd6fc5966fdc723530b02bdd4a469
workflow-type: tm+mt
source-wordcount: '879'
ht-degree: 0%

---

# 設定Microsoft Dynamics 365以與Adobe Campaign Standard整合

瞭解如何設定Microsoft Dynamics 365整合，以及透過Adobe Campaign Standard進行跨管道通訊時啟用您的CRM資料。

## 概覽

在[本頁面](../../integrating/using/d365-acs-get-started.md)中說明Adobe Campaign Standard與Microsoft Dynamics 365整合的一般說明。

您必須設定多個應用程式才能啟用整合，不過，本文章將著重介紹Dynamics 365中所需的步驟。

## 先決條件

在此檔案中執行預先整合設定前，假設您已布建並擁有貴組織的Microsoft Dynamics 365執行個體的管理員存取權。  如果尚未發生此情況，則您必須聯絡Microsoft客戶支援以完成Dynamics 365布建。

如果您要設定測試和生產環境的整合，則需要針對測試和生產Dynamics 365執行個體執行以下步驟。 若您正在設定階段或生產Dynamics 365執行個體，以下的一些指示會稍有不同（例如，對於生產執行個體，請為`<stage or prod>`選取「prod」）

## 設定應用程式和許可權

OAuth存取權杖可讓整合工具透過網頁API向您的Microsoft Dynamics 365執行個體進行驗證，以便將Campaign Standard體驗事件發佈到Microsoft Dynamics 365介面的時間軸檢視。

主要步驟概述於下列影片中：

>[!VIDEO](https://video.tv.adobe.com/v/27637)

若要產生OAuth存取權杖，請遵循下列步驟。

### 註冊新的應用程式 {#register-a-new-app}

1. 在您的系統管理員登入下，登入[portal.azure.com](https://portal.azure.com){target="_blank"}。

1. 按一下左側功能表中的&#x200B;**[!UICONTROL Azure Active Directory]**，然後在出現的子功能表上按一下&#x200B;**[!UICONTROL App registrations]**。

1. 按一下熒幕上方的&#x200B;**[!UICONTROL New registration]**。

1. 填寫應用程式註冊畫面：

   * 名稱： adobe campaign `<stage or prod>`
   * 支援的帳戶型別： **[!UICONTROL Accounts in this organizational directory only]** （預設值）

如需建立新應用程式的詳細資訊，請參閱[本節](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app){target="_blank"}。

>[!NOTE]
>
>Microsoft Azure Directory會將唯一的應用程式（使用者端） ID指派給應用程式。 您稍後在設定Dynamics 365時，以及執行整合工具設定時，都需要此ID。

### 產生使用者端密碼 {#generate-a-client-secret}

1. 在應用程式總覽畫面中，按一下左側子功能表上的&#x200B;**[!UICONTROL Certificates and Secrets > New client secret]**

1. 輸入說明、設定持續時間，然後按一下&#x200B;**[!UICONTROL OK]**。

您的使用者端密碼現在已建立。 暫時保留值，以完成整合工具的預先整合設定。

>[!CAUTION]
>
>視需要保留此值，以完成整合工具預先整合設定。 之後無法擷取它。


### 設定許可權

1. 在此畫面或應用程式總覽畫面中，按一下左側子功能表中的&#x200B;**[!UICONTROL API permissions]**。  按一下&#x200B;**[!UICONTROL Add a permission]**&#x200B;之後，您需要在功能表中選取&#x200B;**[!UICONTROL Dynamics CRM]**。

1. 然後核取&#x200B;**[!UICONTROL user_impersonation]**&#x200B;的方塊，並按一下&#x200B;**[!UICONTROL Add permissions]**&#x200B;按鈕。

如需許可權設定的詳細資訊，請參閱[本節](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-configure-app-access-web-apis#add-permissions-to-access-web-apis){target="_blank"}。

### 建立應用程式使用者

此新使用者是一般使用者。 應用程式將使用此應用程式：此使用者將完成使用API對Microsoft Dynamics 365所做的任何變更。 請依照下列步驟以建立檔案：

1. 導覽至您的Dynamics 365執行個體並以管理員身分登入。

1. 按一下右上角的齒輪圖示，然後按一下&#x200B;**[!UICONTROL Advanced Settings]**。 在上方的橫幅中，按一下&#x200B;**[!UICONTROL Settings]**&#x200B;旁的下拉式清單，再按一下&#x200B;**[!UICONTROL Security > Users]**。

1. 按一下下拉式功能表，前往&#x200B;**[!UICONTROL Application Users]**。 按一下&#x200B;**[!UICONTROL New]**。

1. 確定使用者圖示旁的下拉式清單顯示&#x200B;**[!UICONTROL USER:APPLICATION USER]**。

   填寫新使用者的畫面。  引數建議：

   * **[!UICONTROL User Name]** （電子郵件）： adobe_api_`<stage-or-prod>`@`<your-d365-hostname>`&quot; (例如adobe_api_stage@some-company.crm.dynamics.com)
   * **[!UICONTROL Application ID]**：您在Azure AD中註冊的應用程式識別碼（此為必要專案）
   * 您可以留空&#x200B;**[!UICONTROL Application ID URI]**&#x200B;和&#x200B;**[!UICONTROL Azure AD Object ID]**
   * **[!UICONTROL Full Name]**：AdobeAPI `<stage or prod>`
   * **[!UICONTROL Email]**：與&#x200B;**[!UICONTROL User Name]**&#x200B;相同（或管理員的電子郵件，如果願意）

   如需應用程式使用者建立的詳細資訊，請參閱[本節](https://docs.microsoft.com/en-gb/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user){target="_blank"}。

1. 按一下使用者圖示並上傳Adobe Campaign圖示；這是當Dynamics 365中出現新Adobe事件時，顯示在「時間軸」檢視中的圖示。

1. 按一下頂端功能區中的&#x200B;**[!UICONTROL MANAGE ROLES]**，開啟使用者角色清單。

1. 向下捲動並選取此使用者的&#x200B;**[!UICONTROL System administrator]**&#x200B;存取權。

1. 按一下&#x200B;**[!UICONTROL OK]**。

### 取得租使用者ID {#get-the-tenant-id}

依照此頁面[&#128279;](https://docs.microsoft.com/en-us/onedrive/find-your-office-365-tenant-id)中的指示尋找您的租使用者ID。  在整合工具的預先整合設定期間，您會需要此ID。

## 安裝Microsoft Dynamics 365Campaign Standard {#install-appsource-app}

若要將Dynamics 365應用程式整合至您的Campaign Standard環境，請遵循下列步驟：

1. 瀏覽至[Microsoft商務應用程式](https://appsource.microsoft.com/en-us/marketplace/apps)，並在搜尋列中搜尋_Adobe Campaign Standard_。
或者，您也可以瀏覽至此[連結](https://appsource.microsoft.com/en-us/product/dynamics-365/adobe.adobe_campaign_d365?tab=Overview){target="_blank"}。
1. 依照指示為您的Dynamics 365執行個體安裝應用程式。
1. 安裝後，請導覽至您的Dynamics 365執行個體並以管理員身分登入。
1. 按一下右上角的齒輪圖示，然後按一下&#x200B;**[!UICONTROL Advanced Settings]**。 在頂端橫幅中，按一下&#x200B;**[!UICONTROL Settings]**&#x200B;旁的下拉式清單，再按一下&#x200B;**[!UICONTROL Process Center]**&#x200B;下方的&#x200B;**[!UICONTROL Processes]**。
1. 搜尋&#x200B;**[!UICONTROL Adobe Campaign Email Bounce]**&#x200B;工作並按一下它。
1. 在&#x200B;**[!UICONTROL Administration]**&#x200B;標籤上，按一下頂端功能區的&#x200B;**[!UICONTROL Actions]**，將擁有者變更為先前建立的AdobeAPI應用程式使用者，然後選取&#x200B;**[!UICONTROL Assign to another User]**&#x200B;選項，再從下拉式清單中選取&#x200B;**[!UICONTROL Adobe API application user]**&#x200B;以指派。
1. 重新啟用程式。
1. 對&#x200B;**[!UICONTROL Adobe Campaign Email Click]**&#x200B;任務執行相同操作。

>[!NOTE]
>
>如果您在任何時候想要停用這些程式，可以在此&#x200B;**[!UICONTROL Processes]**&#x200B;畫面中執行。

**相關主題**

* [設定Microsoft Dynamics 365整合的Adobe Developer ](../../integrating/using/d365-acs-configure-adobe-io.md)是設定整合的下一個步驟
* [開始使用自助服務整合應用程式](../../integrating/using/d365-acs-self-service-app-quick-start-guide.md)包含啟動並執行整合的完整步驟清單。
