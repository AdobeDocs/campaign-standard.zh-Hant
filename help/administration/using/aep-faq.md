---
solution: Campaign Standard
product: campaign
title: Adobe Experience Platform SDK與Adobe Campaign整合常見問答集
description: Adobe Experience Platform SDK與Adobe Campaign整合常見問答集
audience: administration
content-type: reference
topic-tags: configuring-channels
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '914'
ht-degree: 4%

---


# Experience Platform SDK 整合常見問答集 {#aep-faq}

若要使用Experience Platform SDK應用程式傳送推播通知和應用程式內訊息，行動應用程式必須在Adobe Experience Platform SDK中設定，並在Adobe Campaign中設定。

下節列出了有關此同步的常見問題。

如需推播或應用程式內的詳細資訊，請參閱下列常見問答集：

* [推播通知常見問答集](../../channels/using/about-push-notifications.md#push-faq)
* [應用程式內常見問答集](../../channels/using/about-in-app-messaging.md#in-app-faq)
* [與Launch技術工作流程同步常見問答集](../../administration/using/syncwithlaunch-faq.md)

## 啟動{#resource-mobile-property}之前的有用資源

如需Adobe Experience Platform SDK與Campaign Standard整合的詳細資訊，請參閱下列資源：

* 啟動／行動[概觀視訊](https://www.adobe.com/experience-platform/launch.html#acpl-mobile-video)
* 啟動／行動[秘訣與訣竅指南](https://www.adobe.com/content/dam/www/us/en/experience-platform/launch-tag-manager/pdfs/adobe-cloud-platform-launch-tips-and-tricks-sheet.pdf)

## Adobe Experience Platform SDK整合是否適用於Adobe Campaign Standard和Adobe Campaign Classic?{#aep-validity}

是的，[!DNL Adobe Experience Platform SDK]整合適用於Adobe Campaign Standard和Adobe Campaign Classic。 您必須透過[!DNL Adobe Launch]安裝對應的&#x200B;**[!UICONTROL Extension]**&#x200B;以啟用整合。

如需關於此項目的詳細資訊，請參閱此[頁面](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard)。

## Adobe Experience Platform SDK整合可在Adobe Campaign中提供哪些功能？{#aep-capabilities}

請參閱下表以進一步瞭解這些功能。

![](assets/faq.png)

>[!NOTE]
>
>[!DNL Places] 整合包含將事件置為應用程式內訊息的觸發器（推播通知不適用），以豐富資料和本機通 [!DNL Places] 知支援的描述檔。如需詳細資訊，請參閱此[頁面](../../channels/using/preparing-and-sending-an-in-app-message.md)。 <br>[!DNL Places] 有限的整合包括豐富資料的個 [!DNL Places] 人檔案。

## Adobe Experience Platform SDK整合可在Adobe Campaign Standard中促進哪些使用案例？{#aep-use-cases}

支援下列使用案例：

* 在促銷活動中取得&#x200B;**[!UICONTROL Mobile Profile]**（由&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (AEP SDK)]** > **[!UICONTROL Mobile Application subscribers]**&#x200B;標籤中的ECID識別）
* 在Adobe Campaign中豐富&#x200B;**[!UICONTROL Mobile Profile]**&#x200B;內容（需要appSubscriberRcp表格的&#x200B;**[!UICONTROL Custom resource Extension]**）
* 取得傳送推播訊息的推播Token（需要使用者選擇加入才能接收推播訊息）
* 傳送推播和應用程式內訊息
* 追蹤使用者與推播和應用程式內訊息的互動，並提供相關報告

## 在Campaign中取得行動設定檔時，我必須做什麼？{#mobile-profile-campaign}

要執行此操作，請遵循下列步驟：

1. 在[!DNL Launch]中配置&#x200B;**[!UICONTROL Mobile property]**。
1. 安裝Adobe Campaign Standard擴充功能。 請注意，Adobe Campaign Standard擴充功能也需要&#x200B;**[!UICONTROL Mobile Core]**、**[!UICONTROL Profile]**&#x200B;和&#x200B;**[!UICONTROL Lifecycle]**&#x200B;擴充功能，預設會安裝在[!DNL Launch]中。
   * 使用者應在&#x200B;**[!UICONTROL Mobile Core]**&#x200B;擴充功能中設定工作階段逾時，這會影響生命週期事件的頻率。
   * 在設定擴充功能後，使用者應使用iOS適用的Cocoapods和Android適用的Gradle，在行動應用程式中新增適當的相依性。 請遵循[此處](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard)的指示。
   * 請隨時取用最新版的程式庫。
   * 在行動應用程式中，註冊&#x200B;**[!UICONTROL Campaign]**、**[!UICONTROL UserProfile]**、**[!UICONTROL Identity]**、**[!UICONTROL Lifecycle]**&#x200B;和&#x200B;**[!UICONTROL Signal]**&#x200B;擴充功能。 請遵循[此處](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard#register-the-campaign-standard-extension-with-mobile-core)的指示。
   * 註冊擴充功能後，請啟動ACPCore。 若是Android，請務必設定Application onCreate()。 請依照Launch中「行動裝置屬性」的「行動裝置安裝指示」中提供的確切指示進行。
   * 您也需要使用下列SDK API。 如[此處](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/lifecycle/lifecycle-extension-in-android)所述，實作生命週期開始和暫停API（適用於Android），以及此處適用於iOS。
1. 在Adobe Campaign Standard中設定&#x200B;**[!UICONTROL Mobile Property]**。 請按照[此處](../../administration/using/configuring-a-mobile-application.md#channel-specific-config)的步驟操作。

## 為了豐富促銷活動中的行動設定檔，我必須做什麼？{#enrich-mobile-profile}

您必須設定CollectPII回傳（請參閱此[page](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#PIIpostback)），並從SDK實作CollectPII API（請參閱此[page](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#collect-pii)）。

## 觸發CollectPII呼叫的頻率為何？{#collect-pii}

CollectPII呼叫的目的是豐富促銷活動中的行動設定檔。 當客戶想要新增新的有意義資訊至描述檔時，應視其使用案例和業務需求而觸發。

## CollectPII呼叫是否可回應多個觸發事件？{#collect-pii-calls}

是. 視您的業務需求而定，您可能會根據使用者登入應用程式而觸發CollectPII呼叫，或購買某些內容、生命週期事件或使用者輸入地理序列等。 總而言之，使用者與應用程式的互動，此應用程式會產生您想要用於擴充描述檔的資訊。

## 我是否只能針對所有行動事件觸發CollectPII呼叫？{#collect-pii-events}

CollectPII呼叫的頻率和設計應根據業務需求而定，不應當在DB上產生額外負載時盲目引發。

### 當我嘗試在Campaign或Launch中存取Adobe Experience Platform應用程式時，有時會出現屬性無法使用的錯誤。{#aep-error}

這是已知問題，會因為代號過期而發生。 您應嘗試登入。

## 若要進一步瞭解Adobe Experience Platform SDK（之前稱為SDK V5），有哪些有用的資源建議？{#resource-aep}

查看以下資源：

* Experience Platform SDK [說明檔案](https://aep-sdks.gitbook.io/docs/)
* Launch &amp; Experience Platform SDK [說明檔案](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property)快速入門
* 升級至Experience Platform SDK [說明檔案](https://aep-sdks.gitbook.io/docs/resources/upgrading-to-aep)
* Github Experience Platform SDK [documentation](https://github.com/Adobe-Marketing-Cloud/acp-sdks/)

## 我在建立推播通知傳送時收到錯誤「您在傳送時沒有寫入存取權」。{#write-access-error}

您應檢查下列項目：

* 行動應用程式應對應至需要建立和傳送推播傳送之使用者的組織單位。 子組織單位的使用者無法使用映射至父組織單位的應用程式來建立推送傳送。

* 建立推播傳送的促銷活動或方案應對應至需要建立和傳送推播傳送之使用者的組織單位。 子組織單位的使用者無法在映射至父組織單位的促銷活動或方案中建立推播傳送。