---
title: 關於應用程式內訊息傳送
description: 使用應用程式內訊息傳送在行動應用程式內顯示訊息或警報。
page-status-flag: never-activated
uuid: 6784cdfc-6db9-41dd-9fbb-2e756a5bcb5f
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: in-app-messaging
discoiquuid: a4168cfb-22bf-4ab3-b9d8-6e76e1bdc055
context-tags: delivery,triggers,back
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 關於應用程式內訊息傳送{#about-in-app-messaging}

應用程式內訊息傳送是傳訊通道，可讓您在使用者於行動應用程式內活動時顯示訊息。此訊息類型免費提供傳送至使用者電話通知中心的推播通知。如需推播通知頻道的詳細資訊，請參閱[本區段](../../channels/using/about-push-notifications.md)。

此通道需要將行動應用程式與　Adobe Experience Platform SDK　整合。這些應用程式必須先在　Adobe Experience Platform Launch　中啟動，才能在　Adobe Campaign　中進行應用程式內訊息傳送。

![](assets/launch_campaign.png)

若要利用 Experience Platform SDK，開始在行動應用程式上傳送應用程式內訊息，您需要遵循下列先決條件：

1. 在　Adobe Campaign　中，確定您可以存取 **[!UICONTROL In-App]** 通道。如果您無法存取這些通道，請聯絡您的帳戶團隊。

1. 若要將　Adobe Campaign Standard　的行動使用案例與　Experience Cloud SDK　應用程式搭配運用，行動應用程式必須在　Adobe Experience Platform Launch　中建立並在　Adobe Campaign Standard　中設定。如需逐步指南，請參閱此[頁面](https://helpx.adobe.com/tw/campaign/kb/configuring-app-sdk.html)。

1. 設定之後，您現在就能準備應用程式內訊息。如需詳細資訊，請參閱此[頁面](../../channels/using/preparing-and-sending-an-in-app-message.md#preparing-your-in-app-message)。

1. 之後，您可以決定傳送[應用程式內訊息](../../channels/using/customizing-an-in-app-message.md)，或[自訂本機通知訊息類型](../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type)。

1. 您的傳送現已準備就緒而可傳送。若要進一步瞭解，請參閱此[頁面](../../channels/using/preparing-and-sending-an-in-app-message.md#sending-your-in-app-message)。

**相關內容：**

* [應用程式內報告](../../reporting/using/in-app-report.md)
* [Adobe Campaign Standard　支援的行動使用案例](https://helpx.adobe.com/tw/campaign/kb/configure-launch-rules-acs-use-cases.html)
* [Campaign Standard　行動指南](https://helpx.adobe.com/tw/campaign/kb/acs-mobile.html)

## 應用程式內常見問答集 {#in-app-faq}

### 若要進一步瞭解Adobe Campaign Standard中的應用程式內通道，有哪些有用的資源建議？ {#resources-inapp}

查看以下資源：

* [教學影片](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/communication-channels/mobile/in-app/in-app-message-overview.html)
* [部落格文章](https://theblog.adobe.com/get-more-out-of-the-new-in-app-message-channel-from-adobe-campaign/)
* [社群頁面](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-standard/ct-p/adobe-campaign-standard-community)

### 促銷活動擴充功能APIs setLinkageField和resetLinkageField的用途為何？ {#extensions-apis}

由於應用程式內訊息是由SDK從Campaign提取，因此我們想要提供安全機制，以確保包含PII資料的應用程式內訊息不會落入惡意之手。 因此，我們有下列機制可確保將訊息安全地傳送至裝置：

* 如果客戶想要確保安全地傳送此特定資訊，請將行動設定檔欄位（appSubscriberRcp表格）欄位標示為「個人」和「敏感」。
* 標示為的欄位只能用於內建其他安全機制的「設定檔」範本（不在appSubscriber範本或廣播範本中）。
* 使用描述檔範本建立的訊息只有在使用者已登入應用程式時才可取得。
* 為方便此安全握手，行動應用程式開發人員應使用setLinkageField API傳遞其他驗證詳細資訊。 請注意，連結欄位是在擴充appSubscriberRcp表格時，被識別為「行動設定檔」和「CRM設定檔」之間的連結。
* 當使用者使用resetLinkageField登出應用程式時，他們應該會清除儲存在裝置上的應用程式內訊息，並重設Linkagefields。 如此可確保當不同的使用者登入應用程式時，他們看不到先前使用者的訊息。
* 請參閱 [Mobile SDK API](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference) ，以實作此安全機制用戶端。

### 我要如何在Campaign中啟用應用程式內報告？ {#enable-inapp-reporting}

您必須設定應用程式內追蹤回傳。 您可在這裡找到 [指示](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#InApptrackingpostback)。

若要實作本機通知追蹤，請參閱本 [頁](../../administration/using/local-tracking.md)。

### 哪些報表適用於應用程式內渠道？ {#report-inapp}

Adobe Campaign for In-App頻道提供現成可用的報表。 請參閱本 [檔案](../../reporting/using/in-app-report.md)。

請參閱 [此頁](../../reporting/using/indicator-calculation.md#in-app-delivery) ，瞭解如何計算每個應用程式內度量。

### 您是否支援應用程式內的多語言內容變體，類似推播？ {#multilingual-inapp}

現在沒有多語言範本可用於應用程式內訊息。

不過，如果目標是傳送非英文語言的「應用程式內」訊息，內容可直接貼在可用的文字方塊中。

![](assets/faq_inapp.png)

### 「促銷活動個人化」欄位是否可新增至自訂HTML? {#custom-html-inapp}

否，目前尚未支援此功能。

### 我已設定警報訊息，但未在裝置上顯示。 {#alert-message}

對於警報消息，至少需要一個關閉按鈕（主要或輔助應具有關閉操作）。 否則，可以保存消息，但不會收到該消息。

### 如果本機通知iOS自訂音效不播放；預設音效會改為播放嗎？ {#local-notification-sound}

若是iOS上的自訂音效，在建立本機通知（例如sound.caf）時，您必須提供副檔名為檔案名稱。 如果未提供此擴充功能，則會使用預設音效。

### 應用程式內訊息是否支援深層連結？ {#inapp-deeplinks}

是的，應用程式內訊息支援深層連結。 深層連結應包括：

* 說明傳送追蹤必須停用才能讓深層連結運作的語言。
* Appsflyer與Branch合作，可進行開發連結追蹤。 如需分支與Adobe Campaign Standard整合的詳細資訊，請參閱本 [頁](https://help.branch.io/using-branch/docs/adobe-campaign-standard-1)。

### 當使用者從推播通知啟動應用程式時，是否可觸發應用程式內訊息？ {#inapp-push-trigger}

是的，這些消息也稱為菊花鏈消息。 請遵循下列程式：

1. 建立應用程式內訊息。

1. 定義自定義事件，並將其選作此IAM的事件觸發器，例如&quot;從秋季預覽推播觸發器&quot;。

1. 在編寫推送消息時，請定義一個自定義變數，其值可以設定為用於觸發IAM的事件，例如，密鑰= &quot;inappkey&quot;，值= &quot;從秋季預覽推送觸發」。

1. 在行動應用程式程式碼中，實作事件觸發，如下所示：

   ![](assets/faq_inapp_2.png)
