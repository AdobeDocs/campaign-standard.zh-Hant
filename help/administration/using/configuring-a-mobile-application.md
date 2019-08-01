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
source-git-commit: 44be801f7bcbb3a495744ecd5fa08250585ed8cb

---


# Configuring a mobile application{#configuring-a-mobile-application}

首先需要在Adobe Mobile Services中設定的行動應用程式中接收推播通知或應用程式內訊息，視您要使用的頻道而定。

* 若要傳送應用程式內訊息和推播通知，您必須利用Adobe Experience Platform SDK在Adobe Campaign中設定行動應用程式。See [Using Adobe Experience Platform SDK](#using-adobe-experience-platform-sdk).

* 若要只傳送推播通知，您可以使用SDK V設定Adobe Campaign和Adobe Mobile Service之間的整合。See [Using SDK V4](#using-sdk-v4).

After your mobile applications are set up in Adobe Campaign by leveraging the Experience Cloud Mobile SDK V4 or Experience Platform SDK, they need to be configured by an administrator under the [!UICONTROL Administration] &gt; [!UICONTROL Channels] &gt; [!UICONTROL Mobile app] menu.

>[!CAUTION]
>
>推播通知和應用程式內建置必須由專家使用者執行。如果需要協助，請聯絡您的Adobe銷售代表或專業服務合作夥伴。

## Using Adobe Experience Platform SDK {#using-adobe-experience-platform-sdk}

>[!Nte te]
>
>To learn more on the different mobile use cases supported in Adobe Campaign Standard by using the Adobe Experience Platform SDKs, refer to this [page](https://helpx.adobe.com/campaign/kb/configure-launch-rules-acs-use-cases.html).

若要使用Experience Platform SDK應用程式傳送推播通知和應用程式內訊息，必須在Adobe Experience Platform Experience Platform Experience Platform Launch並在Adobe Campaign中設定行動應用程式。For the detailed steps to configure your mobile application using Experience Platform SDK, refer to this [page](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html).

請依照下列步驟開始設定：

1. Make sure you can access the **[!UICONTROL Mobile]** channels: Push notification and In-App message in Adobe Campaign. 如果沒有，請聯絡您的帳戶團隊。

   ![](assets/launch_1.png)

1. 建立Mobile類型的屬性，在Experience Platform Launch中建立行動應用程式。For more info, refer to the [Experience Platform Launch](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#create-a-new-mobile-property) documentation.
1. Install the **[!UICONTROL Adobe Campaign Standard]** extension for your mobile application in Experience Platform Launch:

   For more information on extensions, refer to the [Experience Platform Launch](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard) documentation.

1. Configure rules for your application in Adobe Launch, see [Configuring your application in Launch](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Step1Createdataelements)
1. Configure your Adobe Launch application in Adobe Campaign Standard, see [Setting up your Adobe Launch application in Adobe Campaign](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#SettingupyourAdobeLaunchapplicationinAdobeCampaign).
1. Add channel specific configuration to your Mobile Application set-up, see [Channel-specific application configuration in Adobe Campaign](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#ChannelspecificapplicationconfigurationinAdobeCampaign).

   ![](assets/launch_2.png)

## Using SDK V4 {#using-sdk-v4}

SDK V和Adobe Experience Platform SDK支援推播通知，而非應用程式中的SDK。For the detailed steps to use push notifications with your mobile app, refer to this [page](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html).

接收推播通知的行動應用程式必須由管理員在Adobe Campaign介面中設定。透過設定Adobe Campaign和Adobe Mobile Services，您將能夠使用您的行動應用程式資料來進行促銷活動。

若要傳送推播通知，您必須：

1. Make sure you can access the **[!UICONTROL Mobile app]** channel in Adobe Campaign.
1. 設定您的行動應用程式：

   * [Adobe Campaign](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html#SettingupamobileapplicationinAdobeCampaign)。
   * [Adobe Mobile Services](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html#ConfiguringamobileapplicationinAdobeMobileServices)。

1. 執行行動應用程式的特定設定：

   * 將從Adobe Mobile Services介面下載的組態檔封裝為行動應用程式。
   * 將Experience Cloud Mobile SDK整合至您的行動應用程式。

1. 定義您要從應用程式訂閱者收集的資料。在Adobe Campaign資料庫中擁有描述檔的行動應用程式訂閱者，會根據您定義的標準進行協調。

   For more on this, refer to this [page](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html#Collectingsubscribersdatafromamobileapplication).

1. 請在裝置上啓動行動應用程式並登入，確定已順利完成設定。請確定您選擇接收通知。
1. Then, in Adobe Campaign's advanced menu, select **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Mobile app]**.
1. 從清單中選取行動應用程式，以顯示其屬性。您的訂閱資訊會顯示在訂閱者清單下方。

   ![](assets/push_notif_mobile_app.png)

1. To check the mobile applications a profile has subscribed to, in the **[!UICONTROL Profiles & Audiences > Profiles]** menu, select a profile and click the **[!UICONTROL Edit profile properties]** button on the right. The mobile applications are listed in the **[!UICONTROL Mobile App Subscriptions]** tab.

   ![](assets/push_notif_subscriptions.png)