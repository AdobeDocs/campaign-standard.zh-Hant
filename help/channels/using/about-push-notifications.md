---
title: 關於推播通知
description: 探索Adobe Campaign推播通知頻道的主要特性。
page-status-flag: never-activated
uuid: 961aaeb5-6948-4fd2-b8d7-de4510c10566
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: push-notifications
discoiquuid: 23b4212e-e878-4922-be20-50fb7fa88ae8
context-tags: mobileApp,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f9632e88b49c2280c76e709376cfb7a7a27abc1f
workflow-type: tm+mt
source-wordcount: '1280'
ht-degree: 2%

---


# 關於推播通知{#about-push-notifications}

>[!CAUTION]
>
>推播通知實作必須由專家使用者執行。 如果您需要協助，請聯絡您的Adobe客戶主管或專業服務合作夥伴。 推播通知是選用功能。 請檢查您的授權合約，並聯絡您的帳戶管理員以啟用它。

Adobe Campaign可讓您將個人化和分段的推播通知傳送至iOS和Android行動裝置。

這些訊息是在您在Adobe Campaign中設定的行動應用程式上，透過運用Experience Platform SDK收到的。 如需詳細資訊，請參閱「使 [用Adobe Experience Platform SDK設定行動應用程式」](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html)。

In Adobe Campaign, mobile profile attributes data sent from mobile device are stored in **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** resource which allows you to define the data that you want to collect from your applications&#39; subscribers.

需要擴充此資源，以收集您要從行動裝置傳送至Adobe Campaign的資料。 若要這麼做，請參閱本 [頁](../../developing/using/extending-the-subscriptions-to-an-application-resource.md) ，以取得詳細步驟。

Adobe Campaign提供兩種推播通知類型：

* **[!UICONTROL Alert/Message/Badge]** 文字通知可讓您傳送含有其他內容（音效、徽章、Deeplink等）的標準文字訊息。 在區段中定 **[!UICONTROL Advanced options]** 義。

   此通知類型可讓您新增標題和訊息，您可在其中使用個人化欄位。 若要個人化您的訊息，請務必選取范 **[!UICONTROL Send push on profiles]** 本。

* **[!UICONTROL Silent push]** 類型通知可用來無訊息地通知應用程式，而不會傳送任何訊息或內容給一般使用者。 此類訊息的典型使用案例是讓應用程式知道伺服器上有可供下載的內容。

可以設定某些特定配置來定義通知行為。 如需詳細資訊，請參閱[本章節](../../channels/using/customizing-a-push-notification.md)。

