---
title: 關於應用程式內訊息傳送
description: 使用應用程式內傳訊在行動應用程式內顯示訊息或警報。
page-status-flag: 從未激活
uuid: 6784cdfc-6db9-41dd-9fbb-2e756a5bcb5f
contentOwner: 紹維亞
products: SG_CAMPAIGN/STANDARD
audience: 頻道
content-type: 參考
topic-tags: 應用程式內訊息
discoiquuid: a4168cfb-22bf-4ab3-b9d8-6e76e1bdc055
context-tags: 傳送，觸發器，返回
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 關於應用程式內訊息傳送{#about-in-app-messaging}

應用程式內訊息是傳訊渠道，可讓您在使用者在行動應用程式內活動時顯示訊息。 此訊息類型免費提供至使用者電話通知中心的推播通知。 如需推播通知頻道的詳細資訊，請參閱此 [節](../../channels/using/about-push-notifications.md)。

此通道需要將行動應用程式與Adobe Experience Platform SDK整合。 這些應用程式必須先在Adobe Experience Platform Launch中啟動，才能在Adobe Campaign中啟用，才能在應用程式內傳送。

![](assets/launch_campaign.png)

若要開始在運用Experience Platform SDK的行動應用程式上傳送應用程式內訊息，您必須符合下列必要條件：

1. 在Adobe Campaign中，請確定您可以存取該 **[!UICONTROL In-App]** 渠道。 如果您無法存取這些渠道，請連絡您的帳戶團隊。

1. 若要將Adobe Campaign standard的行動使用案例與Experience Cloud SDK應用程式搭配運用，行動應用程式必須在Adobe Experience Platform Launch中建立，並在Adobe Campaign Standard中設定。 如需逐步指南，請參閱本頁 [面](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html)。

1. 設定好後，您現在可以準備應用程式內訊息。 For more on this, refer to this [page](../../channels/using/preparing-and-sending-an-in-app-message.md#preparing-your-in-app-message).

1. 然後您可以決定傳送應用 [程式內訊息](../../channels/using/customizing-an-in-app-message.md) ，或自 [訂本機通知訊息類型](../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type)。

1. 您的傳送現已準備好可以傳送。 若要進一步瞭解，請參閱本 [頁](../../channels/using/preparing-and-sending-an-in-app-message.md#sending-your-in-app-message)。

**相關內容：**

* [應用程式內報告](../../reporting/using/in-app-report.md)
* [推播和應用程式內常見問答集](https://helpx.adobe.com/campaign/kb/push_inapp_faq.html)
* [Adobe Campaign standard支援的行動使用案例](https://helpx.adobe.com/campaign/kb/configure-launch-rules-acs-use-cases.html)
