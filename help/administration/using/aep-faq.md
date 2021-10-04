---
title: Adobe Experience Platform SDK與Adobe Campaign整合常見問題集
description: Adobe Experience Platform SDK與Adobe Campaign整合常見問題集
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 6b3c189d-8ddd-4dc0-8831-65ae62e04c70
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '913'
ht-degree: 4%

---

# Experience Platform SDK 整合常見問答集 {#aep-faq}

若要透過Experience PlatformSDK應用程式傳送推播通知和應用程式內訊息，行動應用程式必須在Adobe Experience Platform SDK中設定，並在Adobe Campaign中設定。

下節列出有關此同步的常見問題。

如需推播或應用程式內的詳細資訊，請參閱下列常見問題集：

* [推播通知常見問題集](../../channels/using/about-push-notifications.md#push-faq)
* [應用程式內常見問題集](../../channels/using/in-app-faq.md)
* [與Launch同步技術工作流程常見問題集](../../administration/using/syncwithlaunch-faq.md)

## 開始之前的有用資源 {#resource-mobile-property}

請查看下列資源，以取得有關Adobe Experience Platform SDK和Campaign Standard整合的詳細資訊：

* Launch/Mobile [概述影片](https://www.adobe.com/experience-platform/launch.html#acpl-mobile-video)
* Launch/Mobile [提示與秘訣指南](https://www.adobe.com/content/dam/dx/us/en/products/experience-platform/launch-tag-manager/pdfs/adobe-cloud-platform-launch-tips-and-tricks-sheet.pdf)

## Adobe Experience Platform SDK整合是否可同時適用於Adobe Campaign Standard和Adobe Campaign Classic? {#aep-validity}

是，[!DNL Adobe Experience Platform SDK]整合適用於Adobe Campaign Standard和Adobe Campaign Classic。 您必須透過[!DNL Adobe Launch]安裝對應的&#x200B;**[!UICONTROL Extension]**&#x200B;以啟用整合。

如需關於此項目的詳細資訊，請參閱此[頁面](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard)。

## Adobe Experience Platform SDK整合可在Adobe Campaign中促進哪些功能？ {#aep-capabilities}

請參閱下表以深入了解這些功能。

![](assets/faq.png)

>[!NOTE]
>
>[!DNL Places] 整合包括將事件置於應用程式內訊息的觸發器（推播通知的不適用），透過資料和本機通知支援 [!DNL Places] 擴充設定檔。如需詳細資訊，請參閱此[page](../../channels/using/preparing-and-sending-an-in-app-message.md)。 <br>[!DNL Places] 有限的整合包括以資料擴充設 [!DNL Places] 定檔。

## Adobe Experience Platform SDK整合可在Adobe Campaign Standard中促進哪些使用案例？ {#aep-use-cases}

支援下列使用案例：

* 在促銷活動中取得&#x200B;**[!UICONTROL Mobile Profile]**（由&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (AEP SDK)]** > **[!UICONTROL Mobile Application subscribers]**&#x200B;標籤中的ECID識別）
* 擴充Adobe Campaign中的&#x200B;**[!UICONTROL Mobile Profile]**（需要appSubscriberRcp表格的&#x200B;**[!UICONTROL Custom resource Extension]**）
* 取得用於傳送推送訊息的推送代號（需要使用者選擇加入以接收推送訊息）
* 傳送推送訊息和應用程式內訊息
* 追蹤使用者與推送訊息和應用程式內訊息的互動，並提供相關報表

## 若要在Campaign中取得行動設定檔，我必須執行什麼？ {#mobile-profile-campaign}

要執行此操作，請遵循下列步驟：

1. 在[!DNL Launch]中配置&#x200B;**[!UICONTROL Mobile property]**。
1. 安裝Adobe Campaign Standard擴充功能。 請注意，Adobe Campaign Standard擴充功能也需要&#x200B;**[!UICONTROL Mobile Core]**、**[!UICONTROL Profile]**&#x200B;和&#x200B;**[!UICONTROL Lifecycle]**&#x200B;擴充功能，預設會在[!DNL Launch]中安裝。
   * 使用者應在&#x200B;**[!UICONTROL Mobile Core]**&#x200B;擴充功能中設定工作階段逾時，這會影響生命週期事件的頻率。
   * 設定擴充功能後，使用者應使用適用於iOS的Cocoapods和適用於Android的Gradle，在行動應用程式中新增適當的相依性。 請遵循[此處](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard)指示。
   * 請一律使用最新版本的程式庫。
   * 在行動應用程式中，註冊&#x200B;**[!UICONTROL Campaign]**、**[!UICONTROL UserProfile]**、**[!UICONTROL Identity]**、**[!UICONTROL Lifecycle]**&#x200B;和&#x200B;**[!UICONTROL Signal]**&#x200B;擴充功能。 請遵循[此處](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard#register-the-campaign-standard-extension-with-mobile-core)指示。
   * 註冊擴充功能後，啟動ACPCore。 對於Android，請務必設定Application onCreate()。 請依照Launch中您行動屬性的行動安裝指示中提供的確切指示操作。
   * 也需要下列SDK API。 如[此處](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/lifecycle/lifecycle-extension-in-android)針對Android和此處針對iOS所述，實作生命週期開始和暫停API。
1. 在Adobe Campaign Standard中設定&#x200B;**[!UICONTROL Mobile Property]**。 請依照[此處](../../administration/using/configuring-a-mobile-application.md#channel-specific-config)操作。

## 若要讓行動設定檔在行銷活動中變得更加豐富，我必須做什麼？ {#enrich-mobile-profile}

您必須設定CollectPII回傳（請參閱此[page](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#PIIpostback)），並從SDK實作CollectPII API（請參閱此[page](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#collect-pii)）。

## CollectPII呼叫的觸發頻率為何？ {#collect-pii}

CollectPII呼叫的目標是讓行銷活動中的行動設定檔更為豐富。 每當有新的有意義資訊，客戶想要根據其使用案例和業務需求將其新增至設定檔時，就應觸發此設定檔。

## 可以回應多個觸發事件來觸發CollectPII呼叫嗎？ {#collect-pii-calls}

是. 根據您的業務需求，您可能會因應使用者登入應用程式而引發CollectPII呼叫，或購買某些項目或生命週期事件，或使用者進入地理柵欄等。 總而言之，使用者與應用程式的互動，該應用程式會產生您想要用於設定檔擴充的資訊。

## 我可以只是響應於所有行動事件觸發CollectPII呼叫嗎？ {#collect-pii-events}

CollectPII呼叫的頻率和設計應由業務需求決定，不應因為在DB上造成額外負載而盲目觸發。

### 當我嘗試在Campaign或Launch中存取Adobe Experience Platform應用程式時，有時會收到無法使用的屬性錯誤。 {#aep-error}

這是已知問題，會因代號過期而發生。 您應嘗試登出再登入。

## 若要深入了解Adobe Experience Platform SDK（先前稱為SDK V5），有哪些實用的資源建議？{#resource-aep}

查看下列資源：

* Experience PlatformSDK [檔案](https://aep-sdks.gitbook.io/docs/)
* Launch與Experience PlatformSDK快速入門[檔案](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property)
* 升級至Experience PlatformSDK [檔案](https://aep-sdks.gitbook.io/docs/resources/upgrading-to-aep)
* GithubExperience PlatformSDK [檔案](https://github.com/Adobe-Marketing-Cloud/acp-sdks/)

## 建立推播通知傳送時，我收到錯誤「您在傳送時沒有寫入存取權」。 {#write-access-error}

您應檢查下列項目：

* 行動應用程式應對應至需要建立及傳送推送傳送之使用者的組織單位。 子組織單位的使用者無法使用對應至父組織單位的應用程式來建立推送傳送。

* 建立推送傳送的促銷活動或方案應對應至需要建立及傳送推送傳送之使用者的組織單位。 子組織單位的使用者無法在對應至父組織單位的促銷活動或方案中建立推送傳送。
