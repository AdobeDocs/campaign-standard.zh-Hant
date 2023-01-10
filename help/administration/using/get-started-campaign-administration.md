---
title: 開始使用 Campaign Standard 系統管理
description: 了解使用者和權限管理、監控準則、通道特定的配置和應用程式設定準則。
audience: administration
feature: Access Management
role: Admin
level: Experienced
exl-id: 9676b5e8-4c34-4848-8616-235e0bac5d6b
source-git-commit: bfba6b156d020e8d2656239e713d2d24625bda54
workflow-type: tm+mt
source-wordcount: '637'
ht-degree: 15%

---

# 開始使用 Campaign Standard 系統管理 {#about-administrating-adobe-campaign}

<table>
<tr><td><img src="assets/do-not-localize/icon_menu.svg" width="60px"><p><a href="#administration-menu">管理功能表</a></p></td>
<td><img src="assets/do-not-localize/icon_users.svg" width="60px"><p><a href="#users-security">使用者與安全性</a></p></td>
<td><img src="assets/do-not-localize/icon_channels.svg" width="60px"><p><a href="#channels-configuration">通道配置</a></p></td>
<td><img src="assets/do-not-localize/icon_settings.svg" width="60px"><p><a href="#application-settings">應用程式設定</a></p></td></tr>
</table>

Adobe Campaign是雲端型解決方案，為管理員提供設定應用程式的不同方式。 雖然基礎架構配置由Adobe執行，但功能管理員可以執行以下詳細說明的各種配置操作。

>[!NOTE]
>
>若您對實作和設定有任何疑問或要求，請聯絡您的Adobe帳戶主管。

請注意，管理員使用者也可以運用「Campaign控制面板」來管理每個執行個體的設定並追蹤每個執行個體的使用方式。 如需詳細資訊，請參閱[專屬文件](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=zh-Hant)。

## 管理功能表 {#administration-menu}

<img src="assets/do-not-localize/icon_menu.svg" width="60px">

不同的Adobe Campaign管理操作會透過 **[!UICONTROL Administration]** 按一下左上角的Adobe Campaign標誌時可存取的功能表。 此部分的介面只能由平台的功能管理員存取。

可用的不同功能表包括：

* [使用者與安全性](../../administration/using/about-access-management.md):此功能表可讓您管理對平台（使用者、角色、安全群組、裝置）的存取權。
* [管道](../../administration/using/about-channel-configuration.md):此功能表會重新分組連結至不同平台通道（電子郵件、行動裝置）的技術參數，以及分類和隔離管理。
* [應用程式設定](../../administration/using/external-accounts.md):此功能表可讓您設定不同的應用程式元素（外部帳戶、選項、技術工作流程）。
* [開發](../../developing/using/data-model-concepts.md):此功能表可讓您管理自訂資源並存取診斷工具。
* [執行個體設定](../../administration/using/branding.md):您可在此功能表定義不同品牌並設定其設定（標誌、管理追蹤、存取登錄頁面的URL網域等）。
* [部署](../../automating/using/managing-packages.md):此功能表會重新分組套件匯入和匯出選項。
* [客戶量度](../../audiences/using/active-profiles.md):Adobe Campaign提供顯示作用中設定檔數目的報表。 此報表僅提供資訊，對帳單沒有直接影響。
* [隱私權工具](../../start/using/privacy-management.md):此功能表可讓您建立GDPR存取和刪除請求，並追蹤其演變。

## 使用者與安全性 {#users-security}

<img src="assets/do-not-localize/icon_users.svg"  width="60px">

邀請使用者存取應用程式並管理 **安全組**，這些是一組使用者，在您的組織內共用相同的角色和權限。 依預設，Adobe Campaign提供 **角色** 這可讓您定義指派給使用者和使用者群組的統一授權。 結合 **組織單位**，角色可讓使用者檢視介面的篩選檢視，並定義其對不同功能的存取權。

Campaign Standard也可讓您監視與安全性相關的資訊。 您可以透過 **[!UICONTROL Export audits]** 畫面，並運用 **[!UICONTROL Licenses]** 螢幕監控組織內所有已安裝的Campaign授權，以及不同資訊，例如組建編號、發行版本和合約條款。

閱讀全文:

* [使用者管理](../../administration/using/users-management.md)
* [組織單位](../../administration/using/organizational-units.md)
* [角色清單](../../administration/using/list-of-roles.md)
* [管理群組和使用者](../../administration/using/managing-groups-and-users.md)
* [稽核匯出記錄](../../administration/using/auditing-export-logs.md)
* [授權](../../administration/using/licenses.md)

## 通道配置 {#channels-configuration}

<img src="assets/do-not-localize/icon_channels.svg" width="60px">

Adobe Campaign中的所有通訊通道都必須正確設定，才能有效傳送訊息。, **[!UICONTROL Channel]**  功能表，您可以管理連結至不同管道的技術參數。

設定各種 **電子郵件** 參數：退信、隔離、電子郵件屬性和路由參數、類型規則的處理規則。 為 **簡訊** 通道，以及SMS編碼和格式。

設定 **行動應用程式** 以便使用Adobe Experience Platform SDK傳送應用程式內訊息和推播通知。

閱讀全文:

* [關於頻道設定](../../administration/using/about-channel-configuration.md)
* [設定電子郵件頻道](../../administration/using/configuring-email-channel.md)
* [設定 SMS 通道](../../administration/using/configuring-sms-channel.md)
* [設定行動應用程式](../../administration/using/configuring-a-mobile-application.md)

## 應用程式設定 {#application-settings}

<img src="assets/do-not-localize/icon_settings.svg" width="60px">

Campaign Standard隨附不同的應用程式元素，可依您的需求進行設定。

設定 **外部帳戶**，用於將Adobe Campaign連線至外部伺服器。 存取Campaign Standard目標對應，並使用 **技術工作流程**.

定義一或多個 **品牌** ，並設定 **即時通知** 在應用程式內，以防發生重要的系統活動。

閱讀全文:

* [關於 Campaign Standard 設定](../../administration/using/about-campaign-standard-settings.md)
* [外部帳戶](../../administration/using/external-accounts.md)
* [Campaign 中目標定位對應](../../administration/using/target-mappings-in-campaign.md)
* [技術工作流程](../../administration/using/technical-workflows.md)
* [品牌](../../administration/using/branding.md)
* [傳送內部通知](../../administration/using/sending-internal-notifications.md)
