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
source-git-commit: 8111dfd2fd3cf254f73d0b01917d606b0a70aa84

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

* **[!UICONTROL Alert/Message/Badge]** 文字通知可讓您傳送含有其他內容（音效、徽章、Deeplink等）的標準文字訊息。在區段中定 **[!UICONTROL Advanced options]** 義。

   此通知類型可讓您新增標題和訊息，您可在其中使用個人化欄位。 若要個人化您的訊息，請務必選取范 **[!UICONTROL Send push on profiles]** 本。

* **[!UICONTROL Silent push]** 類型通知可用來無訊息地通知應用程式，而不會傳送任何訊息或內容給一般使用者。 此類訊息的典型使用案例是讓應用程式知道伺服器上有可供下載的內容。

可以設定某些特定配置來定義通知行為。 如需詳細資訊，請參閱[本小節](../../channels/using/customizing-a-push-notification.md)。

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

1. 將特定頻道的組態新增至行動應用程式設定。 如需詳細資訊，請參 [閱Adobe Campaign中的頻道特定應用程式設定](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#ChannelspecificapplicationconfigurationinAdobeCampaign)。

1. 若要支援行動使用案例實作，請參閱有關使用Adobe Experience Platform SDK的擴充功能、Experience Platform Launch規則，以及 [Adobe Campaign Standard支援的行動使用案例中SDK實作的詳細指示](https://helpx.adobe.com/campaign/kb/configure-launch-rules-acs-use-cases.html)。