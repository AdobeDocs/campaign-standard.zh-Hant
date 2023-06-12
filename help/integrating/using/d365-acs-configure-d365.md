---
title: 設定 Microsoft Dynamics 365 以進行 Campaign 整合
description: 瞭解如何設定Microsoft Dynamics 365以進行Campaign整合。
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

瞭解如何設定Microsoft Dynamics 365整合，以及透過Adobe Campaign Standard進行跨管道通訊時啟用您的CRM資料。

## 概覽

Adobe Campaign Standard與Microsoft Dynamics 365整合的一般說明請參閱 [此頁面](../../integrating/using/d365-acs-get-started.md).

您必須設定多個應用程式才能啟用整合，不過本文會重點介紹Dynamics 365中所需的步驟。

## 必要條件

在此檔案中執行預先整合設定之前，假設您已布建並擁有貴組織的Microsoft Dynamics 365執行個體的管理員存取權。  如果尚未發生此情況，則您需要聯絡Microsoft客戶支援以完成Dynamics 365布建。

如果您要設定中繼和生產環境的整合，則需要為中繼和生產的Dynamics 365執行個體執行以下步驟。 如果您要設定中繼或生產Dynamics 365例項，以下的一些指示會稍有不同(例如，對於生產例項，請選取「prod」 `<stage or prod>`)

## 設定應用程式和許可權

OAuth存取權杖可讓整合工具透過網頁API向您的Microsoft Dynamics 365執行個體進行驗證，以便將Campaign Standard體驗事件發佈到Microsoft Dynamics 365介面的時間軸檢視。

主要步驟概述於下列影片中：

