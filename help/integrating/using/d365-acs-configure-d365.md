---
title: 設定 Microsoft Dynamics 365 以進行 Campaign 整合
description: 瞭解如何配置MicrosoftDynamics 365以進行市場活動整合。
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

# 配置MicrosoftDynamics 365以與Adobe Campaign Standard整合

瞭解如何配置MicrosoftDynamics 365整合併激活與Adobe Campaign Standard的跨通道通信中的CRM資料。

## 概覽

對Adobe Campaign Standard與MicrosoftDynamics 365整合的一般描述在 [此頁](../../integrating/using/d365-acs-get-started.md)。

需要配置多個應用程式以啟用整合，但本文將重點介紹Dynamics 365中所需的步驟。

## 必要條件

在執行本文檔中的預整合設定之前，假定您已設定並擁有對組織的MicrosoftDynamics 365實例的管理員訪問權限。  如果沒有發生這種情況，則您需要與Microsoft客戶支援聯繫以完成Dynamics 365資源調配。

如果要為登台和生產環境配置整合，則需要對登台和生產Dynamics 365實例執行以下步驟。 以下幾條說明會略有不同，具體取決於您是配置階段還是生產Dynamics 365實例(例如，對於生產實例，請為 `<stage or prod>`)

## 設定應用程式和權限

OAuth訪問令牌允許整合工具通過Web API向您的MicrosoftDynamics 365實例進行身份驗證，以便將Campaign Standard體驗事件發佈到MicrosoftDynamics 365介面的時間軸視圖。

以下視頻中概述了主要步驟：

