---
title: Adobe Experience PlatformSDK和Adobe Campaign整合常見問題
description: Adobe Experience PlatformSDK和Adobe Campaign整合常見問題
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 6b3c189d-8ddd-4dc0-8831-65ae62e04c70
source-git-commit: bfba6b156d020e8d2656239e713d2d24625bda54
workflow-type: tm+mt
source-wordcount: '907'
ht-degree: 4%

---

# Experience Platform SDK 整合常見問答集 {#aep-faq}

要使用Experience PlatformSDK應用程式發送推送通知和In-App消息，必須在Adobe Experience PlatformSDK中設定移動應用程式，並在Adobe Campaign配置。

下面一節列出了有關此同步的常見問題。

有關推送或In-App的詳細資訊，請參閱以下常見問題：

* [推送通知常見問題](../../channels/using/about-push-notifications.md#push-faq)
* [應用程式內常見問題集](../../channels/using/in-app-faq.md)
* [與啟動同步技術工作流常見問題](../../administration/using/syncwithlaunch-faq.md)

## 啟動前的有用資源 {#resource-mobile-property}

有關Adobe Experience PlatformSDK和Campaign Standard整合的詳細資訊，請查看以下資源：

* 啟動/移動 [概述視頻](https://www.adobe.com/experience-platform/launch.html#acpl-mobile-video)
* 啟動/移動 [提示和技巧指南](https://www.adobe.com/content/dam/dx/us/en/products/experience-platform/launch-tag-manager/pdfs/adobe-cloud-platform-launch-tips-and-tricks-sheet.pdf)

## Adobe Experience PlatformSDK整合是否可用於Adobe Campaign Standard和Adobe Campaign Classic? {#aep-validity}

是的， [!DNL Adobe Experience Platform SDK] Adobe Campaign Standard和Adobe Campaign Classic都可進行一體化。 必須安裝相應的 **[!UICONTROL Extension]** 通過 [!DNL Adobe Launch] 以啟用整合。

如需關於此項目的詳細資訊，請參閱此[頁面](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard)。

## Adobe Experience PlatformSDK整合在Adobe Campaign有哪些功能？ {#aep-capabilities}

請參閱下表以瞭解有關這些功能的詳細資訊。

![](assets/faq.png)

>[!NOTE]
>
>[!DNL Places] 整合包括將事件作為In-App消息的觸發器（N/A用於Push通知），使用豐富的配置檔案 [!DNL Places] 資料和本地通知支援。 請參閱此 [頁](../../channels/using/preparing-and-sending-an-in-app-message.md) 的子菜單。 <br>[!DNL Places] 有限整合包括豐富配置檔案 [!DNL Places] 資料。

## Adobe Experience PlatformSDK整合在Adobe Campaign Standard有什麼用例？ {#aep-use-cases}

支援以下使用案例：

* 獲取 **[!UICONTROL Mobile Profile]** 市場活動中（由中的ECID標識） **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (AEP SDK)]** > **[!UICONTROL Mobile Application subscribers]** )
* 豐富 **[!UICONTROL Mobile Profile]** 在Adobe Campaign **[!UICONTROL Custom resource Extension]** appSubscriberRcp表)
* 獲取用於發送推送消息的推送令牌（需要用戶選擇加入以接收推送消息）
* 發送推送和應用內消息
* 跟蹤用戶與推送和應用內消息的交互，並提供有關此資訊的報告

## 在活動中獲取移動配置檔案時，我必須做什麼？ {#mobile-profile-campaign}

要執行此操作，請遵循下列步驟：

