---
title: 使用者管理
description: 'Adobe Campaign使用者具有特定角色。 探索主要使用者類型。 '
page-status-flag: never-activated
uuid: 8c4cc74a-815f-4815-af66-a7c21bc754f1
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: users-and-security
discoiquuid: 08c8712a-0066-4b8b-8471-2656b8fb23ed
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c26f98c8edd832beeedfedafb8ad27730cc30d25

---


# 使用者管理{#users-management}

## 關於用戶 {#about-users}

Adobe Campaign可讓您指派一組角色給您的使用者，以定義使用者可存取的介面部分。

以下各節將詳細介紹特定角色和相應的授權：了 [解角色](../../administration/using/list-of-roles.md)[和授權](https://docs.campaign.adobe.com/doc/standard/en/Technotes/AdobeCampaign-ACSRights.pdf)。

管理員可從管理控制台管理使用者。 然後，使用者會自動與Adobe Campaign同步。 如需詳細資訊，請參閱「管理控 [制台](https://helpx.adobe.com/enterprise/using/users.html) 」檔案。

若要在Adobe Campaign中檢視使用者，請按一 **[!UICONTROL Adobe Campaign]**下左上角的標誌，然後選取**[!UICONTROL Administration > Users & Security > Users]**。

若要從Adobe Campaign存取使用者管理介面，請按一下 **[!UICONTROL User administration]**。

![](assets/user_management_5.png)

**相關主題：**

* [管理使用者權限](https://helpx.adobe.com/campaign/kt/acs/using/acs-user-access-rights-feature-video-use.html) 影片
* [角色清單](../../administration/using/list-of-roles.md)
* [授權清單](https://docs.campaign.adobe.com/doc/standard/en/Technotes/AdobeCampaign-ACSRights.pdf)

## 使用者類型 {#type-of-users}

此使用者區段並非強制性，它僅代表Adobe Campaign最常用的用法。

本節將協助您瞭解Adobe Campaign使用者的主要類型。 在此，我們不會討論使用者可以承擔的所有特定角色（開始傳送、匯出、準備傳送等）。 有關角色的詳細資訊，請參 [閱角色清單](../../administration/using/list-of-roles.md)[和管理組和用戶頁](../../administration/using/managing-groups-and-users.md) 。

我們寧可專注於Adobe Campaign中的不同工作如何分為三種主要使用者類型：

* [功能管理員](#functional-administrators):在您組織的所有使用者中，他們是最具技術性的。
* [進階使用者](#advanced-users):他們會設定行銷人員傳送及監控其交貨所需的所有元素。
* [基本使用者](#basic-users):他們是行銷人員，負責個人化、傳遞及監控其宣傳活動。

>[!NOTE]
>
>功能管理員與Adobe技術管理員不同。 Adobe技術管理員負責Adobe內部角色，客戶無法使用。 他們管理實例配置、托管、基礎架構監控和監控、技術故障排除。

### 功能管理員 {#functional-administrators}

功能管理員是可存取介面中最技術部分的使用者。 他們負責 **[!UICONTROL Administration]**此角色，並確保平台都已設定好，因此行銷人員只需專注於傳遞其宣傳活動。

功能管理員是唯一可存取Adobe Campaign介 **[!UICONTROL Administration]**面中功能表的使用者。 由於這些使用者需要存取技術資源，因此應指派更多進階角色給他們，**[!UICONTROL Administration]** 例如 **[!UICONTROL Datamodel]**立即可用的角色。 這些角色會結合**[!UICONTROL Administrators]** 在現成可用的安全組中。 For more on this, refer to this [section](../../administration/using/list-of-roles.md).

以下是他們可以執行的主要任務：

* [管理使用者和權限](../../administration/using/about-access-management.md):管理對平台（用戶、角色、安全組、設備）的訪問。
* [設定不同的頻道](../../administration/using/about-channel-configuration.md):建立不同的平台通道，以及分類和隔離管理。
* [設定一般應用程式設定](../../administration/using/external-accounts.md):設定不同的應用程式元素（外部帳戶、選項、技術工作流程）。
* [開發新功能以增強現成可用的功能](../../developing/using/data-model-concepts.md):管理您的自訂資源並存取診斷工具。
* [設定實例參數](../../administration/using/branding.md):定義您的不同品牌並設定其設定（標誌、管理追蹤、存取著陸頁面的URL網域等）。
* [匯出和匯入資料套件](../../automating/using/managing-packages.md):透過結構化XML檔案，在不同Adobe Campaign實例之間交換資源。
* [匯出記錄](../../automating/using/exporting-logs.md) ，並 [定義匯入範本](../../automating/using/defining-import-templates.md)。

### 進階使用者 {#advanced-users}

進階使用者是在Adobe Campaign中執行最具技術性使用案例的行銷使用者。 他們會預先設定行銷人員用來傳送及監控其遞送的所有元素。

與功能管理員相比，這種類型的用戶需要更多的一般角色，但仍應能夠執行一些技術操作。 為此，應指派這些角色， **[!UICONTROL Export]**例如**[!UICONTROL Generic import]** , **[!UICONTROL Workflow]**即裝即用的角色。 For more on this, refer to this[section](../../administration/using/list-of-roles.md).

以下是他們可以執行的主要任務：

* [建立並執行複雜的資料管理工作流程](../../automating/using/about-data-management-activities.md):匯入、豐富和轉換資料以餵送資料庫，或匯出外部檔案中所需的資料，以便在您自己的工具中處理。
* [管理範本](../../start/using/marketing-activity-templates.md):管理範本，以根據您的需求預先設定特定的行銷活動參數。
* [建立查詢](../../automating/using/editing-queries.md#about-query-editor) , [並管理您的觀眾](../../audiences/using/about-audiences.md):使用查詢手動建立您的觀眾，或自動使用專屬的工作流程。
* [執行進階運算式編輯](../../automating/using/editing-queries.md#about-query-editor):使用進階函式來控制用於執行特定查詢的值，例如日期、字串、數值欄位、排序等。
* [使用現有的匯](../../automating/using/exporting-lists.md) 入範本匯出清單和匯入資料 [](../../automating/using/importing-data-with-import-templates.md)。

### 基本使用者 {#basic-users}

由於擁有功能管理員和進階使用者，行銷人員可以個人化、提供和監控其宣傳活動，而不需擔心技術設定。 為此，應指派這些角色， **[!UICONTROL Prepare deliveries]**例如**[!UICONTROL Workflow]** , **[!UICONTROL Start deliveries]**即裝即用的角色。 這些角色會結合**[!UICONTROL Standard Users]** 在現成可用的安全組中。 For more on this, refer to this [section](../../administration/using/list-of-roles.md).

以下是他們可以執行的主要任務：

* [管理方案和宣傳活動](../../start/using/programs-and-campaigns.md):建立行銷宣傳，包括不同的活動類型（電子郵件、SMS訊息、推播通知、工作流程、登陸頁面）。
* 管理 [設定檔](../../audiences/using/about-profiles.md) 和測 [試設定檔](../../sending/using/managing-test-profiles-and-sending-proofs.md):管理已識別的收件者，並測試您的傳送目標。 新增名字、姓氏、連絡人資訊、訂閱、電子郵件等資訊。
* [建立和傳送訊息](../../sending/using/confirming-the-send.md):建立您的訊息、選取觀眾、定義訊息內容及其個人化元素、傳送校樣並傳送最終訊息給觀眾。
* [建立和發佈登陸頁面](../../channels/using/getting-started-with-landing-pages.md):建立並管理您想要提供給客戶的一組服務，例如訂閱或取消訂閱表格。
* [建立並執行促銷活動工作流程](../../automating/using/building-a-workflow.md):使用工作流程自動化您的宣傳流程。
* 透過可用報表監控您的 [行銷活動](../../reporting/using/defining-the-report-period.md)。

## 建立使用者 {#creating-a-user}

若要新增使用者至您的例項，您必須先在「管理控制台」中建立該使用者，然後才能在Adobe Campaign Standard中管理。

1. 從進階功能表中，選取並 **[!UICONTROL Administration > Users & Security > Users]**按一下**[!UICONTROL User administration]** 以存取管理控制台。

   ![](assets/user_management_5.png)

1. 在中， **[!UICONTROL Admin Console]**按一下頁籤**[!UICONTROL Users]** 。

1. 按一下 **[!UICONTROL Add User]**.

   ![](assets/create_user_2.png)

1. 在標籤 **[!UICONTROL User details]**中，填寫使用者的詳細資訊，例如電子郵件地址、姓名和姓氏。

   ![](assets/create_user_3.png)

1. 從標籤 **[!UICONTROL Assign products]**中，為您的使用者指派一或多個安全性群組。 有關安全組的詳細資訊，請參閱本[頁](../../administration/using/managing-groups-and-users.md)。

   完成 **[!UICONTROL Save]**配置後按一下。

   ![](assets/create_user_4.png)

您的使用者現在已建立，應會收到重新導向至下列視窗的電子郵件，使用者必須先設定密碼，然後接受使用合約條款。 然後，此使用者便能連線至您的Adobe Campaign standard實例。

![](assets/create_user_5.png)

當您的使用者登入您的例項時，就會將其同步至Adobe Campaign Standard。

然後，您可以檢查您的使用者是否已正確同步至Adobe Campaign:

1. 從進階選單中，選 **[!UICONTROL Administration > Users & Security > Users]**取您先前建立的使用者。

1. 更新 **[!UICONTROL Mobile]**或**[!UICONTROL Time zone]** 視 **[!UICONTROL Regional settings]**需要更新。

1. 檢查您使用者的安全性群組。 在這裡，您可以看到用戶已被分配到安 **[!UICONTROL Administrators]**全組。

   >[!Note]
   >
   >安全性群組只能在「管理控制台」中移除或新增至使用者。

   ![](assets/create_user_6.png)

1. 如果 **[!UICONTROL Account disabled]**您想停用此使用者，請勾選。

1. 在字 **[!UICONTROL Authorized connection zone]**段中，選擇用戶將通過哪個方式連接到此實例，如內部網路或VPN。

1. 按一下 **[!UICONTROL Save]**.

您的使用者現在已準備好使用Adobe Campaign Standard。
