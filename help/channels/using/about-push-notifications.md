---
title: 關於推播通知
seo-title: 關於推播通知
description: 關於推播通知
seo-description: 探索Adobe Campaign推播通知頻道的主要細節。
page-status-flag: 從未啓動
uuid: 961aaeb5-6948-4fd2-b8 d7-de4510 c10566
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 頻道
content-type: reference
topic-tags: 推播通知
discoiquuid: 23b4212e-e878-4922-be20-50fb7 fa88 ae8
context-tags: MobileApp，概觀
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 80e65c3fedc5452105c296144a683948daa69150

---


# About push notifications{#about-push-notifications}

>[!CAUTION]
>
>推播通知實作必須由專家使用者執行。如果需要協助，請聯絡您的Adobe銷售代表或專業服務合作夥伴。推播通知是選用功能。請檢查您的授權合約，並聯絡您的帳戶管理員以啓用它。

Adobe Campaign可讓您將個人化和分段推播通知傳送至iOS和Android行動裝置。

這些訊息會透過運用Experience Cloud Mobile SDK V或Experience Platform SDK，在您在Adobe Campaign中設定的行動應用程式中收到。For more information on this, refer to [Configuring a mobile application using SDK V4](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html) and [Configuring a mobile application using Adobe Experience Platform SDKs](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html).

In Adobe Campaign, mobile profile attributes data sent from mobile device are stored in **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** resource which allows you to define the data that you want to collect from your applications' subscribers.

此資源需要延伸，以收集您要從行動裝置傳送至Adobe Campaign的資料。To do so, refer to this [page](../../developing/using/extending-the-subscriptions-to-an-application-resource.md) for the detailed steps.

Adobe Campaign提供兩種推播通知：

* **[!UICONTROL Alert/Message/Badge]** 文字通知可讓您以其他內容傳送標準文字訊息(聲音、徽章、深層連結等)that you can define in the **[!UICONTROL Advanced options]** section.

   此通知類型可讓您新增標題和可使用個人化欄位的訊息。To be able to personalize your message, make sure you select the **[!UICONTROL Send push on profiles]** template.

* **[!UICONTROL Silent push]** 文字通知可用來無訊息地通知應用程式，而不會對使用者提供任何訊息或內容。此類訊息的典型使用案例，是讓應用程式知道伺服器上有可用的內容。

您可以設定某些特定設定來定義通知行為。For more on this, refer to [this section](../../channels/using/customizing-a-push-notification.md).

As an expert user, to define these specific configurations, refer to the mobile app [technotes](https://helpx.adobe.com/campaign/kb/acs-article-list.html).

>[!NOTE]
>
>關於隱私權的法律因國家/地區而異。有些國家要求您通知使用者行動應用程式收集到的資料類型。請檢查您所在國家/地區的行動應用程式相關法律。確定傳送至行動應用程式的推播通知符合Apple(Apple Push Notification Service)和Google(Google Cloud Messaging或Firebase Cloud Messaging)所指定的必要條件和條件。

**相關內容：**

* [準備和傳送推播通知](../../channels/using/preparing-and-sending-a-push-notification.md)
* [建立多語言推播通知](../../channels/using/creating-a-multilingual-push-notification.md)
* [在工作流程中傳送推播通知](../../automating/using/push-notification-delivery.md)
* [推送和應用程式內常見問題](https://helpx.adobe.com/campaign/kb/push_inapp_faq.html)

## Prerequisites {#prerequisites}

>[!NOTE]
>若要利用Campaign中的推播通知功能，您必須提供有效的推播憑證，而且不含密碼。
如果您有有效的p12憑證，可以使用線上資源輕鬆將它轉換為. pem檔案。

首先，若要開始傳送推播通知，您需要使用SDK V設定行動應用程式。您也可以使用Experience Platform SDK設定行動應用程式。For more on this, refer to this [page](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html).

傳送推播通知之前，您應先：

1. Make sure you can access the **[!UICONTROL Mobile app]** channel in Adobe Campaign.
1. 設定您的行動應用程式：

   * Adobe Campaign
   * Adobe Mobile Services介面

1. 執行行動應用程式的特定設定：

   * 將從Adobe Mobile Services介面下載的組態檔封裝為行動應用程式。
   * 將Experience Cloud Mobile SDK整合至您的行動應用程式。

1. 定義您要從應用程式訂閱者收集的資料。在Adobe Campaign資料庫中擁有描述檔的行動應用程式訂閱者，會根據您定義的標準進行協調。

在設定行動應用程式後，您現在可以開始準備和傳送您的應用程式內訊息。For more on this, refer to [Preparing and sending a push notification](../../channels/using/preparing-and-sending-a-push-notification.md).