1. 配置 **[!UICONTROL Mobile property]** 在 [!DNL Launch]。
1. 安裝Adobe Campaign Standard分機。 注意，Adobe Campaign Standard分機也要求 **[!UICONTROL Mobile Core]**。 **[!UICONTROL Profile]** 和 **[!UICONTROL Lifecycle]** 預設安裝的擴展 [!DNL Launch]。
   * 用戶應在中配置會話超時 **[!UICONTROL Mobile Core]** 影響生命週期事件頻率的擴展。
   * 配置擴展後，用戶應使用Cocoapods for iOS和Gradle for Android在Mobile App中添加適當的依賴項。 按照指示 [這裡](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard)。
   * 始終採用庫的最新版本。
   * 在Mobile App中，註冊 **[!UICONTROL Campaign]**。 **[!UICONTROL UserProfile]**。 **[!UICONTROL Identity]**。 **[!UICONTROL Lifecycle]** 和 **[!UICONTROL Signal]** 擴展。 按照指示 [這裡](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard#register-the-campaign-standard-extension-with-mobile-core)。
   * 註冊擴展後，啟動ACPCore。 對於Android，請確保setApplication onCreate()。 按照Launch中Mobile Property的Mobile Install Instructions中提供的確切說明進行操作。
   * 還需要以下SDK API。 實施生命週期啟動和暫停API（如所述） [這裡](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/lifecycle/lifecycle-extension-in-android) 安卓和iOS。
1. 配置 **[!UICONTROL Mobile Property]** 在Adobe Campaign Standard。 按照過程操作 [這裡](../../administration/using/configuring-a-mobile-application.md#channel-specific-config)。

## 為了豐富活動中的移動配置檔案，我必須做什麼？ {#enrich-mobile-profile}

您必須配置CollectPII後退（請參閱此） [頁](../../administration/using/configuring-rules-launch.md#pii-postback))並從SDK中實現CollectPII API(請參閱 [頁](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#collect-pii))。

## CollectPII調用應被激發的頻率是多長？ {#collect-pii}

CollectPII呼叫的目的是豐富Mobile Profile在Campig中的內容。 當客戶希望根據其使用案例和業務需要將新的有意義資訊添加到配置檔案時，應將其解除。

## 是否可以響應多個觸發事件來激發CollectPII調用？ {#collect-pii-calls}

是. 根據您的業務需要，您可能會響應用戶登錄應用程式而觸發CollectPII呼叫，或者購買某些內容或生命週期事件或用戶進入地理序列等。 總而言之，用戶與應用程式的交互，該應用程式生成您希望用於Profile濃縮的資訊。

## 我是否只能響應所有移動事件而觸發CollectPII呼叫？ {#collect-pii-events}

CollectPII調用的頻率和設計應根據業務需要而定，不應因為它給資料庫帶來額外負載而盲目地觸發。

### 當我嘗試訪問「活動」或「啟動」中的「Adobe Experience Platform應用」時，我有時會遇到一個不可用屬性錯誤。 {#aep-error}

這是已知問題，由於令牌過期而發生。 您應嘗試登錄並登錄。

## 要瞭解有關Adobe Experience PlatformSDK（以前稱為SDK V5）的更多資訊，有哪些有用的資源建議？{#resource-aep}

簽出以下資源：

* Experience PlatformSDK [文檔](https://aep-sdks.gitbook.io/docs/)
* 啟動和Experience PlatformSDK入門 [文檔](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property)
* 升級到Experience PlatformSDK [文檔](https://aep-sdks.gitbook.io/docs/resources/upgrading-to-aep)
* GithubExperience PlatformSDK [文檔](https://github.com/Adobe-Marketing-Cloud/acp-sdks/)

## 建立推送通知傳遞時，我遇到錯誤「您在傳遞時沒有寫權限」。 {#write-access-error}

您應檢查以下內容：

* 應將移動應用映射到需要建立和發送推送遞送的用戶的組織單位。 子組織單位的用戶無法使用映射到父組織單位的應用建立推送傳遞。

* 建立推送交貨的市場活動或方案應映射到需要建立和發送推送交貨的用戶的組織單位。 子組織單位的用戶無法在映射到父組織單位的市場活動或方案中建立推送傳遞。
