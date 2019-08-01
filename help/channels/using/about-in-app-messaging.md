---
title: 關於應用程式內傳訊
seo-title: 關於應用程式內傳訊
description: 關於應用程式內傳訊
seo-description: 使用應用程式內訊息顯示行動應用程式中的訊息或警報。
page-status-flag: 從未啓動
uuid: 6784cfc-6db9-41dd-9fb-2e756a5bcp5f
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 頻道
content-type: reference
topic-tags: 應用程式內訊息
discoiquuid: a4168brick-22fb-4ab3-b9 d8-1e76 e76 e1 bdc055
context-tags: 傳送，觸發器，返回
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 74f037ba618639ab61edfb8311adeb44a7a99ebd

---


# About In-App messaging{#about-in-app-messaging}

應用程式內訊息是一個傳訊頻道，可讓您在行動應用程式中使用使用者時顯示訊息。推播通知免費提供給使用者手機通知中心的推播通知。For more information on the push notification channel, refer to this [section](../../channels/using/about-push-notifications.md).

此管道需要與Adobe Experience Platform SDK整合的行動應用程式。這些應用程式必須在Adobe Experience Platform Launch中啓動，才能在Adobe Campaign中針對應用程式內遞送提供。

![](assets/launch_campaign.png)

若要開始在使用Experience Platform SDK的行動應用程式上傳送應用程式內訊息，您必須符合下列必要條件：

1. In Adobe Campaign, make sure you can access the **[!UICONTROL In-App]** channel. 如果無法存取這些渠道，請聯絡您的帳戶團隊。
1. 在Experience Platform Launch中，建立行動應用程式並使用Experience Platform SDK來檢測行動應用程式。

   For more information, refer to the [Set up a mobile property](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property) section in Adobe Launch documentation.

1. In Experience Platform Launch, install the **[!UICONTROL Adobe Campaign Standard]** extension for your mobile application in Experience Platform Launch:

   For more on extensions, refer to the [Configure Campaign Standard Extension in Experience Platform Launch](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard) in Experience Platform Launch documentation.

1. In Experience Platform Launch, configure rules and data elements for your application, see [Configuring your application in Experience Platform Launch](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Step1Createdataelements)

1. Configure your Experience Platform Launch application in Adobe Campaign Standard, see [Setting up your Experience Platform Launch application in Adobe Campaign](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#SettingupyourAdobeLaunchapplicationinAdobeCampaign) .

To learn how to configure Experience Platform SDKs, refer to this [page](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html).

**相關內容：**

* [準備及傳送應用程式內訊息](../../channels/using/preparing-and-sending-an-in-app-message.md)
* [自訂應用程式內訊息](../../channels/using/customizing-an-in-app-message.md)
* [自訂本機通知訊息類型](../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type)
* [在工作流程中傳送應用程式內訊息](../../automating/using/in-app-delivery.md)
* [推送和應用程式內常見問題](https://helpx.adobe.com/campaign/kb/push_inapp_faq.html)