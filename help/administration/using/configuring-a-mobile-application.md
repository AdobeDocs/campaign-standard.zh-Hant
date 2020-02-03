---
title: 設定行動應用程式
description: 瞭解如何設定Adobe Campaign，以使用SDK V4或Experience Platform SDK傳送推播通知或應用程式內訊息。
page-status-flag: never-activated
uuid: 63e1476a-7875-4f48-ba9e-97f1a0007e42
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: configuring-channels
discoiquuid: 2a14500f-5ede-4131-8b1a-b7fd65b7e3aa
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: aa1539a1fc5fd08e7cf4e081ae2517e39ddde121

---


# 設定行動應用程式{#configuring-a-mobile-application}

在行動應用程式上，會收到推播通知或應用程式內訊息，這些應用程式首先需要在Adobe Campaign standard中設定，視您要使用的頻道而定。

若要傳送應用程式內訊息和推播通知，您的行動應用程式必須在Adobe Campaign中運用Adobe Experience Platform SDK來設定。 請參 [閱「使用Adobe Experience Platform SDK](#using-adobe-experience-platform-sdk)」。

在Adobe Campaign中運用Experience Cloud Mobile SDK V4或Experience Platform SDK設定行動應用程式後，必須由管理員在 [!UICONTROL Administration] > [!UICONTROL Channels] >選單下設 [!UICONTROL Mobile app] 定。

>[!CAUTION]
>
>推播通知和應用程式內建置必須由專家使用者執行。 如果您需要協助，請聯絡您的Adobe客戶主管或專業服務合作夥伴。

設定行動應用程式後，您就可以擷取其收集的PII資料，以從資料庫建立或更新描述檔。 如需更多相關資訊，請參閱本節：根 [據行動應用程式資料建立和更新個人檔案資訊](../../channels/using/updating-profile-with-mobile-app-data.md)。

如需Adobe Campaign standard中行動傳送的一般准則，請參閱本頁 [面](https://helpx.adobe.com/campaign/kb/acs-mobile.html)

## 使用Adobe Experience Platform SDK {#using-adobe-experience-platform-sdk}

>[!Note]
>
>若要進一步瞭解使用Adobe Experience Platform SDK的Adobe Campaign standard支援的不同行動使用案例，請參閱本 [頁](https://helpx.adobe.com/campaign/kb/configure-launch-rules-acs-use-cases.html)。

若要使用Experience Platform SDK應用程式傳送推播通知和應用程式內訊息，行動應用程式必須在Adobe Experience Platform Experience Platform Launch中設定，並在Adobe Campaign中設定。 如需使用Experience Platform SDK設定行動應用程式的詳細步驟，請參閱本 [頁](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html)。

請依照下列步驟啟動設定：

1. 請確定您可以存取頻 **[!UICONTROL Mobile]**道：Adobe Campaign中的推播通知和應用程式內訊息。 如果沒有，請連絡您的帳戶團隊。

   ![](assets/launch_1.png)

1. 在Experience Platform Launch中建立行動應用程式，方法是建立Mobile類型的屬性。 如需詳細資訊，請參閱 [Experience Platform Launch檔案](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#create-a-new-mobile-property) 。
1. 在Experience Platform Launch **[!UICONTROL Adobe Campaign Standard]**中安裝行動應用程式的擴充功能：

   如需擴充功能的詳細資訊，請參閱 [Experience Platform Launch檔案](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard) 。

1. 在Adobe Launch中設定應用程式的規則，請參閱在Launch [中設定應用程式](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Step1Createdataelements)
1. 在Adobe Campaign standard中設定您的Adobe Launch應用程式，請參 [閱「在Adobe Campaign中設定Adobe Launch應用程式」](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#SettingupyourAdobeLaunchapplicationinAdobeCampaign)。
1. 將頻道專用的設定新增至您的行動應用程式設定，請參 [閱Adobe Campaign中頻道專用的應用程式設定](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#ChannelspecificapplicationconfigurationinAdobeCampaign)。

   ![](assets/launch_2.png)