>[!VIDEO](https://video.tv.adobe.com/v/27637)

若要產生OAuth存取權杖，請遵循下列步驟。

### 註冊新的應用程式 {#register-a-new-app}

1. 在您的管理員登入下，登入 [portal.azure.com](https://portal.azure.com){target="_blank"}.

1. 按一下 **[!UICONTROL Azure Active Directory]** ，然後按一下 **[!UICONTROL App registrations]** 在出現的子選單上。

1. 按一下 **[!UICONTROL New registration]** 在熒幕上方。

1. 填寫應用程式註冊畫面：

   * 名稱： adobe campaign `<stage or prod>`
   * 支援的帳戶型別： **[!UICONTROL Accounts in this organizational directory only]** （預設值）

如需建立新應用程式的詳細資訊，請參閱 [本節](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app){target="_blank"}.

>[!NOTE]
>
>Microsoft Azure Directory會指派唯一的應用程式（使用者端） ID給您的應用程式。 您稍後在設定Dynamics 365時，以及執行整合工具設定時，都需要此ID。

### 產生使用者端密碼 {#generate-a-client-secret}

1. 在應用程式總覽畫面上的左側子功能表中，按一下 **[!UICONTROL Certificates and Secrets > New client secret]**

1. 輸入說明、設定持續時間，然後按一下 **[!UICONTROL OK]**.

您的使用者端密碼現在已建立。 暫時保留值，以完成整合工具的預先整合設定。

>[!CAUTION]
>
>視需要保留此值，以完成整合工具預先整合設定。 之後無法擷取。


### 設定許可權

1. 從此畫面或應用程式總覽畫面，按一下 **[!UICONTROL API permissions]** 在左側的子功能表中。  按一下 **[!UICONTROL Add a permission]**，您需要選取 **[!UICONTROL Dynamics CRM]** （在功能表中）。

1. 然後勾選方塊 **[!UICONTROL user_impersonation]**，然後按一下 **[!UICONTROL Add permissions]** 按鈕。

如需許可權設定的詳細資訊，請參閱 [本節](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-configure-app-access-web-apis#add-permissions-to-access-web-apis){target="_blank"}.

### 建立應用程式使用者

此新使用者是一般使用者。 應用程式將使用此應用程式：此使用者將完成使用API對Microsoft Dynamics 365所做的任何變更。 若要建立，請遵循下列步驟：

1. 導覽至您的Dynamics 365執行個體並以管理員身分登入。

1. 按一下右上角的齒輪圖示，然後按一下 **[!UICONTROL Advanced Settings]**. 在頂端橫幅中，按一下旁邊的下拉式清單 **[!UICONTROL Settings]**，按一下 **[!UICONTROL Security > Users]**.

1. 按一下下拉式功能表，前往 **[!UICONTROL Application Users]**. 按一下&#x200B;**[!UICONTROL New]**。

1. 確定使用者圖示旁的下拉式清單顯示 **[!UICONTROL USER:APPLICATION USER]**.

   填寫新使用者的畫面。  引數建議：

   * **[!UICONTROL User Name]** （電子郵件）： adobe_api_`<stage-or-prod>`@`<your-d365-hostname>`&quot; (例如adobe_api_stage@some-company.crm.dynamics.com)
   * **[!UICONTROL Application ID]**：您在Azure AD中註冊的應用程式ID （此為必要）
   * 您可以保留空白 **[!UICONTROL Application ID URI]** 和 **[!UICONTROL Azure AD Object ID]**
   * **[!UICONTROL Full Name]**：AdobeAPI `<stage or prod>`
   * **[!UICONTROL Email]**：與 **[!UICONTROL User Name]** (或管理員的電子郵件（如果您願意）)

   如需應用程式使用者建立的詳細資訊，請參閱 [本節](https://docs.microsoft.com/en-gb/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user){target="_blank"}.

1. 按一下使用者圖示並上傳Adobe Campaign圖示；這是當Dynamics 365中出現新Adobe事件時，顯示在「時間軸」檢視中的圖示。

1. 按一下以開啟使用者角色清單 **[!UICONTROL MANAGE ROLES]** 在頂端功能區中。

1. 向下捲動並選取 **[!UICONTROL System administrator]** 此使用者的存取權。

1. 按一下&#x200B;**[!UICONTROL OK]**。

### 取得租使用者ID {#get-the-tenant-id}

依照指示操作 [在此頁面中](https://docs.microsoft.com/en-us/onedrive/find-your-office-365-tenant-id) 以尋找您的租使用者ID。  在整合工具的預先整合設定期間，您將需要此ID。

## 安裝Microsoft Dynamics 365Campaign Standard {#install-appsource-app}

若要將Dynamics 365應用程式整合至您的Campaign Standard環境，請遵循下列步驟：

1. 導覽至下列連結： [https://appsource.microsoft.com/en-us/marketplace/apps](https://appsource.microsoft.com/en-us/marketplace/apps) 並搜尋 _適用於Dynamics 365的Adobe Campaign_ 在搜尋列中。
或者，您可以導覽至此 [連結](https://appsource.microsoft.com/en-us/product/dynamics-365/adobecampaign.re4snj-a4n7-5t6y-a14br-d5d1b?flightCodes=adobesignhide&amp;tab=Overview)
{target="_blank"}.
1. 依照指示為您的Dynamics 365執行個體安裝應用程式。
1. 安裝後，請導覽至您的Dynamics 365執行個體並以管理員身分登入。
1. 按一下右上角的齒輪圖示，然後按一下 **[!UICONTROL Advanced Settings]**. 在頂端橫幅中，按一下旁邊的下拉式清單 **[!UICONTROL Settings]**，按一下 **[!UICONTROL Processes]** 在 **[!UICONTROL Process Center]**.
1. 搜尋 **[!UICONTROL Adobe Campaign Email Bounce]** 任務並按一下它。
1. 於 **[!UICONTROL Administration]** 索引標籤中，按一下「 」，將擁有者變更為先前建立的AdobeAPI應用程式使用者 **[!UICONTROL Actions]** 從頂端功能區中，然後選取 **[!UICONTROL Assign to another User]** 選項，選取 **[!UICONTROL Adobe API application user]** 從下拉式清單中進行指派。
1. 重新啟用程式。
1. 對執行相同操作 **[!UICONTROL Adobe Campaign Email Click]** 任務。

>[!NOTE]
>
>如果您在任何時候想要停用這些程式，可以在此完成 **[!UICONTROL Processes]** 畫面。

**相關主題**

* [設定Adobe Developer以進行Microsoft Dynamics 365整合](../../integrating/using/d365-acs-configure-adobe-io.md) 是設定整合的下一個步驟
* [開始使用自助服務整合應用程式](../../integrating/using/d365-acs-self-service-app-quick-start-guide.md) 包含啟動並執行整合的完整步驟清單。
