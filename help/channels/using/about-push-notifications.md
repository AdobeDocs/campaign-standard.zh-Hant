---
title: 關於推播通知
description: 探索Adobe Campaign推播通知頻道的主要特性。
page-status-flag: 從未激活
uuid: 961aeb5-6948-4fd2-b8d7-de4510c10566
contentOwner: 紹維亞
products: SG_CAMPAIGN/STANDARD
audience: 頻道
content-type: 參考
topic-tags: 推播通知
discoiquuid: 23b4212e-e878-4922-be20-50fb7fa88ae8
context-tags: mobileApp，概觀
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 關於推播通知{#about-push-notifications}

>[!CAUTION]
>
>推播通知實作必須由專家使用者執行。 如果您需要協助，請聯絡您的Adobe客戶主管或專業服務合作夥伴。 推播通知是選用功能。 請檢查您的授權合約，並聯絡您的帳戶管理員以啟用它。

Adobe Campaign可讓您將個人化和分段的推播通知傳送至iOS和Android行動裝置。

這些訊息是在您在Adobe Campaign中設定的行動應用程式上，透過運用Experience Cloud Mobile SDK V4或Experience Platform SDK收到的。 如需詳細資訊，請參 [閱「使用SDK V4設定行動應用程式」](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html) , [以及「使用Adobe Experience Platform SDK設定行動應用程式」](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html)。

In Adobe Campaign, mobile profile attributes data sent from mobile device are stored in **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** resource which allows you to define the data that you want to collect from your applications' subscribers.

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
* [推播和應用程式內常見問答集](https://helpx.adobe.com/campaign/kb/push_inapp_faq.html)

## 必要條件 {#prerequisites}

>[!NOTE]
>若要運用Campaign的推播通知功能，您必須提供。pem格式的有效推播憑證，而不需密碼。
如果您有有效的p12憑證，則可使用線上資源，輕鬆將它轉換為。pem檔案。

首先，若要開始傳送推播通知，您必須使用SDK V4來設定您的行動應用程式。 您也可以使用Experience Platform SDK來設定行動應用程式。 For more on this, refer to this [page](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html).

傳送推播通知前，您應：

1. 請確定您可以存取Adobe **[!UICONTROL Mobile app]** Campaign中的渠道。
1. 在下列位置設定您的行動應用程式：

   * Adobe Campaign
   * Adobe Mobile services介面

1. 執行行動應用程式的特定設定：

   * 將從Adobe Mobile services介面下載的設定檔與行動應用程式封裝。
   * 將Experience Cloud Mobile SDK整合到您的行動應用程式中。

1. 定義您要向應用程式訂閱者收集的資料。 在Adobe Campaign資料庫中擁有描述檔的行動應用程式的訂閱者，會根據您所定義的條件進行協調。

設定行動應用程式後，您現在可以開始準備和傳送應用程式內訊息。 如需詳細資訊，請參閱「準 [備和傳送推播通知」](../../channels/using/preparing-and-sending-a-push-notification.md)。