>[!VIDEO](https://video.tv.adobe.com/v/27637)

要生成OAuth訪問令牌，請執行以下步驟。

### 註冊新應用程式 {#register-a-new-app}

1. 在管理員登錄下，登錄到 [門戶.azure.com](https://portal.azure.com){target="_blank"}。

1. 按一下 **[!UICONTROL Azure Active Directory]** 菜單的左側；按一下 **[!UICONTROL App registrations]** 的子菜單。

1. 按一下 **[!UICONTROL New registration]** 在螢幕頂部。

1. 填寫應用註冊螢幕：

   * 名稱：adobe促銷 `<stage or prod>`
   * 支援的帳戶類型： **[!UICONTROL Accounts in this organizational directory only]** （預設值）

有關建立新應用程式的詳細資訊，請參閱 [此部分](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app){target="_blank"}。

>[!NOTE]
>
>MicrosoftAzure Directory將唯一的應用程式（客戶端）ID分配給你的應用。 以後在配置Dynamics 365以及執行整合工具設定時，需要此ID。

### 生成客戶端密碼 {#generate-a-client-secret}

1. 在應用程式概述螢幕左側的子菜單上，按一下 **[!UICONTROL Certificates and Secrets > New client secret]**

1. 輸入說明，設定持續時間，然後按一下 **[!UICONTROL OK]**。

您的客戶機密碼現已建立。 暫時保留值，以完成整合工具的預整合設定。

>[!CAUTION]
>
>保留此值，因為您需要它來完成整合工具的預整合設定。 以後無法檢索。


### 設定權限

1. 在此螢幕或應用概述螢幕中，按一下 **[!UICONTROL API permissions]** 的上界。  按一下後 **[!UICONTROL Add a permission]**，需要選擇 **[!UICONTROL Dynamics CRM]** 的雙曲餘切值。

1. 然後選中 **[!UICONTROL user_impersonation]**，然後按一下 **[!UICONTROL Add permissions]** 按鈕

有關權限設定的詳細資訊，請參閱 [此部分](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-configure-app-access-web-apis#add-permissions-to-access-web-apis){target="_blank"}。

### 建立應用用戶

此新用戶是通用用戶。 應用程式將使用它：使用此API對MicrosoftDynamics 365的任何更改將由此用戶完成。 要建立它，請執行以下步驟：

1. 導航到Dynamics 365實例並以管理員身份登錄。

1. 按一下右上角的齒輪表徵圖，然後按一下 **[!UICONTROL Advanced Settings]**。 在頂部標題中，按一下旁邊的下拉框 **[!UICONTROL Settings]**，按一下 **[!UICONTROL Security > Users]**。

1. 按一下下拉菜單，轉到 **[!UICONTROL Application Users]**。 按一下&#x200B;**[!UICONTROL New]**。

1. 確保下拉菜單位於用戶表徵圖旁，顯示 **[!UICONTROL USER:APPLICATION USER]**。

   填寫新用戶的螢幕。  參數建議：

   * **[!UICONTROL User Name]** （電子郵件）:adobe_api`<stage-or-prod>`@`<your-d365-hostname>`&quot;(例如，adobe_api_stage@some-company.crm.dynamics.com)
   * **[!UICONTROL Application ID]**:您在Azure AD中註冊的應用程式的ID（此為必需項）
   * 可以留空 **[!UICONTROL Application ID URI]** 和 **[!UICONTROL Azure AD Object ID]**
   * **[!UICONTROL Full Name]**:AdobeAPI `<stage or prod>`
   * **[!UICONTROL Email]**:相同 **[!UICONTROL User Name]** (或管理員的電子郵件（如果您願意）

   有關應用程式用戶建立的詳細資訊，請參閱 [此部分](https://docs.microsoft.com/en-gb/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user){target="_blank"}。

1. 按一下用戶表徵圖並上傳Adobe Campaign表徵圖；這是當新Adobe事件出現在Dynamics 365中時，將在時間軸視圖中顯示的表徵圖。

1. 通過按一下 **[!UICONTROL MANAGE ROLES]** 在頂部彩帶上。

1. 向下滾動並選擇 **[!UICONTROL System administrator]** 此用戶的訪問權限。

1. 按一下&#x200B;**[!UICONTROL OK]**。

### 獲取租戶ID {#get-the-tenant-id}

按照說明操作 [此頁](https://docs.microsoft.com/en-us/onedrive/find-your-office-365-tenant-id) 找到您的租戶ID。  在整合工具中的預整合設定期間，您需要此ID。

## 安裝MicrosoftDynamics 365的Campaign Standard {#install-appsource-app}

要將Dynamics 365應用程式整合到您的Campaign Standard環境，請執行以下步驟：

1. 導航到以下連結： [https://appsource.microsoft.com/en-us/marketplace/apps](https://appsource.microsoft.com/en-us/marketplace/apps) 並搜索 _Adobe Campaign動力365_ 的子菜單。
或者，您可以導航到此 [連結](https://appsource.microsoft.com/en-us/product/dynamics-365/adobecampaign.re4snj-a4n7-5t6y-a14br-d5d1b?flightCodes=adobesignhide&amp;tab=Overview)
{target="_blank"}。
1. 按照說明為Dynamics 365實例安裝應用。
1. 安裝後，導航到Dynamics 365實例並以管理員身份登錄。
1. 按一下右上角的齒輪表徵圖，然後按一下 **[!UICONTROL Advanced Settings]**。 在頂部標題中，按一下旁邊的下拉框 **[!UICONTROL Settings]**，按一下 **[!UICONTROL Processes]** 在 **[!UICONTROL Process Center]**。
1. 搜索 **[!UICONTROL Adobe Campaign Email Bounce]** 任務並按一下。
1. 在 **[!UICONTROL Administration]** 頁籤，通過按一下將所有者更改為先前建立的AdobeAPI應用程式用戶 **[!UICONTROL Actions]** 從頂部功能區中，然後選擇 **[!UICONTROL Assign to another User]** 選項，選擇 **[!UICONTROL Adobe API application user]** 從下拉清單中分配。
1. 重新激活進程。
1. 為 **[!UICONTROL Adobe Campaign Email Click]** 的子菜單。

>[!NOTE]
>
>如果您希望隨時停用這些進程，可以在此中執行此操作 **[!UICONTROL Processes]** 的上界。

**相關主題**

* [配置Adobe Developer以進行MicrosoftDynamics 365整合](../../integrating/using/d365-acs-configure-adobe-io.md) 是設定整合的下一步
* [開始使用自助服務整合應用](../../integrating/using/d365-acs-self-service-app-quick-start-guide.md) 包含獲取整合啟動和運行的完整步驟清單。
