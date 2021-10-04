---
title: 開始使用 Campaign Standard 系統管理
description: 探索使用者和權限管理、監控準則、通道特定的配置和應用程式設定準則。
audience: administration
content-type: reference
topic-tags: about-administrating-adobe-campaign
feature: Access Management
role: Admin
level: Experienced
exl-id: 9676b5e8-4c34-4848-8616-235e0bac5d6b
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '636'
ht-degree: 15%

---

# 開始使用 Campaign Standard 系統管理 {#about-administrating-adobe-campaign}

<table>
<tr><td><img src="assets/do-not-localize/icon_menu.svg" width="60px"><p><a href="#administration-menu">管理功能表</a></p></td>
<td><img src="assets/do-not-localize/icon_users.svg" width="60px"><p><a href="#users-security">使用者與安全性</a></p></td>
<td><img src="assets/do-not-localize/icon_channels.svg" width="60px"><p><a href="#channels-configuration">通道配置</a></p></td>
<td><img src="assets/do-not-localize/icon_settings.svg" width="60px"><p><a href="#application-settings">應用程式設定</a></p></td></tr>
</table>

Adobe Campaign是雲端型解決方案，為管理員提供不同的應用程式設定方式。 雖然基礎架構配置由Adobe執行，但功能管理員可以執行以下詳細說明的各種配置操作。

>[!NOTE]
>
>若您對實作和設定有任何疑問或要求，請聯絡您的Adobe帳戶主管。

請注意，管理員使用者也可以運用「Campaign控制面板」來管理每個執行個體的設定並追蹤每個執行個體的使用方式。 如需詳細資訊，請參閱[專屬文件](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=zh-Hant)。

## 管理功能表 {#administration-menu}

<img src="assets/do-not-localize/icon_menu.svg" width="60px">

按一下左上角的Adobe Campaign標誌時，會透過&#x200B;**[!UICONTROL Administration]**&#x200B;功能表執行不同的Adobe Campaign管理作業。 此部分的介面只能由平台的功能管理員存取。

可用的不同功能表包括：

* [使用者與安全性](../../administration/using/about-access-management.md):此功能表可讓您管理對平台（使用者、角色、安全群組、裝置）的存取權。
* [管道](../../administration/using/about-channel-configuration.md):此功能表會重新分組連結至不同平台通道（電子郵件、行動裝置）的技術參數，以及分類和隔離管理。
* [應用程式設定](../../administration/using/external-accounts.md):此功能表可讓您設定不同的應用程式元素（外部帳戶、選項、技術工作流程）。
* [開發](../../developing/using/data-model-concepts.md):此功能表可讓您管理自訂資源並存取診斷工具。
* [執行個體設定](../../administration/using/branding.md):您可在此功能表定義不同品牌並設定其設定（標誌、管理追蹤、存取登錄頁面的URL網域等）。
* [部署](../../automating/using/managing-packages.md):此功能表會重新分組套件匯入和匯出選項。
* [客戶量度](../../audiences/using/active-profiles.md):Adobe Campaign提供顯示作用中設定檔數目的報表。此報表僅提供資訊，對帳單沒有直接影響。
* [隱私權工具](../../start/using/privacy-management.md):此功能表可讓您建立GDPR存取和刪除請求，並追蹤其演變。

## 使用者與安全性 {#users-security}

<img src="assets/do-not-localize/icon_users.svg"  width="60px">

邀請用戶訪問應用程式並管理&#x200B;**安全組**，這些組是一組在您的組織內共用相同角色和權限的用戶。 依預設，Adobe Campaign提供一組&#x200B;**角色**，可讓您定義指派給使用者和使用者群組的統一授權。 角色與&#x200B;**組織單位**&#x200B;結合後，可讓使用者檢視介面的篩選檢視，並定義其對不同功能的存取權。

Campaign Standard也可讓您監控安全相關資訊。 您可以透過&#x200B;**[!UICONTROL Export audits]**&#x200B;畫面擷取使用者執行之資料匯出的相關資訊，並運用&#x200B;**[!UICONTROL Licenses]**&#x200B;畫面來監控組織內所有已安裝的Campaign授權，以及不同資訊，例如組建編號、發行版本和合約條款。

顯示全文:

* [使用者管理](../../administration/using/users-management.md)
* [組織單位](../../administration/using/organizational-units.md)
* [角色清單](../../administration/using/list-of-roles.md)
* [管理群組和使用者](../../administration/using/managing-groups-and-users.md)
* [稽核匯出記錄](../../administration/using/auditing-export-logs.md)
* [授權](../../administration/using/licenses.md)

## 通道配置 {#channels-configuration}

<img src="assets/do-not-localize/icon_channels.svg" width="60px">

Adobe Campaign中的所有通信通道必須正確配置才能有效發送消息。,**[!UICONTROL Channel]**&#x200B;菜單允許您管理連結到不同通道的技術參數。

設定各種&#x200B;**email**&#x200B;參數：退信、隔離、電子郵件屬性和路由參數、類型規則的處理規則。 定義&#x200B;**SMS**&#x200B;通道的路由配置和屬性，以及SMS編碼和格式。

設定&#x200B;**行動應用程式**，以便能使用Adobe Experience Platform SDK傳送應用程式內訊息和推播通知。

顯示全文:

* [關於頻道設定](../../administration/using/about-channel-configuration.md)
* [設定電子郵件頻道](../../administration/using/configuring-email-channel.md)
* [設定 SMS 通道](../../administration/using/configuring-sms-channel.md)
* [設定行動應用程式](../../administration/using/configuring-a-mobile-application.md)

## 應用程式設定 {#application-settings}

<img src="assets/do-not-localize/icon_settings.svg" width="60px">

Campaign Standard隨附不同的應用程式元素，可依您的需求進行設定。

設定用於將Adobe Campaign連接到外部伺服器的&#x200B;**外部帳戶**。 存取Campaign Standard目標對應，並使用&#x200B;**技術工作流程**&#x200B;監控您的平台。

為您的組織定義一或多個&#x200B;**品牌**，並在發生重要系統活動時設定應用程式內的&#x200B;**即時通知**&#x200B;傳送。

顯示全文:

* [關於 Campaign Standard 設定](../../administration/using/about-campaign-standard-settings.md)
* [外部帳戶](../../administration/using/external-accounts.md)
* [Campaign 中目標定位對應](../../administration/using/target-mappings-in-campaign.md)
* [技術工作流程](../../administration/using/technical-workflows.md)
* [品牌](../../administration/using/branding.md)
* [傳送內部通知](../../administration/using/sending-internal-notifications.md)
