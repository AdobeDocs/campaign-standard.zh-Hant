---
title: 設定行動應用程式
seo-title: 設定行動應用程式
description: 設定行動應用程式
seo-description: 瞭解如何設定Adobe Campaign，使用SDK V或Experience Platform SDK傳送推播通知或應用程式內訊息。
page-status-flag: 從未啓動
uuid: 63e1476a-7785-4f48-ba9 e-97f1 a00007 e42
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 管理
content-type: reference
topic-tags: 設定頻道
discoiquuid: 2a14500f-5ede-4131-8b1a-b7 fd65 b7 e3 aa
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 3b7da7df5092476be4c6acc21b2ad2472a80da83

---


# 設定行動應用程式{#configuring-a-mobile-application}

首先需要在Adobe Mobile Services中設定的行動應用程式中接收推播通知或應用程式內訊息，視您要使用的頻道而定。

* 若要傳送應用程式內訊息和推播通知，您必須利用Adobe Experience Platform SDK在Adobe Campaign中設定行動應用程式。請參閱 [使用Adobe Experience Platform SDK](#using-adobe-experience-platform-sdk)。

* 若要只傳送推播通知，您可以使用SDK V設定Adobe Campaign和Adobe Mobile Service之間的整合。請參閱 [使用SDK V4](#using-sdk-v4)。

借由運用Experience Cloud Mobile SDK V或Experience Platform SDK在Adobe Campaign中設定行動應用程式後，就必須由管理員在 [!UICONTROL Administration] &gt; [!UICONTROL Channels] &gt; [!UICONTROL Mobile app] 功能表中設定它們。

>[!CAUTION]
>
>推播通知和應用程式內建置必須由專家使用者執行。如果需要協助，請聯絡您的Adobe銷售代表或專業服務合作夥伴。

在設定行動應用程式後，您就可以擷取其收集的PII資料，以便從資料庫建立或更新描述檔。如需更多資訊，請參閱本節： [根據行動應用程式資料建立和更新描述檔資訊](../../channels/using/updating-profile-with-mobile-app-data.md)。

## 使用Adobe Experience Platform SDK {#using-adobe-experience-platform-sdk}

>[!Nte te]
>
>若要深入瞭解Adobe Campaign Standard支援的不同行動使用案例，請參閱此 [頁面](https://helpx.adobe.com/campaign/kb/configure-launch-rules-acs-use-cases.html)。

若要使用Experience Platform SDK應用程式傳送推播通知和應用程式內訊息，必須在Adobe Experience Platform Experience Platform Experience Platform Launch並在Adobe Campaign中設定行動應用程式。如需使用Experience Platform SDK設定行動應用程式的詳細步驟，請參閱此 [頁面](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html)。

請依照下列步驟開始設定：

1. 確定您可以存取 **[!UICONTROL Mobile]** 渠道：Adobe Campaign中的推播通知和應用程式內訊息。如果沒有，請聯絡您的帳戶團隊。

   ![](assets/launch_1.png)

1. 建立Mobile類型的屬性，在Experience Platform Launch中建立行動應用程式。如需詳細資訊，請參閱 [Experience Platform Launch](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#create-a-new-mobile-property) 文件。
1. 在Experience **[!UICONTROL Adobe Campaign Standard]** Platform Launch中安裝行動應用程式的擴充功能：

   如需擴充功能的詳細資訊，請參閱 [Experience Platform Launch](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard) 文件。

1. 在Adobe Launch中設定應用程式的規則，請參閱 [Launch中的設定應用程式](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Step1Createdataelements)
1. 在Adobe Campaign Standard中設定您的Adobe Launch應用程式，請參閱 [在Adobe Campaign中設定您的Adobe Launch應用程式](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#SettingupyourAdobeLaunchapplicationinAdobeCampaign)。
1. 將頻道特定設定新增至您的行動應用程式設定，請參閱 [Adobe Campaign中的頻道特定應用程式設定](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#ChannelspecificapplicationconfigurationinAdobeCampaign)。

   ![](assets/launch_2.png)

## 使用SDK V4 {#using-sdk-v4}

SDK V和Adobe Experience Platform SDK支援推播通知，而非應用程式中的SDK。如需使用推播通知與行動應用程式的詳細步驟，請參閱此 [頁面](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html)。

接收推播通知的行動應用程式必須由管理員在Adobe Campaign介面中設定。透過設定Adobe Campaign和Adobe Mobile Services，您將能夠使用您的行動應用程式資料來進行促銷活動。

若要傳送推播通知，您必須：

1. 確定您可以在Adobe Campaign中存取 **[!UICONTROL Mobile app]** 渠道。
1. 設定您的行動應用程式：

   * [Adobe Campaign](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html#SettingupamobileapplicationinAdobeCampaign)。
   * [Adobe Mobile Services](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html#ConfiguringamobileapplicationinAdobeMobileServices)。

1. 執行行動應用程式的特定設定：

   * 將從Adobe Mobile Services介面下載的組態檔封裝為行動應用程式。
   * 將Experience Cloud Mobile SDK整合至您的行動應用程式。

1. 定義您要從應用程式訂閱者收集的資料。在Adobe Campaign資料庫中擁有描述檔的行動應用程式訂閱者，會根據您定義的標準進行協調。

   如需更多資訊，請參閱本 [頁](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html#Collectingsubscribersdatafromamobileapplication)。

1. 請在裝置上啓動行動應用程式並登入，確定已順利完成設定。請確定您選擇接收通知。
1. 然後在Adobe Campaign的進階功能表中，選取 **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Mobile app]**。
1. 從清單中選取行動應用程式，以顯示其屬性。您的訂閱資訊會顯示在訂閱者清單下方。

   ![](assets/push_notif_mobile_app.png)

1. 若要檢查描述檔已訂閱的行動應用程式，請在 **[!UICONTROL Profiles & Audiences > Profiles]** 功能表中選取描述檔，然後按一下右邊的 **[!UICONTROL Edit profile properties]** 按鈕。行動應用程式會列在 **[!UICONTROL Mobile App Subscriptions]** 索引標籤中。

   ![](assets/push_notif_subscriptions.png)