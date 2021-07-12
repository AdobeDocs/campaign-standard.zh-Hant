---
solution: Campaign Standard
product: campaign
title: 應用程式內常見問題集
description: 應用程式內傳訊的常見問題
audience: channels
content-type: reference
topic-tags: in-app-messaging
context-tags: delivery,triggers,back
feature: 應用程式內
role: User
exl-id: 986646b1-42d5-4169-ac38-d8e612a9a6d3
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '676'
ht-degree: 2%

---


# 應用程式內常見問題集 {#in-app-faq}

## 若要進一步了解Adobe Campaign Standard的應用程式內管道，有哪些實用資源建議？ {#resources-inapp}

查看下列資源：

* [影片教學課程](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/communication-channels/mobile/in-app/in-app-message-overview.html)
* [部落格貼文](https://theblog.adobe.com/get-more-out-of-the-new-in-app-message-channel-from-adobe-campaign/)
* [社群頁面](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-standard/ct-p/adobe-campaign-standard-community)

## 促銷活動擴充功能API setLinkageField和resetLinkageField有何用途？ {#extensions-apis}

由於應用程式內訊息是由Campaign的SDK提取，因此我們想提供安全的機制，以確保包含PII資料的應用程式內訊息不會落入惡意人士之手。 因此，我們具備下列機制，可確保將訊息安全傳送至裝置：

* 如果客戶希望確保安全地傳送此特定資訊，請將行動設定檔欄位（appSubscriberRcp表格）欄位標示為「個人與敏感」。
* 標示為的欄位只能用於內建其他安全機制的「設定檔」範本（不能用於appSubscriber範本或廣播範本）。
* 使用設定檔範本建立的訊息，只有在使用者已登入應用程式時，才能提供。
* 為了便於進行此安全交握，行動應用程式開發人員應使用setLinkageField API傳遞其他驗證詳細資訊。 請注意，連結欄位是在擴充appSubscriberRcp表格時，識別為行動設定檔與CRM設定檔之間連結的欄位。
* 當使用者使用resetLinkageField登出應用程式時，應排清儲存在裝置上的應用程式內訊息，並重設Linkagefields。 這可確保當其他使用者登入應用程式時，不會看見針對先前使用者的訊息。
* 請參閱[行動SDK API](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference)以實作此安全機制用戶端。

## 如何在Campaign中啟用應用程式內報告？ {#enable-inapp-reporting}

您必須設定應用程式內追蹤回傳。 您可以在[此處](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#InApptrackingpostback)找到說明。

若要實作本機通知追蹤，請參閱此[page](../../administration/using/local-tracking.md)。

## 應用程式內管道可使用哪些報表？ {#report-inapp}

Adobe Campaign提供應用程式內管道的現成報表。 請參閱此[檔案](../../reporting/using/in-app-report.md)。

請參閱此[page](../../reporting/using/indicator-calculation.md#in-app-delivery)以了解每個應用程式內量度的計算方式。

## 應用程式內支援類似「推送」的多語言內容變體嗎？ {#multilingual-inapp}

現在，應用程式內傳訊功能沒有多語言範本可用。

不過，如果目標是傳送英文以外的語言「應用程式內」訊息，內容可直接貼在可用的文字方塊中。

![](assets/faq_inapp.png)

## 可以將Campaign個人化欄位新增至自訂HTML嗎？ {#custom-html-inapp}

否，目前尚不支援此功能。

## 我已配置了警報消息，但該消息不會顯示在設備上。 {#alert-message}

對於警報訊息，至少需要一個關閉按鈕（主要或次要應具有關閉動作）。 否則，可以保存該消息，但不會收到該消息。

## 如果本機通知iOS自訂音效未播放；預設音效會改為播放嗎？ {#local-notification-sound}

若是iOS上的自訂音效，建立本機通知時（例如sound.caf），您必須提供副檔名為的檔案名稱。 如果未提供此擴充功能，則使用預設音效。

## 應用程式內訊息是否支援深層連結？ {#inapp-deeplinks}

是的，應用程式內訊息支援深層連結。 深層連結應包括：

* 說明必須停用傳送追蹤才能讓深層連結運作的語言。
* 以Branch作為合作夥伴執行深層連結追蹤的Appsflyer。 如需Branch和Adobe Campaign Standard整合的詳細資訊，請參閱此[page](https://help.branch.io/using-branch/docs/adobe-campaign-standard-1)。

## 使用者從推播通知啟動應用程式時，是否可觸發應用程式內訊息？ {#inapp-push-trigger}

是的，這些消息也稱為菊花鏈消息。 請依照下列程式操作：

1. 建立應用程式內訊息。

1. 定義自定義事件，並將其選作此IAM的事件觸發器，例如「秋季預覽推播觸發」。

1. 在編寫推送消息時，請定義一個自定義變數，其值可以設定為用於觸發IAM的事件，例如，鍵= &quot;inappkey&quot;，值= &quot;從秋季預覽推送觸發&quot;。

1. 在行動應用程式程式碼中，實施事件觸發器，如下所示：

   ![](assets/faq_inapp_2.png)
