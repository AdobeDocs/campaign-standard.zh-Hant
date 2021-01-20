---
solution: Campaign Standard
product: campaign
title: 設定 Microsoft Dynamics 365 以進行 Campaign 整合
description: 瞭解如何設定Microsoft Dynamics 365以進行Campaign整合。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
translation-type: tm+mt
source-git-commit: 3ba3e0db816832ea57c124a9bea1fa82cf068859
workflow-type: tm+mt
source-wordcount: '911'
ht-degree: 1%

---


# 設定Microsoft Dynamics 365，以與Adobe Campaign Standard整合

瞭解如何設定Microsoft Dynamics 365整合，並透過Adobe Campaign Standard的跨通道通訊啟動您的CRM資料。

## 概觀

本頁[說明與Microsoft Dynamics 365整合的Adobe Campaign Standard的一般說明。](../../integrating/using/d365-acs-get-started.md)

但是，必須設定多個應用程式才能啟用整合，本文將著重於Dynamics 365中所需的步驟。

## 必要條件

在本檔案中執行預先整合設定之前，我們假定您已布建並擁有貴組織Microsoft Dynamics 365例項的管理員存取權。  如果未發生此情況，則您需要與Microsoft客戶支援聯絡，以完成Dynamics 365布建。

如果您要為測試環境和生產環境配置整合，則需要為測試和生產Dynamics 365實例執行以下步驟。 以下幾條說明會隨您設定舞台或生產Dynamics 365例項而稍有不同（例如，對於生產例項，請選取`<stage or prod>`的&quot;prod&quot;）

## 設定應用程式和權限

OAuth存取Token可讓整合工具透過網頁API與您的Microsoft Dynamics 365例項驗證，以便將Campaign Standard體驗事件張貼至Microsoft Dynamics 365介面的時間軸檢視。

以下視訊概述了主要步驟：

