---
title: 使用者管理
seo-title: 使用者管理
description: 使用者管理
seo-description: 'Adobe Campaign使用者擁有特定角色。探索主要使用者類型。 '
page-status-flag: 從未啓動
uuid: 8c4cc74a-815f-4815-af66-a7 c21 bc754 f1
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 管理
content-type: reference
topic-tags: 使用者與安全性
discoiquuid: 08c8712a-006-1b8b-8471-2656b8fb23ed
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: ab329af94dc4e28651aaef17f4588d894fb48b74

---


# Users management{#users-management}

## About users {#about-users}

Adobe Campaign可讓您指派一組角色給您的使用者，定義他們可以存取的介面部分。

The specific roles and the corresponding authorizations are detailed in the following sections: [understanding roles](../../administration/using/list-of-roles.md) and [authorizations](https://docs.campaign.adobe.com/doc/standard/en/Technotes/AdobeCampaign-ACSRights.pdf).

管理員可以從Admin Console管理使用者。然後使用者會自動與Adobe Campaign同步。For more on this, refer to the [Admin console](https://helpx.adobe.com/enterprise/using/users.html) documentation.

To view the users in Adobe Campaign, click the **[!UICONTROL Adobe Campaign]** logo, in the top left corner, then select **[!UICONTROL Administration > Users & Security > Users]**.

To access the user management interface from Adobe Campaign, click **[!UICONTROL User administration]**.

![](assets/user_management_5.png)

**相關主題：**

* [管理使用者權限](https://helpx.adobe.com/campaign/kt/acs/using/acs-user-access-rights-feature-video-use.html) 影片
* [角色清單](../../administration/using/list-of-roles.md)
* [授權清單](https://docs.campaign.adobe.com/doc/standard/en/Technotes/AdobeCampaign-ACSRights.pdf)

## Type of users {#type-of-users}

此使用者區隔並非強制性，僅代表Adobe Campaign最常見的用法。

本節將協助您瞭解Adobe Campaign使用者的主要類型。在這裡，我們不會進入使用者可以擁有的所有特定角色(開始傳送、轉存、準備遞送等)。For more information on roles, refer to [List of roles](../../administration/using/list-of-roles.md) and [Managing groups and users](../../administration/using/managing-groups-and-users.md) pages.

我們想要重點放在如何將不同的Adobe Campaign工作分為三種主要使用者類型：

* [功能管理員](../../administration/using/users-management.md#functional-administrators)：在所有組織的使用者當中，他們最具技術知識。
* [進階使用者](../../administration/using/users-management.md#advanced-users)：他們會設定行銷人員傳送和監控其傳遞所需的所有元素。
* [基本使用者](../../administration/using/users-management.md#basic-users)：他們是個人化、傳遞及監控宣傳活動的行銷人員。

>[!NOTE]
>
>功能管理員與Adobe技術管理員不同。Adobe技術管理員擁有Adobe內部角色，可供客戶使用。他們管理執行個體、托管、基礎結構監控和監督、技術疑難排解。

### Functional administrators {#functional-administrators}

功能管理員是可存取介面最技術部分的使用者。They hold the **[!UICONTROL Administration]** role and make sure that the platform is all set up so that marketers only have to focus on delivering their campaigns.

Functional administrators are the only users who can access the **[!UICONTROL Administration]** menu, in the Adobe Campaign interface. Since these users need to access technical resources, more advanced roles should be assigned to them, such as the **[!UICONTROL Administration]** and **[!UICONTROL Datamodel]** out-of-the-box roles. These roles are combined in the **[!UICONTROL Administrators]** out-of-the-box security group. For more on this, refer to this [section](../../administration/using/list-of-roles.md).

以下是他們可執行的主要工作：

* [管理使用者和權限](../../administration/using/about-access-management.md)：管理平台的存取權(使用者、角色、安全性群組、單位)。
* [設定不同的頻道](../../administration/using/about-channel-configuration.md)：設定不同的平台通道以及打字和隔離管理。
* [設定一般應用程式設定](../../administration/using/external-accounts.md)：設定不同的應用程式元素(外部帳戶、選項、技術工作流程)。
* [開發新功能以增強立即可用的功能](../../developing/using/data-model-concepts.md)：管理您的自訂資源並存取診斷工具。
* [設定例項參數](../../administration/using/branding.md)：定義您的不同品牌並設定其設定(標誌、管理追蹤、URL網域存取登陸頁面等)。
* [匯出及匯入資料封包](../../automating/using/managing-packages.md)：透過結構化XML檔案在不同的Adobe Campaign例項之間交換資源。
* [匯出記錄並](../../automating/using/exporting-logs.md)[定義匯入範本](../../automating/using/defining-import-templates.md)。

### Advanced users {#advanced-users}

進階使用者是執行Adobe Campaign技術使用案例的行銷使用者。他們預先設定行銷人員用來傳送和監控其傳送的所有元素。

這類使用者所需的一般角色比功能管理員更多，但仍能執行一些技術操作。To do so, they should be assigned, for example, the **[!UICONTROL Export]**, **[!UICONTROL Generic import]** or **[!UICONTROL Workflow]** out-of-the-box roles. For more on this, refer to this [section](../../administration/using/list-of-roles.md).

以下是他們可執行的主要工作：

* [建立並執行複雜的資料管理工作流程](../../automating/using/about-data-management-activities.md)：匯入、豐富和轉換資料以餵送資料庫，或匯出外部檔案中需要的資料，以在您自己的工具中處理。
* [管理範本](../../start/using/about-templates.md)：管理範本，根據您的需求預先設定行銷活動的某些參數。
* [建立查詢](../../automating/using/editing-queries.md#about-query-editor) 並 [管理觀眾](../../audiences/using/about-audiences.md)：使用查詢或使用專屬工作流程自動建立觀眾。
* [執行進階運算式編輯](../../automating/using/editing-queries.md#about-query-editor)：使用進階函數來控制用於執行特定查詢(例如日期、字串、數值欄位、排序等)的值。
* [使用現有的匯入範本匯出清單](../../automating/using/exporting-lists.md) 並 [匯入資料](../../automating/using/importing-data-with-import-templates.md)。

### Basic users {#basic-users}

由於具備功能管理員和進階用戶，行銷人員可以個人化、提供和監控宣傳活動，而無需擔心技術配置。To do so, they should be assigned, for example, the **[!UICONTROL Prepare deliveries]**, **[!UICONTROL Workflow]** and **[!UICONTROL Start deliveries]** out-of-the-box roles. These roles are combined in the **[!UICONTROL Standard Users]** out-of-the-box security group. For more on this, refer to this [section](../../administration/using/list-of-roles.md).

以下是他們可執行的主要工作：

* [管理計劃和宣傳](../../start/using/programs-and-campaigns.md)：建立行銷活動，包括不同類型的活動(電子郵件、SMS訊息、推播通知、工作流程、登陸頁面)。
* Manage [profiles](../../audiences/using/about-profiles.md) and [test profiles](../../sending/using/managing-test-profiles-and-sending-proofs.md): manage the identified and test recipients that will be targeted by your deliveries. 加入名字、姓氏、聯絡資訊、訂閱、電子郵件等資訊。
* [建立和傳送訊息](../../sending/using/confirming-the-send.md)：建立您的訊息、選取觀眾、定義訊息內容及其個人化元素、傳送校樣並傳送最後訊息給您的觀眾。
* [建立和發佈登陸頁面](../../channels/using/about-landing-pages.md)：建立並管理您希望為客戶提供的一組服務，例如訂閱或取消訂閱表格。
* [建立並執行促銷活動工作流程](../../automating/using/building-a-workflow.md)：使用工作流程自動化您的促銷活動流程。
* Monitor your marketing activities through the [available reports](../../reporting/using/defining-the-report-period.md).

## Creating a user {#creating-a-user}

若要新增使用者至您的例項，您必須先在Admin Console中建立它，然後才能在Adobe Campaign Standard中加以管理。

1. From the advanced menu, select **[!UICONTROL Administration > Users & Security > Users]** and click **[!UICONTROL User administration]** to access the admin console.

   ![](assets/user_management_5.png)

1. In the **[!UICONTROL Admin Console]**, click on the **[!UICONTROL Users]** tab.

1. Click **[!UICONTROL Add User]**.

   ![](assets/create_user_2.png)

1. From the **[!UICONTROL User details]** tab, fill in the user's details such as email address, name and surname.

   ![](assets/create_user_3.png)

1. From the **[!UICONTROL Assign products]** tab, assign one or multiple security group to your user. For more information on security groups, refer to this [page](../../administration/using/managing-groups-and-users.md).

   Click **[!UICONTROL Save]** when done configuring.

   ![](assets/create_user_4.png)

您的使用者現在已建立，且應該會收到重新導向至下列視窗的電子郵件，使用者必須設定密碼，然後接受使用期限合約。然後，此使用者就可以連線至您的Adobe Campaign Standard例項。

![](assets/create_user_5.png)

當使用者登入您的實例時，將會同步至Adobe Campaign Standard。

然後您可以檢查使用者是否已正確同步至Adobe Campaign：

1. From the advanced menu **[!UICONTROL Administration > Users & Security > Users]** select your previously created user.

1. Update the **[!UICONTROL Mobile]**, **[!UICONTROL Time zone]** or **[!UICONTROL Regional settings]** if needed.

1. 檢查使用者的安全性群組。Here, you can see that the user has been assigned the **[!UICONTROL Administrators]** security group.

   >[!Nte te]
   >
   >只有在「管理控制台」中才能移除或新增安全性群組。

   ![](assets/create_user_6.png)

1. Check **[!UICONTROL Account disabled]** if you want to deactivate this user.

1. In the **[!UICONTROL Authorized connection zone]** field, select through which way your user will connect to this instance, e.g. internal network or VPN.

1. Click **[!UICONTROL Save]**.

您的使用者現在已準備好使用Adobe Campaign Standard。
