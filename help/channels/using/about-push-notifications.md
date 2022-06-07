---
title: 關於推播通知
description: 探索　Adobe Campaign　推播通知通道的主要特性。
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
feature: Push
role: User
level: Intermediate
exl-id: e61daed6-a0ec-49d8-b1ad-77590fafb496
source-git-commit: 7767b39a48502f97e2b3af9d21a3f49b9283ab2e
workflow-type: tm+mt
source-wordcount: '1238'
ht-degree: 41%

---

# 關於推送通知{#about-push-notifications}

>[!CAUTION]
>
>推播通知實作必須由專家使用者執行。如果您需要協助，請聯絡您的 Adobe 客戶主管或專業服務合作夥伴。推播通知是選用功能。請檢查您的授權合約，並聯絡您的帳戶管理員以啟用它。

Adobe Campaign 可讓您將個人化和分段的推播通知傳送至 iOS 和 Android 行動裝置。

這些訊息是您利用 Experience Platform SDK 在 Adobe Campaign 中設定之行動應用程式接收而來的。如需詳細資訊，請參閱[使用 Adobe Experience Platform SDK 設定行動應用程式](../../administration/using/configuring-a-mobile-application.md)。

在 Adobe Campaign 中，由行動裝置傳送的行動設定檔屬性資料會儲存在 **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** 資源中，您可藉此定義要從應用程式訂閱者收集的資料。

需要擴充此資源，才能收集您要從行動裝置傳送至 Adobe Campaign 的資料。要執行此操作，請參閱本[頁面](../../developing/using/extending-the-subscriptions-to-an-application-resource.md)以取得詳細步驟。

Adobe Campaign 提供兩種類型的推播通知：

* **[!UICONTROL Alert/Message/Badge]** 類型通知可讓您傳送包含您可在&#x200B;**[!UICONTROL Advanced options]** 區段中定義之其他內容（音效、徽章、Deeplink 等）的標準文字型訊息。

   此通知類型可讓您新增標題和訊息，您可在其中使用個人化欄位。若要個人化您的訊息，請務必選取 **[!UICONTROL Send push on profiles]** 範本。

* **[!UICONTROL Silent push]** 類型通知可用於無訊息地通知應用程式，而不會傳送任何訊息或內容給一般使用者。此類訊息的典型使用案例是讓應用程式知道伺服器上有可供下載的內容。

可以進行一些特定設定來定義通知行為。如需詳細資訊，請參閱[本區段](../../channels/using/customizing-a-push-notification.md)。

>[!NOTE]
>
>關於隱私權的法律會依國家/地區而異。有些國家/地區會要求您通知使用者行動應用程式收集的資料類型。請檢查您所在國家/地區的行動應用程式相關法律。請確定傳送至行動應用程式的推播通知符合 Apple（Apple 推播通知服務）和 Google（Google 雲端訊息或 Firebase 雲端訊息）所指定的必要條件。

**相關內容：**

* [準備和傳送推送通知](../../channels/using/preparing-and-sending-a-push-notification.md)
* [建立多語言推送通知](../../channels/using/creating-a-multilingual-push-notification.md)
* [推播通知報告](../../reporting/using/push-notification-report.md)
* [Campaign Standard　行動指南](../../channels/using/get-started-communication-channels.md)

## 必要條件 {#prerequisites}

>[!NOTE]
>若要利用來自 Campaign 的推播通知功能，您需要以 .pem 格式提供有效的推播憑證，而且不含密碼。

>
>如果您有有效的 p12 憑證，則可使用線上資源，輕鬆地將之轉換為 .pem 檔案。

傳送推播通知前，您應該：

1. 在　Adobe Campaign　中，確定您可以存取 **[!UICONTROL Push notification]** 通道。如果您無法存取這些通道，請聯絡您的帳戶團隊。

1. 驗證您的用戶是否在Adobe Campaign Standard和Adobe Experience Platform擁有必要的權限。

1. 在資料收集UI中，建立移動屬性。 如需詳細資訊，請參閱[設定行動裝置屬性](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property)。

1. 在資料收集UI中，安裝 **[!UICONTROL Adobe Campaign Standard]** 擴展。