身為專家使用者，若要定義這些特定組態，請參閱行動應用程式 [技術](https://helpx.adobe.com/campaign/kb/acs-article-list.html)。

>[!NOTE]
>
>隱私權相關法律依國家／地區而異。 有些國家／地區需要您通知使用者行動應用程式收集的資料類型。 請檢查您所在國家／地區的行動應用程式相關法律。 請確定傳送至行動應用程式的推播通知符合Apple（Apple推播通知服務）和Google（Google雲端訊息或Firebase雲端訊息）所指定的必要條件。

**相關內容：**

* [準備和傳送推播通知](../../channels/using/preparing-and-sending-a-push-notification.md)
* [建立多語言推播通知](../../channels/using/creating-a-multilingual-push-notification.md)
* [推播通知報告](../../reporting/using/push-notification-report.md)
* [Campaign Standard行動指南](https://helpx.adobe.com/campaign/kb/acs-mobile.html)

## 必要條件 {#prerequisites}

>[!NOTE]
>若要運用Campaign的推播通知功能，您必須提供。pem格式的有效推播憑證，而不需密碼。
如果您有有效的p12憑證，則可使用線上資源，輕鬆將它轉換為。pem檔案。

傳送推播通知前，您應：

1. 在Adobe Campaign中，請確定您可以存取該 **[!UICONTROL Push notification]** 渠道。 如果您無法存取這些渠道，請連絡您的帳戶團隊。

1. 確認您的使用者擁有Adobe Campaign Standard和Experience Platform Launch中的必要權限。

1. 在Experience Platform Launch中，建立行動屬性。 如需詳細資訊，請 [參閱「設定行動裝置屬性」](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property)。

1. 在Experience Platform Launch中，安裝擴 **[!UICONTROL Adobe Campaign Standard]** 充功能。

1. 在Adobe Campaign Standard中，設定您在Experience Platform Launch中建立的行動裝置屬性。 如需詳細資訊，請 [參閱「在Adobe Campaign中設定Experience Platform Launch應用程式」](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#SettingupyourAdobeExperiencePlatformLaunchapplicationinAdobeCampaign)。

1. 將特定頻道的組態新增至行動應用程式設定。 如需詳細資訊，請參 [閱Adobe Campaign中的頻道特定應用程式設定](../../administration/using/configuring-a-mobile-application.md#channel-specific-config)。

1. 若要支援行動使用案例實作，請參閱有關使用Adobe Experience Platform SDK的擴充功能、Experience Platform Launch規則，以及 [Adobe Campaign Standard支援的行動使用案例中SDK實作的詳細指示](https://helpx.adobe.com/campaign/kb/configure-launch-rules-acs-use-cases.html)。

## 推播通知常見問答集 {#push-faq}

### 若要進一步瞭解推播頻道，有哪些有用的資源建議？ {#resource-push}

查看以下資源：

* [教學影片](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/communication-channels/mobile/push/creating-a-push-notification.html)
* [產品檔案](../../channels/using/about-push-notifications.md)
* 使用AEP SDK檔案進行設 [定](../../administration/using/configuring-a-mobile-application.md)
* [社群頁面](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-standard/ct-p/adobe-campaign-standard-community)

### 我必須做什麼才能在促銷活動中取得推播代號？ {#push-token-acquisition}

請確定布建團隊已在Adobe Campaign Standard中完成布建推播頻道。 從SDK實作setPushIdentifier API。 For more on this, refer to this [page](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard#set-up-push-messaging).

### 在促銷活動中擁有推播Token和ECID後，我還需要傳送推播通知嗎？ {#sending-push}

客戶必須提供。pem格式的有效推播憑證，才能傳送推播通知。 您不需要此憑證的密碼。

### 如果我有。p12憑證而非。pem憑證，該怎麼辦？ {#certificates}

您可以在終端機中執行下列命令，將。p12憑證轉換為。pem憑證。 還提供數種線上資源，以取得轉換指示。

```
openssl pkcs12 -in pushcert.p12 -out pushcert.pem -nodes -clcerts
```

### 如何得知憑證上傳是否成功？ {#certificate-upload}

您將看到以下訊息。

![](assets/faq_2.png)

### 我是否可同時上傳iOS應用程式的「製作」和「沙盒」憑證（Android為N/A）? {#prod-sandbox-certificate}

否，應用程式可在沙盒或生產模式中運作，而且一旦設定後，就無法變更為另一個（即沙盒至生產應用程式）。 我們建議您先在沙盒模式下測試應用程式，然後轉換至生產模式。

若要變更為生產模式，您必須建立其他應用程式。 此外，請務必不要勾選沙盒核取方塊，並上傳生產憑證。

### 我是否可同時上傳iOS和Android憑證？ {#ios-android-credentials}

是的，Campaign同時支援兩個平台，並允許您上傳兩個平台的認證。

### 我已成功上傳推播憑證，但未傳送推播訊息。 {#push-certificates-upload}

請在此處測試您的推播憑證，以確定其有 [效](https://pushtry.com/)。

### 我可以從pushtry.com成功傳送推播通知，但無法透過Campaign傳送。 {#push-not-sending}

請確定您正在遵循此處提供的推送裝載 [指示](../../administration/using/push-payload.md)。

請注意，對於Android,Campaign僅支援資料裝載，不支援通知裝載

### 我已在Adobe Campaign Standard的「管理」區段中設定應用程式，但「傳送」屬性中無法使用「行動應用程式」。 {#mobile-app-unavailable}

應用程式必須已上傳有效的推播憑證，才能在傳送屬性中提供。

### 我已試用此頁面上的所有指示，但無法從促銷活動傳送推播。 {#push-troubleshoot}

請開啟客戶服務票證。

### 推播通知是從Campaign傳送，但媒體檔案未顯示。{#media-file-unavailable}

行動應用程式開發人員需要處理應用程式中媒體檔案的支援。 有時網路頻寬也會妨礙媒體檔案的轉換。 有關其他指 [針](../../administration/using/image-push-notification.md) ，請參閱此頁。

### 我要如何在促銷活動中啟用推送報表？ {#push-reporting-enable}

請遵循下列步驟：

* 設定推播追蹤回傳。 您可在這裡找到 [指示](../../administration/using/configuring-a-mobile-application.md)。
* 從Mobile Core實作trackAction API。 Refer to this [page](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference) for more information.

如需詳細指示，請參閱本 [頁](../../administration/using/push-tracking.md)。

### 哪些報表適用於推播渠道？ {#push-report-available}

Adobe推播促銷活動頻道提供現成可用的報表。 請參閱本 [檔案](../../reporting/using/push-notification-report.md)。

請參閱 [此頁](../../reporting/using/indicator-calculation.md#push-notification-delivery) ，瞭解如何計算每個推播量度。

### 推送和應用程式內訊息是否支援深層連結？ {#deeplink-push}

是的，推送訊息支援深層連結。 深層連結應包括：

* 說明傳送追蹤必須停用才能讓深層連結運作的語言。
* Appsflyer與Branch合作，可進行開發連結追蹤。 如需分支與Adobe Campaign Standard整合的詳細資訊，請參閱本 [頁](https://help.branch.io/using-branch/docs/adobe-campaign-standard-1)。