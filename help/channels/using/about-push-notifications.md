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
source-git-commit: 597ece8d833a216f0540f801461b08fdc9865024
workflow-type: tm+mt
source-wordcount: '1239'
ht-degree: 40%

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

1. 確認您的使用者擁有Adobe Campaign Standard中的必要權限，以及Adobe Experience Platform中的標籤。

1. 在資料收集UI中，建立行動屬性。 如需詳細資訊，請參閱[設定行動裝置屬性](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/)。

1. 在資料收集UI中，安裝 **[!UICONTROL Adobe Campaign Standard]** 擴充功能。

1. 在Adobe Campaign Standard中，設定您在資料收集UI中建立的行動屬性。 如需詳細資訊，請參閱 [在Adobe Campaign中設定您的標籤應用程式](../../administration/using/configuring-a-mobile-application.md#set-up-campaign).

1. 將特定通道的設定新增至行動應用程式設定。如需詳細資訊，請參閱[ Adobe Campaign 中的通道特定應用程式設定](../../administration/using/configuring-a-mobile-application.md#channel-specific-config)。

1. 若要支援行動使用案例實作，請參閱以下主題的擴充功能、標籤規則和SDK實作的詳細指示： [Adobe Campaign Standard支援的行動使用案例：使用Adobe Experience Platform SDK](../../administration/using/configuring-rules-launch.md).

## 推播通知常見問題集 {#push-faq}

### 若要深入了解推播管道，有哪些實用的資源建議？ {#resource-push}

查看下列資源：

* [影片教學課程](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/communication-channels/mobile/push/creating-a-push-notification.html)
* [產品檔案](../../channels/using/about-push-notifications.md)
* 使用AEP SDK進行配置 [檔案](../../administration/using/configuring-a-mobile-application.md)
* [社群頁面](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-standard/ct-p/adobe-campaign-standard-community)

### 要在Campaign中取得推播代號，我必須做什麼？ {#push-token-acquisition}

確認布建團隊已完成在Adobe Campaign Standard中布建推播通道。 從SDK實作setPushIdentifier API。 如需關於此項目的詳細資訊，請參閱此[頁面](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/#set-up-push-messaging)。

### 在Campaign中擁有推播代號和ECID後，我還需要傳送推播通知什麼？ {#sending-push}

客戶需要以.pem格式提供有效的推播憑證，才能傳送推播通知。 您不需要此證書的密碼。

### 如果我有.p12憑證而非.pem憑證，該怎麼辦？ {#certificates}

您可以在終端機中執行以下命令，將.p12憑證轉換為.pem憑證。 轉換指示也提供數個線上資源。

```
openssl pkcs12 -in pushcert.p12 -out pushcert.pem -nodes -clcerts
```

### 如何知道憑證上傳是否成功？ {#certificate-upload}

您會看到下列訊息。

![](assets/faq_2.png)

### 我可以同時上傳iOS應用程式的生產和沙箱憑證嗎（Android適用的為不適用）? {#prod-sandbox-certificate}

否，應用程式可在沙箱或生產模式中運作，且一旦設定後，就無法變更為其他應用程式（即沙箱至生產應用程式）。 建議您先以沙箱模式測試應用程式，然後轉變為生產模式。

若要變更為生產模式，您必須建立其他應用程式。 也請務必不勾選沙箱核取方塊和上傳生產憑證。

### 我可以同時上傳iOS和Android憑證嗎？ {#ios-android-credentials}

是的，Campaign可同時支援兩個平台，並允許您上傳兩個平台的憑證。

### 我已成功上傳推送憑證，但未傳送推送訊息。 {#push-certificates-upload}

請測試您的推播憑證，以確定其有效 [此處](https://pushtry.com/).

### 我可以從pushtry.com成功傳送推播通知，但不能透過Campaign。 {#push-not-sending}

請確定您遵循提供的推送裝載指示 [此處](../../administration/using/push-payload.md).

請注意，對於Android,Campaign僅支援資料裝載，不支援通知裝載

### 我已在Adobe Campaign Standard的「管理」區段中設定應用程式，但「傳送」屬性中無法使用行動應用程式。 {#mobile-app-unavailable}

應用程式必須先上傳有效的推送憑證，才能在傳送屬性中使用。

### 我已嘗試此頁面上的所有指示，但無法從Campaign傳送推播。 {#push-troubleshoot}

請開張客戶服務票證。

### 推播通知是從Campaign傳送，但媒體檔案未顯示。{#media-file-unavailable}

行動應用程式開發人員需要處理應用程式中媒體檔案的支援。 有時，網路頻寬也可能會阻止媒體檔案的呈現。 請參閱 [頁面](../../administration/using/image-push-notification.md) 其他指針。

### 如何在Campaign中啟用推送報表？ {#push-reporting-enable}

請遵循以下步驟：

* 設定推播追蹤回傳。 可找到指示 [此處](../../administration/using/configuring-a-mobile-application.md).
* 從行動核心實作trackAction API。 請參閱 [頁面](https://developer.adobe.com/client-sdks/documentation/mobile-core/api-reference/) 以取得更多資訊。

如需更多詳細指示，請參閱 [頁面](../../administration/using/push-tracking.md).

### 哪些報表可用於推播管道？ {#push-report-available}

Adobe Campaign for Push管道中提供現成報表。 請參閱 [檔案](../../reporting/using/push-notification-report.md).

看這個 [頁面](../../reporting/using/indicator-calculation.md#push-notification-delivery) 了解每個推送量度的計算方式。

### 推送訊息和應用程式內訊息是否支援深層連結？ {#deeplink-push}

是，推送訊息支援深層連結。 深層連結應包括：

* 說明傳送追蹤必須停用才能讓深層連結運作的語言。
* 以Branch作為合作夥伴執行深層連結追蹤的Appsflyer。 如需分支和Adobe Campaign Standard整合的詳細資訊，請參閱 [頁面](https://help.branch.io/using-branch/docs/adobe-campaign-standard-1).