1. 在Adobe Campaign Standard，配置在資料收集UI中建立的移動屬性。 有關詳細資訊，請參見 [在Adobe Campaign設定標籤應用程式](../../administration/using/configuring-a-mobile-application.md#set-up-campaign)。

1. 將特定通道的設定新增至行動應用程式設定。如需詳細資訊，請參閱[ Adobe Campaign 中的通道特定應用程式設定](../../administration/using/configuring-a-mobile-application.md#channel-specific-config)。

1. 要支援移動用例實現，請參閱中有關擴展、標籤規則和SDK實現的詳細說明 [在Adobe Campaign Standard使用Adobe Experience PlatformSDK支援的移動使用案例](../../administration/using/configuring-rules-launch.md)。

## 推送通知常見問題 {#push-faq}

### 哪些有用的資源建議可以詳細瞭解推送渠道？ {#resource-push}

簽出以下資源：

* [影片教學課程](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/communication-channels/mobile/push/creating-a-push-notification.html)
* [產品文檔](../../channels/using/about-push-notifications.md)
* 使用AEP SDK配置 [文檔](../../administration/using/configuring-a-mobile-application.md)
* [社區頁](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-standard/ct-p/adobe-campaign-standard-community)

### 我必須做什麼才能在活動中獲得推令牌？ {#push-token-acquisition}

確保預配團隊已完成Adobe Campaign Standard的Push通道預配。 從SDK實現setPushIdentifier API。 如需關於此項目的詳細資訊，請參閱此[頁面](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard#set-up-push-messaging)。

### 一旦我在市場活動中擁有了推送令牌和ECID，我還需要發送推送通知嗎？ {#sending-push}

客戶需要以.pem格式提供有效的推送證書才能發送推送通知。 您不需要此證書的密碼。

### 如果我有.p12證書而不是.pem證書會怎樣？ {#certificates}

通過在終端中運行以下命令，可以將.p12證書轉換為.pem證書。 還有幾種線上資源可用於轉換說明。

```
openssl pkcs12 -in pushcert.p12 -out pushcert.pem -nodes -clcerts
```

### 如何確定證書上載是否成功？ {#certificate-upload}

您將看到以下消息。

![](assets/faq_2.png)

### 我是否可以同時為iOS應用程式上載生產證書和沙盒證書（Android為N/A）? {#prod-sandbox-certificate}

否，應用程式將在沙盒或生產模式中工作，一旦設定，就不能更改到其他應用程式（即沙盒到生產應用程式）。 我們建議您先在沙盒模式下test應用，然後過渡到生產模式。

若要更改為生產模式，您必須建立其他應用。 另請確保不選中沙盒複選框並上載生產證書。

### 我是否可以同時上傳iOS和Android憑據？ {#ios-android-credentials}

是的，市場活動同時支援兩個平台，允許您上載兩個平台的憑據。

### 我已成功上載推送證書，但未發送推送消息。 {#push-certificates-upload}

請通過測試您的推送證書來確保其有效 [這裡](https://pushtry.com/)。

### 我可以從pushtry.com成功發送推送通知，但不能通過活動。 {#push-not-sending}

請確保您遵循提供的推送負載說明 [這裡](../../administration/using/push-payload.md)。

請注意，對於Android，市場活動僅支援資料負載而不支援通知負載

### 我在Adobe Campaign Standard的「管理」部分配置了應用，但「傳遞」屬性中不提供移動應用。 {#mobile-app-unavailable}

應用必須上載有效的推送證書，才能在傳遞屬性中使其可用。

### 我已嘗試了此頁上的所有說明，但無法從市場活動發送推送。 {#push-troubleshoot}

請開啟客戶服務票。

### 推送通知正在從市場活動中傳遞，但媒體檔案未顯示。{#media-file-unavailable}

Mobile App開發人員需要處理對應用中媒體檔案的支援。 有時，網路頻寬也可能阻止媒體檔案呈現。 請參閱此 [頁](../../administration/using/image-push-notification.md) 用於其他指針。

### 我必須做什麼才能在活動中啟用推送報告？ {#push-reporting-enable}

請遵循以下步驟：

* 配置推回跟蹤後退。 可以找到說明 [這裡](../../administration/using/configuring-a-mobile-application.md)。
* 從移動核心實現trackAction API。 請參閱此 [頁](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference) 的子菜單。

有關更詳細的說明，請參閱 [頁](../../administration/using/push-tracking.md)。

### 哪些報告可用於推送渠道？ {#push-report-available}

在Adobe Campaign，可以為Push頻道提供現成報告。 請參閱此 [文檔](../../reporting/using/push-notification-report.md)。

查看 [頁](../../reporting/using/indicator-calculation.md#push-notification-delivery) 瞭解如何計算每個推送度量。

### 推送和應用內消息中是否支援刪除？ {#deeplink-push}

是，推送消息中支援刪除。 相關連結應包括：

* 聲明需要禁用交付跟蹤以使交付連結工作的語言。
* Appsflyer與Branch一起作為合作夥伴，可以執行部署跟蹤。 有關分支和Adobe Campaign Standard整合的詳細資訊，請參閱 [頁](https://help.branch.io/using-branch/docs/adobe-campaign-standard-1)。
