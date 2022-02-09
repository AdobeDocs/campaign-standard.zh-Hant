---
title: 開始使用 Campaign Standard 系統管理
description: 瞭解用戶和權限管理、監視指南、特定於渠道的配置和應用程式設定指南
audience: administration
feature: Access Management
role: Admin
level: Experienced
exl-id: 9676b5e8-4c34-4848-8616-235e0bac5d6b
source-git-commit: bfba6b156d020e8d2656239e713d2d24625bda54
workflow-type: tm+mt
source-wordcount: '637'
ht-degree: 13%

---

# 開始使用 Campaign Standard 系統管理 {#about-administrating-adobe-campaign}

<table>
<tr><td><img src="assets/do-not-localize/icon_menu.svg" width="60px"><p><a href="#administration-menu">「管理」菜單</a></p></td>
<td><img src="assets/do-not-localize/icon_users.svg" width="60px"><p><a href="#users-security">使用者與安全性</a></p></td>
<td><img src="assets/do-not-localize/icon_channels.svg" width="60px"><p><a href="#channels-configuration">通道配置</a></p></td>
<td><img src="assets/do-not-localize/icon_settings.svg" width="60px"><p><a href="#application-settings">應用程式設定</a></p></td></tr>
</table>

作為基於雲的解決方案，Adobe Campaign為管理員提供了配置應用程式的不同方法。 儘管基礎架構配置由Adobe執行，但功能管理員可以執行下面詳述的各種配置操作。

>[!NOTE]
>
>如果您對實施和配置問題有疑問或請求，請與您的Adobe客戶經理聯繫。

請注意，管理員用戶還可以利用市場活動控制面板來管理每個實例的設定和跟蹤使用情況。 如需詳細資訊，請參閱[專屬文件](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=zh-Hant)。

## 「管理」菜單 {#administration-menu}

<img src="assets/do-not-localize/icon_menu.svg" width="60px">

不同的Adobe Campaign管理操作通過 **[!UICONTROL Administration]** 按一下左上角的Adobe Campaign徽標時可訪問的菜單。 此部分介面只能由平台的功能管理員訪問。

不同的菜單包括：

* [用戶和安全](../../administration/using/about-access-management.md):此菜單允許您管理對平台（用戶、角色、安全組、設備）的訪問。
* [頻道](../../administration/using/about-channel-configuration.md):此菜單將連結到不同平台通道（電子郵件、移動）的技術參數重新分組，以及分類和隔離管理。
* [應用程式設定](../../administration/using/external-accounts.md):此菜單允許您配置不同的應用程式元素（外部帳戶、選項、技術工作流）。
* [開發](../../developing/using/data-model-concepts.md):此菜單允許您管理自定義資源並訪問診斷工具。
* [實例設定](../../administration/using/branding.md):在此菜單中，您可以定義不同品牌並配置其設定（徽標、管理跟蹤、訪問登錄頁的URL域等）。
* [部署](../../automating/using/managing-packages.md):此菜單重新組合包導入和導出選項。
* [客戶指標](../../audiences/using/active-profiles.md):Adobe Campaign提供顯示活動配置檔案數的報告。 此報告僅提供資訊，對計費沒有直接影響。
* [隱私工具](../../start/using/privacy-management.md):此菜單允許您建立GDPR訪問和刪除請求並跟蹤其演變。

## 使用者與安全性 {#users-security}

<img src="assets/do-not-localize/icon_users.svg"  width="60px">

邀請用戶訪問應用程式並管理 **安全組**，這些是在您的組織內共用相同角色和權限的一組用戶。 預設情況下，Adobe Campaign提供 **角色** 允許您定義分配給用戶和用戶組的統一授權。 與 **組織單位**，角色為用戶提供一個過濾後的介面視圖，並定義他們對不同功能的訪問權限。

市場活動標準還允許您監視與安全相關的資訊。 您可以檢索有關用戶通過 **[!UICONTROL Export audits]** 並利用 **[!UICONTROL Licenses]** 螢幕，用於監視組織內已安裝的所有市場活動許可證，以及內部版本號、版本和協定條款等不同資訊。

閱讀全文:

* [使用者管理](../../administration/using/users-management.md)
* [組織單位](../../administration/using/organizational-units.md)
* [角色清單](../../administration/using/list-of-roles.md)
* [管理群組和使用者](../../administration/using/managing-groups-and-users.md)
* [稽核匯出記錄](../../administration/using/auditing-export-logs.md)
* [授權](../../administration/using/licenses.md)

## 通道配置 {#channels-configuration}

<img src="assets/do-not-localize/icon_channels.svg" width="60px">

必須正確配置Adobe Campaign的所有通信通道才能有效發送消息。 **[!UICONTROL Channel]**  菜單允許您管理連結到不同通道的技術參數。

配置各種 **電子郵件** 參數：處理退出、隔離、電子郵件屬性和路由參數的規則、類型規則。 定義路由配置和屬性 **簡訊** 以及簡訊編碼和格式。

設定 **移動應用** 以便能夠使用Adobe Experience PlatformSDK發送In-App消息和推送通知。

閱讀全文:

* [關於頻道設定](../../administration/using/about-channel-configuration.md)
* [設定電子郵件頻道](../../administration/using/configuring-email-channel.md)
* [設定 SMS 通道](../../administration/using/configuring-sms-channel.md)
* [設定行動應用程式](../../administration/using/configuring-a-mobile-application.md)

## 應用程式設定 {#application-settings}

<img src="assets/do-not-localize/icon_settings.svg" width="60px">

Campaign Standard附帶了可配置為滿足您需要的不同應用程式元素。

設定 **外部帳戶**，用於將Adobe Campaign連接到外部伺服器。 訪問Campaign Standard目標映射，並使用 **技術工作流**。

定義一個或多個 **品牌** 為您的組織配置發送 **即時通知** 在重要系統活動的情況下。

閱讀全文:

* [關於 Campaign Standard 設定](../../administration/using/about-campaign-standard-settings.md)
* [外部帳戶](../../administration/using/external-accounts.md)
* [Campaign 中目標定位對應](../../administration/using/target-mappings-in-campaign.md)
* [技術工作流程](../../administration/using/technical-workflows.md)
* [品牌](../../administration/using/branding.md)
* [傳送內部通知](../../administration/using/sending-internal-notifications.md)
