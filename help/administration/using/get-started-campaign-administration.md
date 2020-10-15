---
title: 開始使用 Campaign Standard 管理
description: 探索使用者和權限管理、監控準則、通道特定的配置和應用程式設定準則。
page-status-flag: never-activated
uuid: 64c34729-5c98-4db0-9131-af6dd0e78fb4
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: about-administrating-adobe-campaign
discoiquuid: 5587530a-2308-4be1-9f56-19eeb7a924d5
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '650'
ht-degree: 16%

---


# 開始使用 Campaign Standard 管理 {#about-administrating-adobe-campaign}

<table>
<tr><td><img src="assets/do-not-localize/icon_menu.svg" width="60px"><p><a href="#administration-menu">管理功能表</a></p></td>
<td><img src="assets/do-not-localize/icon_users.svg" width="60px"><p><a href="#users-security">使用者與安全性</a></p></td>
<td><img src="assets/do-not-localize/icon_channels.svg" width="60px"><p><a href="#channels-configuration">頻道設定</a></p></td>
<td><img src="assets/do-not-localize/icon_settings.svg" width="60px"><p><a href="#application-settings">應用程式設定</a></p></td></tr>
</table>

Adobe Campaign是雲端解決方案，為管理員提供不同的方式來設定應用程式。 雖然基礎架構設定由Adobe執行，但功能管理員可執行下列各項設定作業。

>[!NOTE]
>
>如果您對實作和設定事項有任何疑問或要求，請聯絡您的Adobe銷售代表。

## 管理功能表 {#administration-menu}

<img src="assets/do-not-localize/icon_menu.svg" width="60px">

按一下左上角的Adobe Campaign標誌時， **[!UICONTROL Administration]** 可透過可存取的功能表執行不同的Adobe Campaign管理作業。 此部分介面只能由平台的功能管理員存取。

可用的不同功能表包括：

* [使用者與安全性](../../administration/using/about-access-management.md):此菜單允許您管理對平台（用戶、角色、安全組、設備）的訪問。
* [渠道](../../administration/using/about-channel-configuration.md):此功能表會重新分組連結至不同平台通道（電子郵件、行動裝置）的技術參數，以及分類和隔離管理。
* [應用程式設定](../../administration/using/external-accounts.md):此功能表可讓您設定不同的應用程式元素（外部帳戶、選項、技術工作流程）。
* [開發](../../developing/using/data-model-concepts.md):此功能表可讓您管理自訂資源並存取診斷工具。
* [例項設定](../../administration/using/branding.md):此功能表是您定義不同品牌並設定其設定的位置（標誌、管理追蹤、存取著陸頁面的URL網域等）。
* [部署](../../automating/using/managing-packages.md):此菜單重組包導入和導出選項。
* [客戶量度](../../audiences/using/active-profiles.md):Adobe Campaign提供顯示作用中描述檔數目的報表。 此報告僅提供資訊，對帳單沒有直接影響。
* [隱私權工具](https://helpx.adobe.com/tw/campaign/kb/campaign-privacy.html):此功能表可讓您建立GDPR存取和刪除請求，並追蹤其演變。

## 使用者與安全性 {#users-security}

<img src="assets/do-not-localize/icon_users.svg"  width="60px">

邀請使用者存取應用程式並管 **理安全性群組**，這些是一組在您組織內共用相同角色和權限的使用者。 By default, Adobe Campaign offers a set of **roles** which allows you to define unitary authorizations assigned to users and user groups. Combined with **organizational units**, roles give users a filtered view of the interface and define their access to the different features.

Campaign Standard也可讓您監控與安全性相關的資訊。 您可以擷取使用者透過螢幕所執行之資料匯出的相關資訊，並運用螢幕來監控組織內所有已安裝的促銷活動授權，以及不同的資訊，例如組建編號、發行版本和合約條款。 **[!UICONTROL Export audits]****[!UICONTROL Licenses]**

顯示全文:

* [使用者管理](../../administration/using/users-management.md)
* [組織單位](../../administration/using/organizational-units.md)
* [角色清單](../../administration/using/list-of-roles.md)
* [管理群組和使用者](../../administration/using/managing-groups-and-users.md)
* [審核匯出日誌](../../administration/using/auditing-export-logs.md)
* [授權](../../administration/using/licenses.md)

## 頻道設定 {#channels-configuration}

<img src="assets/do-not-localize/icon_channels.svg" width="60px">

Adobe Campaign中的所有通訊管道都必須正確設定，才能有效傳送訊息。功能表 **[!UICONTROL Channel]** ，可讓您管理連結至不同管道的技術參數。

設定各種 **電子郵件** 參數：反彈、隔離、電子郵件屬性和路由參數的處理規則、類型規則。 定義 **SMS通道的路由配置** 、屬性，以及SMS編碼和格式。

設定行 **動應用程式** ，以便能夠使用Adobe Experience Platform SDK傳送應用程式內訊息和推播通知，並透過建立和設定事件來 **設定交易訊息** 。

顯示全文:

* [關於通道設定](../../administration/using/about-channel-configuration.md)
* [設定電子郵件通道](../../administration/using/configuring-email-channel.md)
* [設定 SMS 通道](../../administration/using/configuring-sms-channel.md)
* [設定行動應用程式](../../administration/using/configuring-a-mobile-application.md)
* [設定交易式訊息傳遞](../../administration/using/configuring-transactional-messaging.md)

## 應用程式設定 {#application-settings}

<img src="assets/do-not-localize/icon_settings.svg" width="60px">

Campaign Standard隨附不同的應用程式元素，可依您的需求進行設定。

設定 **外部帳戶**，這些帳戶用於將Adobe Campaign連接至外部伺服器。 存取Campaign Standard目標對應，並使用技術工作流程監控 **您的平台**。

為您的組織定 **義一或多個品牌** ，並設定在應用程式 **** 中傳送即時通知的方式，以防發生重要的系統活動。

顯示全文:

* [關於 Campaign Standard 設定](../../administration/using/about-campaign-standard-settings.md)
* [外部帳戶](../../administration/using/external-accounts.md)
* [Campaign 中鎖定對應](../../administration/using/target-mappings-in-campaign.md)
* [技術工作流程](../../administration/using/technical-workflows.md)
* [品牌推廣](../../administration/using/branding.md)
* [傳送內部通知](../../administration/using/sending-internal-notifications.md)

## 其他資源

* [管理使用者存取權限（視訊）](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/administrating/managing-user-access-rights.html)
* [控制面板文件](https://docs.adobe.com/content/help/zh-Hant/control-panel/using/control-panel-home.html)
