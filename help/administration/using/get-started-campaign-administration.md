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
source-wordcount: '631'
ht-degree: 12%

---

# 開始使用 Campaign Standard 系統管理 {#about-administrating-adobe-campaign}

<table>
<tr><td><img src="assets/do-not-localize/icon_menu.svg" width="60px"><p><a href="#administration-menu">管理功能表</a></p></td>
<td><img src="assets/do-not-localize/icon_users.svg" width="60px"><p><a href="#users-security">使用者與安全性</a></p></td>
<td><img src="assets/do-not-localize/icon_channels.svg" width="60px"><p><a href="#channels-configuration">頻道設定</a></p></td>
<td><img src="assets/do-not-localize/icon_settings.svg" width="60px"><p><a href="#application-settings">應用程式設定</a></p></td></tr>
</table>

Adobe Campaign做為雲端型解決方案，為管理員提供設定應用程式的不同方式。 雖然基礎架構設定是由Adobe執行，但功能管理員可以執行各種設定操作，如下所述。

>[!NOTE]
>
>如果您對實作與設定事宜有任何疑問或請求，請聯絡您的Adobe客戶主管。

請注意，管理員使用者也可以利用Campaign「控制面板」來管理設定，並追蹤每個執行個體的使用量。 如需詳細資訊，請參閱[專屬文件](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=zh-Hant)。

## 管理功能表 {#administration-menu}

<img src="assets/do-not-localize/icon_menu.svg" width="60px">

不同的Adobe Campaign管理員作業是透過 **[!UICONTROL Administration]** 按一下左上角的Adobe Campaign標誌即可存取功能表。 介面的這個部分只能由平台的功能管理員存取。

可用的不同功能表有：

* [使用者與安全性](../../administration/using/about-access-management.md)：此功能表可讓您管理對平台的存取權（使用者、角色、安全性群組、裝置）。
* [頻道](../../administration/using/about-channel-configuration.md)：此功能表會重新分組連結至不同平台管道（電子郵件、行動裝置）的技術引數，以及分類和隔離管理。
* [應用程式設定](../../administration/using/external-accounts.md)：此功能表可讓您設定不同的應用程式元素（外部帳戶、選項、技術工作流程）。
* [開發](../../developing/using/data-model-concepts.md)：此功能表可讓您管理自訂資源並存取診斷工具。
* [執行個體設定](../../administration/using/branding.md)：您可以在此功能表定義不同品牌並進行其設定（標誌、管理追蹤、存取登入頁面的URL網域等）。
* [部署](../../automating/using/managing-packages.md)：此功能表會對套件匯入和匯出選項進行重新分組。
* [客戶量度](../../audiences/using/active-profiles.md)： Adobe Campaign提供可顯示作用中設定檔數量的報表。 此報告僅提供資訊，對帳單沒有直接影響。
* [隱私權工具](../../start/using/privacy-management.md)：此功能表可讓您建立GDPR存取和刪除要求，並追蹤其演化。

## 使用者與安全性 {#users-security}

<img src="assets/do-not-localize/icon_users.svg"  width="60px">

邀請使用者存取應用程式並管理 **安全性群組**，即貴組織內共用相同角色和許可權的一組使用者。 依預設，Adobe Campaign提供了一組 **角色** 可讓您定義指派給使用者和使用者群組的統一授權。 結合 **組織單位**，角色可提供介面的篩選檢視，並定義使用者對不同功能的存取權。

Campaign standard也可讓您監視安全性相關資訊。 您可以透過以下方式擷取使用者執行的資料匯出相關資訊： **[!UICONTROL Export audits]** 熒幕，並運用 **[!UICONTROL Licenses]** 熒幕可監視組織內所有已安裝的Campaign授權，以及組建編號、發行版本和合約條款等不同資訊。

詳細內容：

* [使用者管理](../../administration/using/users-management.md)
* [組織單位](../../administration/using/organizational-units.md)
* [角色清單](../../administration/using/list-of-roles.md)
* [管理群組和使用者](../../administration/using/managing-groups-and-users.md)
* [稽核匯出記錄](../../administration/using/auditing-export-logs.md)
* [授權](../../administration/using/licenses.md)

## 頻道設定 {#channels-configuration}

<img src="assets/do-not-localize/icon_channels.svg" width="60px">

Adobe Campaign中的所有通訊通道都必須正確設定，才能有效地傳送訊息。，因此 **[!UICONTROL Channel]**  功能表可讓您管理連結至不同色版的技術引數。

設定各種 **電子郵件** 引數：退信、隔離、電子郵件屬性和路由引數的處理規則，型別規則。 定義路由設定和屬性 **簡訊** 管道及SMS編碼和格式。

設定 **行動應用計畫** 以便能夠使用Adobe Experience Platform SDK傳送應用程式內訊息和推播通知。

詳細內容：

* [關於頻道設定](../../administration/using/about-channel-configuration.md)
* [設定電子郵件頻道](../../administration/using/configuring-email-channel.md)
* [設定簡訊通道](../../administration/using/configuring-sms-channel.md)
* [設定行動應用程式](../../administration/using/configuring-a-mobile-application.md)

## 應用程式設定 {#application-settings}

<img src="assets/do-not-localize/icon_settings.svg" width="60px">

Campaign Standard隨附不同的應用程式元素，可加以設定以符合您的需求。

設定 **外部帳戶**，用於將Adobe Campaign連線至外部伺服器。 存取Campaign Standard目標對應，並使用監控您的平台 **技術工作流程**.

定義一或多個 **品牌** 並為您的組織設定傳送 **即時通知** 若是重要的系統活動，則位於應用程式內。

詳細內容：

* [關於 Campaign Standard 設定](../../administration/using/about-campaign-standard-settings.md)
* [外部帳戶](../../administration/using/external-accounts.md)
* [Campaign 中目標定位對應](../../administration/using/target-mappings-in-campaign.md)
* [技術工作流程](../../administration/using/technical-workflows.md)
* [品牌](../../administration/using/branding.md)
* [傳送內部通知](../../administration/using/sending-internal-notifications.md)
