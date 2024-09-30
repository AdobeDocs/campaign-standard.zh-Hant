---
title: Adobe Experience Platform SDK與Adobe Campaign整合常見問題集
description: Adobe Experience Platform SDK與Adobe Campaign整合常見問題集
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 6b3c189d-8ddd-4dc0-8831-65ae62e04c70
source-git-commit: 2f3a0f4233df2915c5b7d293452246c688d69228
workflow-type: tm+mt
source-wordcount: '856'
ht-degree: 1%

---

# Experience Platform SDK整合常見問題集 {#aep-faq}

若要使用Experience Platform SDK應用程式傳送推播通知和應用程式內訊息，必須在Adobe Experience Platform SDK中設定行動應用程式，並在Adobe Campaign中設定。

下節列出此同步的常見問題。

如需推播或應用程式內的詳細資訊，請參閱下列常見問題：

* [推播通知常見問題集](../../channels/using/about-push-notifications.md#push-faq)
* [應用程式內常見問題集](../../channels/using/in-app-faq.md)
* [Adobe Experience Platform 同步常見問答集中的標籤](../../administration/using/syncwithlaunch-faq.md)

## 開始前有用的資源 {#resource-mobile-property}

請參閱下列資源，以取得有關Adobe Experience Platform SDK和Campaign Standard整合的詳細資訊：

* 啟動/行動[概觀影片](https://www.adobe.com/experience-platform/launch.html#acpl-mobile-video){target="_blank"}
* 啟動/行動[提示與秘訣指南](https://www.adobe.com/content/dam/dx/us/en/products/experience-platform/launch-tag-manager/pdfs/adobe-cloud-platform-launch-tips-and-tricks-sheet.pdf)

## Adobe Experience Platform SDK整合是否同時適用於Adobe Campaign Standard和Adobe Campaign Classic？ {#aep-validity}

是，[!DNL Adobe Experience Platform SDK]整合可用於Adobe Campaign Standard和Adobe Campaign Classic。 您必須透過[!DNL Data Collection UI]安裝對應的&#x200B;**[!UICONTROL Extension]**，才能啟用整合。

如需詳細資訊，請參閱此[頁面](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard){target="_blank"}。

## Adobe Experience Platform SDK整合有助於Adobe Campaign中的哪些功能？ {#aep-capabilities}

請參閱下表以進一步瞭解這些功能。

![](assets/faq.png)

>[!NOTE]
>
>[!DNL Places]整合包括將places事件作為應用程式內訊息的觸發器（推播通知不適用），透過[!DNL Places]資料和本機通知支援豐富設定檔。 如需詳細資訊，請參閱此[頁面](../../channels/using/preparing-and-sending-an-in-app-message.md)。 <br>[!DNL Places]有限整合包括使用[!DNL Places]資料擴充設定檔。

## Adobe Experience Platform SDK整合在Adobe Campaign Standard中促進什麼使用案例？ {#aep-use-cases}

支援下列使用案例：

* 在Campaign中取得&#x200B;**[!UICONTROL Mobile Profile]** （由&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (AEP SDK)]** > **[!UICONTROL Mobile Application subscribers]**&#x200B;索引標籤中的ECID識別）
* 擴充Adobe Campaign中的&#x200B;**[!UICONTROL Mobile Profile]** （需要appSubscriberRcp資料表的&#x200B;**[!UICONTROL Custom resource Extension]**）
* 取得用於傳送推播訊息的推播權杖（需要使用者選擇加入以接收推播訊息）
* 傳送推播和應用程式內訊息
* 追蹤使用者與推播和應用程式內訊息的互動，並提供相關報表

## 在Campaign中取得行動設定檔需要做什麼？ {#mobile-profile-campaign}

要執行此操作，請遵循下列步驟：

1. 在[!DNL Launch]中設定&#x200B;**[!UICONTROL Mobile property]**。
1. 安裝Adobe Campaign Standard擴充功能。 請注意，Adobe Campaign Standard擴充功能還需要&#x200B;**[!UICONTROL Mobile Core]**、**[!UICONTROL Profile]**&#x200B;和&#x200B;**[!UICONTROL Lifecycle]**&#x200B;擴充功能，這些擴充功能預設安裝在[!DNL Launch]中。
   * 使用者應在&#x200B;**[!UICONTROL Mobile Core]**&#x200B;擴充功能中設定工作階段逾時，這會影響生命週期事件的頻率。
   * 設定擴充功能後，使用者應使用iOS的Cocoapods和Android的Gradle，在行動應用程式中新增適當的相依性。 請依照[這裡](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard)的指示操作。
   * 一律採用最新版本的程式庫。
   * 在行動應用程式中，註冊&#x200B;**[!UICONTROL Campaign]**、**[!UICONTROL UserProfile]**、**[!UICONTROL Identity]**、**[!UICONTROL Lifecycle]**&#x200B;和&#x200B;**[!UICONTROL Signal]**&#x200B;擴充功能。 請依照[這裡](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/#register-the-campaign-standard-extension-with-mobile-core)的指示操作。
   * 註冊擴充功能後，請啟動ACPCore。 若為Android，請務必設定onCreate()。 請依照Launch中行動屬性的行動安裝指示中提供的確切指示操作。
   * 您也需要下列SDK API。 實作生命週期開始和暫停API，如同[這裡](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/android)適用於Android，這裡適用於iOS。
1. 在Adobe Campaign Standard中設定&#x200B;**[!UICONTROL Mobile Property]**。 請依照程式[這裡](../../administration/using/configuring-a-mobile-application.md#channel-specific-config)。

## 為了擴充Campaign中的行動設定檔，我必須做什麼？ {#enrich-mobile-profile}

您必須設定CollectPII回傳（請參閱此[頁面](../../administration/using/configuring-rules-launch.md#pii-postback)）並從SDK實作CollectPII API （請參閱此[頁面](https://developer.adobe.com/client-sdks/documentation/mobile-core/api-reference)）。

## CollectPII呼叫的引發頻率為何？ {#collect-pii}

CollectPII呼叫的目標是擴充Campaign中的行動設定檔。 每當有客戶根據其使用案例和業務需求想要新增至描述檔的具意義新資訊時，即應引發此事件。

## CollectPII呼叫是否可因應多個觸發事件而引發？ {#collect-pii-calls}

是。 根據您的業務需求，您可能會引發CollectPII呼叫以回應使用者登入應用程式、購買某物件或生命週期事件或使用者進入地理柵欄等。 總而言之，使用者與應用程式的互動，會產生您要用於設定檔擴充的資訊。

## 我可以直接觸發CollectPII呼叫來回應所有行動事件嗎？ {#collect-pii-events}

CollectPII呼叫的頻率和設計應該由業務需求決定，並且不應該盲目引發，因為這會在DB上產生額外負載。

### 當我嘗試在Campaign或Launch中存取Adobe Experience Platform應用程式時，有時會收到無法使用屬性錯誤。 {#aep-error}

這是已知問題，而且會因為權杖過期而發生。 您應該嘗試登出並登入。

## 進一步瞭解Adobe Experience Platform SDK （原稱為SDK V5）時，建議使用哪些實用資源？{#resource-aep}

檢視下列資源：

* Experience PlatformSDK [檔案](https://developer.adobe.com/client-sdks/documentation/)
* Launch &amp; Experience Platform SDK快速入門[檔案](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/)
* 升級至Experience Platform SDK [檔案](https://developer.adobe.com/client-sdks/resources/upgrade-platform-sdks/)
* GithubExperience PlatformSDK [檔案](https://github.com/Adobe-Marketing-Cloud/acp-sdks/)

## 建立推播通知傳送時，我收到「您沒有傳送的寫入許可權」錯誤。 {#write-access-error}

您應檢查下列專案：

* 行動應用程式應對應至需要建立和傳送推播傳遞之使用者的組織單位。 子組織單位的使用者無法使用對應至父組織單位的應用程式來建立推播傳遞。

* 在其中建立推播傳遞的行銷活動或方案，應對應至需要建立和傳送推播傳遞之使用者的組織單位。 子組織單位的使用者無法在對應至父組織單位的行銷活動或方案中建立推播傳遞。
