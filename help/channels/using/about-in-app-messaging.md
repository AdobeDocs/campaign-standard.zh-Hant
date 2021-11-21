---
title: 關於應用程式內訊息傳送
description: 使用應用程式內訊息傳送在行動應用程式內顯示訊息或警報。
audience: channels
content-type: reference
topic-tags: in-app-messaging
context-tags: delivery,triggers,back
feature: In App
role: User
exl-id: 986646b1-42d5-4169-ac38-d8e612a9a6d3
source-git-commit: 462ebaf8e8f1f056aa92118226ef77aea37b972b
workflow-type: tm+mt
source-wordcount: '443'
ht-degree: 100%

---

# 關於應用程式內訊息傳送{#about-in-app-messaging}

應用程式內訊息傳送是傳訊通道，可讓您在使用者於行動應用程式內活動時顯示訊息。此訊息類型免費提供傳送至使用者電話通知中心的推播通知。如需推播通知頻道的詳細資訊，請參閱[本區段](../../channels/using/about-push-notifications.md)。

此通道需要將行動應用程式與　Adobe Experience Platform SDK　整合。這些應用程式必須先在　Adobe Experience Platform Launch　中啟動，才能在　Adobe Campaign　中進行應用程式內訊息傳送。

![](assets/launch_campaign.png)

若要利用 Experience Platform SDK，開始在行動應用程式上傳送應用程式內訊息，您需要遵循下列先決條件：

1. 在　Adobe Campaign　中，確定您可以存取 **[!UICONTROL In-App]** 通道。如果您無法存取這些通道，請聯絡您的帳戶團隊。

1. 若要將　Adobe Campaign Standard　的行動使用案例與　Experience Cloud SDK　應用程式搭配運用，行動應用程式必須在　Adobe Experience Platform Launch　中建立並在　Adobe Campaign Standard　中設定。如需逐步指南，請參閱此[頁面](../../administration/using/configuring-a-mobile-application.md)。

1. 設定之後，您現在就能準備應用程式內訊息。如需詳細資訊，請參閱此[頁面](../../channels/using/preparing-and-sending-an-in-app-message.md#preparing-your-in-app-message)。

1. 之後，您可以決定傳送[應用程式內訊息](../../channels/using/customizing-an-in-app-message.md)，或[自訂本機通知訊息類型](../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type)。

1. 您的傳送現已準備就緒而可傳送。若要進一步瞭解，請參閱此[頁面](../../channels/using/preparing-and-sending-an-in-app-message.md#sending-your-in-app-message)。

**相關內容：**

* [應用程式內報告](../../reporting/using/in-app-report.md)
* [Adobe Campaign Standard 支援的行動使用案例](../../administration/using/configuring-rules-launch.md)
* [Campaign Standard　行動指南](../../channels/using/get-started-communication-channels.md)

## 使用個人和敏感資料處理行動設定檔欄位 {#handling-mobile-profile-fields-with-personal-and-sensitive-data}

在 Adobe Campaign 中，由行動裝置傳送的行動設定檔屬性資料會儲存在 **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** 資源中，您可藉此定義要從應用程式訂閱者收集的資料。

需要擴充此資源，才能收集您要從行動裝置傳送至 Adobe Campaign 的資料。要執行此操作，請參閱本[頁面](../../developing/using/extending-the-subscriptions-to-an-application-resource.md)以取得詳細步驟。

為了提供更安全的應用程式內訊息個人化功能，您需要據此設定這項資源的行動設定檔欄位。在您的 **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** 中，建立新行動設定檔欄位時，請和取 **[!UICONTROL Personal and Sensitive]** 在應用程式內訊息個人化期間使用這些設定檔。

>[!NOTE]
>
>如果此表格上已有具有自訂資源擴充功能的現有實作，我們建議您在將欄位用於個人化應用程式內訊息之前，先適當地標籤欄位。

![](assets/in_app_personal_data_2.png)

在設定並發佈 **[!UICONTROL Subscriptions to an application]** 自訂資源後，您就可以開始使用 **[!UICONTROL Target users based on their Mobile profile (inApp)]** 範本準備應用程式內傳送內容。個人化 **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** 資源將僅提供非個人和非敏感欄位。

若需使用 **Personal and Sensitive** 欄位來達到個人化目的，建議您使用 **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]** 範本，此範本提供額外的安全機制，能確保使用者的 PII 資料安全無虞。