>[!VIDEO](https://video.tv.adobe.com/v/27637)

若要產生OAuth存取Token，請遵循下列步驟。

### 註冊新應用程式{#register-a-new-app}

1. 在您的管理員登入下，登入portal.azure.com。

1. 按一下左側菜單中的&#x200B;**[!UICONTROL Azure Active Directory]**;然後，在出現的子菜單上按一下&#x200B;**[!UICONTROL App registrations]**。

1. 按一下畫面頂端的&#x200B;**[!UICONTROL New registration]**。

   ![](assets/do-not-localize/MSdynACSIntegration-7.png)

1. 填寫應用程式註冊畫面：

   * 名稱：adobe campaign `<stage or prod>`
   * 支援的帳戶類型：**[!UICONTROL Accounts in this organizational directory only]**（預設值）

有關建立新應用程式的詳細資訊，請參閱[本節](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app)。

>[!NOTE]
>
>Microsoft Azure目錄會為您的應用程式指派唯一的應用程式（用戶端）ID。 您稍後在設定Dynamics 365時，以及執行整合工具設定時，都需要此ID。

### 產生用戶端密碼{#generate-a-client-secret}

1. 在應用程式概述畫面中，按一下左側子選單上的&#x200B;**[!UICONTROL Certificates and Secrets > New client secret]**

   ![](assets/do-not-localize/MSdynACSIntegration-8.png)

1. 輸入說明，設定持續時間，然後按一下&#x200B;**[!UICONTROL OK]**。

您的客戶機密碼現在已建立。 暫時保留值以完成整合工具的預先整合設定。

>[!CAUTION]
>
>視需要保留此值，以完成整合工具的預先整合設定。 以後無法檢索。


### 設定權限

1. 在此畫面或應用程式概述畫面中，按一下左側子選單中的&#x200B;**[!UICONTROL API permissions]**。  按一下&#x200B;**[!UICONTROL Add a permission]**&#x200B;後，需要在菜單中選擇&#x200B;**[!UICONTROL Dynamics CRM]**。

   ![](assets/do-not-localize/MSdynACSIntegration-9.png)

1. 然後選中&#x200B;**[!UICONTROL user_impersonation]**&#x200B;的框，然後按一下&#x200B;**[!UICONTROL Add permissions]**&#x200B;按鈕。

   ![](assets/do-not-localize/MSdynACSIntegration-10.png)

有關權限設定的詳細資訊，請參閱[本節](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-configure-app-access-web-apis#add-permissions-to-access-web-apis)。

### 建立應用程式使用者

此新使用者是一般使用者。 應用程式將會使用它：使用API對Microsoft Dynamics 365所做的任何變更，都將由此使用者完成。 若要建立它，請依照下列步驟：

1. 導覽至您的Dynamics 365例項，並以管理員身分登入。

1. 按一下右上角的齒輪表徵圖，然後按一下&#x200B;**[!UICONTROL Advanced Settings]**。 在頂端橫幅中，按一下&#x200B;**[!UICONTROL Settings]**&#x200B;旁的下拉式清單，然後按一下&#x200B;**[!UICONTROL Security > Users]**。

1. 按一下下拉式功能表前往&#x200B;**[!UICONTROL Application Users]**。 按一下 **[!UICONTROL New]**。

1. 確保使用者圖示旁的下拉式清單顯示&#x200B;**[!UICONTROL USER:APPLICATION USER]**。

   為新使用者填寫螢幕。  參數建議：

   * **[!UICONTROL User Name]** （電子郵件）:adobe_api_`<stage-or-prod>`@`<your-d365-hostname>`&quot;(例如，adobe_api_stage@some-company.crm.dynamics.com)
   * **[!UICONTROL Application ID]**:您在Azure AD中註冊的應用程式ID（此為必要項）
   * 您可以留空&#x200B;**[!UICONTROL Application ID URI]**&#x200B;和&#x200B;**[!UICONTROL Azure AD Object ID]**
   * **[!UICONTROL Full Name]**:Adobe API  `<stage or prod>`
   * **[!UICONTROL Email]**:與(或 **[!UICONTROL User Name]** 管理員的電子郵件（如果您願意）相同

   如需建立應用程式使用者的詳細資訊，請參閱[本節](https://docs.microsoft.com/en-gb/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user)。

1. 按一下使用者圖示並上傳Adobe Campaign圖示；這是當Dynamics 365中出現新的Adobe事件時，在「時間軸」檢視中顯示的圖示。

1. 按一下頂部功能區中的&#x200B;**[!UICONTROL MANAGE ROLES]**&#x200B;開啟用戶角色清單。

1. 向下滾動並選擇此用戶的&#x200B;**[!UICONTROL System administrator]**&#x200B;訪問。

1. 按一下 **[!UICONTROL OK]**。

### 取得租用戶ID {#get-the-tenant-id}

請依照本頁](https://docs.microsoft.com/en-us/onedrive/find-your-office-365-tenant-id)中的指示[尋找您的租用戶ID。  在整合工具的預先整合設定期間，您將需要此ID。

## 安裝Microsoft Dynamics 365的Campaign Standard {#install-appsource-app}

若要將Dynamics 365應用程式整合至您的Campaign Standard環境，請遵循下列步驟：

1. 導覽至下列連結：[https://appsource.microsoft.com/en-us/marketplace/apps](https://appsource.microsoft.com/en-us/marketplace/apps)並在搜尋列中搜尋&#x200B;_Adobe Campaign for Dynamics 365_。
或者，您也可以導覽至此[link](https://appsource.microsoft.com/en-us/product/dynamics-365/adobecampaign.re4snj-a4n7-5t6y-a14br-d5d1b?flightCodes=adobesignhide&amp;tab=Overview)。
1. 請依照指示，為您的Dynamics 365例項安裝應用程式。
1. 安裝後，導覽至您的Dynamics 365例項，並以管理員身分登入。
1. 按一下右上角的齒輪表徵圖，然後按一下&#x200B;**[!UICONTROL Advanced Settings]**。 在頂端橫幅中，按一下&#x200B;**[!UICONTROL Settings]**&#x200B;旁的下拉式清單，按一下&#x200B;**[!UICONTROL Process Center]**&#x200B;下方的&#x200B;**[!UICONTROL Processes]**。
1. 搜索&#x200B;**[!UICONTROL Adobe Campaign Email Bounce]**&#x200B;任務並按一下它。
1. 在&#x200B;**[!UICONTROL Administration]**&#x200B;標籤上，將擁有者變更為先前建立的Adobe API應用程式使用者，方法是從頂端功能區按一下&#x200B;**[!UICONTROL Actions]**，然後選取&#x200B;**[!UICONTROL Assign to another User]**&#x200B;選項，從下拉式清單中選取&#x200B;**[!UICONTROL Adobe API application user]**。
1. 重新啟動程式。
1. 對&#x200B;**[!UICONTROL Adobe Campaign Email Click]**&#x200B;任務執行相同操作。

>[!NOTE]
>
>如果您希望隨時停用這些進程，可以在此&#x200B;**[!UICONTROL Processes]**&#x200B;螢幕中執行此操作。

**相關主題**

* [設定Adobe IO for Microsoft Dynamics 365整](../../integrating/using/d365-acs-configure-adobe-io.md) 合是設定整合的下一步
* [開始使用自助服務整合應](../../integrating/using/d365-acs-self-service-app-quick-start-guide.md) 用程式，其中包含啟動及執行整合的完整步驟清單。
