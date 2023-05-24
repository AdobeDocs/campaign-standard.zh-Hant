---
title: 應用程式內常見問題集
description: 有關In-App消息傳遞的常見問題
audience: channels
content-type: reference
topic-tags: in-app-messaging
context-tags: delivery,triggers,back
feature: In App
role: User
exl-id: 0101773d-b109-49a3-89d4-b4bb226d9ebd
source-git-commit: 597ece8d833a216f0540f801461b08fdc9865024
workflow-type: tm+mt
source-wordcount: '668'
ht-degree: 1%

---

# 應用程式內常見問題集 {#in-app-faq}

## 有哪些有用的資源建議可詳細瞭解Adobe Campaign Standard的In-App渠道？ {#resources-inapp}

簽出以下資源：

* [影片教學課程](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/communication-channels/mobile/in-app/in-app-message-overview.html)
* [部落格帖子](https://theblog.adobe.com/get-more-out-of-the-new-in-app-message-channel-from-adobe-campaign/)
* [社區頁](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-standard/ct-p/adobe-campaign-standard-community)

## 市場活動擴展APIs setLinkageField和resetLinkageField的目的是什麼？ {#extensions-apis}

由於In-App消息是由SDK從市場活動中提取的，因此我們希望提供一種安全機制，以確保包含PII資料的In-App消息不會落入惡意的手中。 因此，我們具備以下機制來確保向設備安全傳遞消息：

* 如果客戶希望確保安全傳送此特定資訊，則將移動配置檔案欄位（appSubscriberRcp表）標籤為「個人」和「敏感」。
* 標籤為此類的欄位只能用於內置其他安全機制的配置檔案模板（不在appSubscriber模板或廣播模板中）。
* 僅當用戶已登錄應用時，才能提供使用配置檔案模板生成的消息。
* 為了便於進行此安全握手，移動應用程式開發人員應使用setLinkageField API傳遞其他身份驗證詳細資訊。 請注意，在擴展appSubscriberRcp表時，連結欄位被標識為移動配置檔案和CRM配置檔案之間的連結。
* 當用戶使用resetLinkageField從應用註銷時，他們應刷新儲存在設備上的In-App消息並resetLinkagefield。 這可確保如果其他用戶登錄到應用程式，則他們不會看到針對前一個用戶的消息。
* 請參閱 [移動SDK API](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/api-reference/) 實現此安全機制客戶端。

## 我必須做什麼才能在活動中啟用應用內報告？ {#enable-inapp-reporting}

您需要配置In-App跟蹤後退。 可以找到說明 [這裡](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback)。

要實施本地通知跟蹤，請參閱 [頁](../../administration/using/local-tracking.md)。

## 哪些報告可用於In-App渠道？ {#report-inapp}

在Adobe Campaign,In-App頻道提供現成報告。 請參閱此 [文檔](../../reporting/using/in-app-report.md)。

查看 [頁](../../reporting/using/indicator-calculation.md#in-app-delivery) 瞭解如何計算每個In-App度量。

## 是否支援與推送類似的In-App的多語言內容變體？ {#multilingual-inapp}

現在沒有可用於應用程式內消息傳遞的多語言模板。

但是，如果目標是以英語以外的語言發送In-App消息，則內容可以直接貼上到可用的文本框中。

![](assets/faq_inapp.png)

## 是否可以將「市場活動個性化」欄位添加到「自定義HTML」？ {#custom-html-inapp}

不，尚不支援此操作。

## 我已配置了警報消息，但該消息未顯示在設備上。 {#alert-message}

對於警報消息，至少需要一個消除按鈕（主或次應具有消除操作）。 否則，可能會保存消息，但不會接收該消息。

## 如果本地通知不播放iOS自定義聲音；預設聲音會改為播放嗎？ {#local-notification-sound}

對於iOS的自定義聲音，在建立本地通知（例如sound.caf）時，需要提供副檔名為的檔案名。 如果未提供此擴展，則使用預設聲音。

## In-App消息中是否支援刪除？ {#inapp-deeplinks}

是，In-App消息中支援刪除。 相關連結應包括：

* 聲明需要禁用交付跟蹤以便讓開發人員工作的語言。
* Appsflyer與Branch一起作為合作夥伴，可以執行部署跟蹤。 有關分支和Adobe Campaign Standard整合的詳細資訊，請參閱 [頁](https://help.branch.io/using-branch/docs/adobe-campaign-standard-1)。

## 當用戶從推送通知啟動應用時，是否可以觸發In-App消息？ {#inapp-push-trigger}

是，這些消息也稱為菊花鏈消息。 按照以下過程操作：

1. 建立應用內消息。

1. 定義自定義事件並將其選作此IAM的事件觸發器，例如&quot;從秋季預覽推送觸發&quot;。

1. 在創作Push消息時，定義一個自定義變數，其值可設定為用於觸發IAM的事件，例如Key = &quot;inappkey&quot;,value = &quot;Trigger from fall preview Push&quot;。

1. 在移動應用代碼中，按如下方式實現事件觸發器：

   ![](assets/faq_inapp_2.png)
