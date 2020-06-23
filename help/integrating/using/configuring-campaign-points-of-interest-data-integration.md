---
title: 設定 Campaign-Points of Interest 資料整合
description: 瞭解如何設定Adobe Campaign中的地標資料功能，以根據訂閱者的位置傳送個人化訊息。
page-status-flag: never-activated
uuid: 0689a06c-cc1a-442f-95b8-a07fcec85d79
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics-for-mobile
discoiquuid: a967c6cc-c53b-41b4-866b-90860d78f463
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f7adb7a4725129727010c2486ca34bbc2021c539
workflow-type: tm+mt
source-wordcount: '1340'
ht-degree: 1%

---


# 設定 Campaign-Points of Interest 資料整合{#configuring-campaign-points-of-interest-data-integration}

## 設定與Adobe Experience Platform SDK的促銷活動興趣點資料整合 {#configuring-campaign-poi-aep-sdk}

>[!NOTE]
>
>您的行動應用程式應已使用Adobe Experience Platform SDK在Adobe Campaign Standard中設定。 如需詳細步驟，請參閱本 [頁](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html)。

用來收集位置資料的行動應用程式必須由Adobe Campaign介面 **中的管** 理員設定。

若要將Adobe Experience Platform Location Services與以Adobe Experience Platform SDK設定的行動應用程式搭配使用，您必須：

1. 在Adobe Experience Platform Launch **[!UICONTROL Places]** 中將 **[!UICONTROL Places Monitor]** 和擴充功能新增至您的行動應用程式設定。 在Adobe Campaign中設定您的行動應用程式。 請參 [閱在Adobe Experience Platform Launch中安裝Places擴充功能](https://docs.adobe.com/content/help/en/places/using/places-ext-aep-sdks/places-extension/places-extension.html#install-the-places-extension-in-adobe-experience-platform-launch) , [並在Experience Platform Launch中安裝Places Monitor擴充功能](https://docs.adobe.com/content/help/en/places/using/places-ext-aep-sdks/places-monitor-extension/using-places-monitor-extension.html#install-the-places-monitor-extension-in-experience-platform-launch)。

1. 在設定擴充功能後，請在中建立資料元素，以 **[!UICONTROL Adobe Experience Platform Launch]** 從這些擴充功能擷取資料。 請參閱本頁 [以建立](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Step1Createdataelements) 您的資料元素。

1. 然後，您 **[!UICONTROL Adobe Experience Platform Launch]**&#x200B;需要建立規則，以支援興趣點和Adobe Campaign之間的行動使用案例。\
   當使用者進入地理圍欄時，將會觸發此規則 **[!UICONTROL Point of Interest]**。 請參閱此 [頁](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Locationpostback) ，以建立規則。

1. 在地標中 **[!UICONTROL Points of Interest]** 定義您的。 請 [參閱建立興趣點](https://docs.adobe.com/content/help/en/places/using/poi-mgmt-ui/create-a-poi-ui.html)。

1. 請確定您存取行動應用程式和Adobe Campaign中收集的位置資料。 請參 [閱存取用於收集位置資料的行動應用程式](#accessing-mobile-apps-used-to-collect-location-data) ，以 [及存取收集的位置資料](#accessing-collected-location-data)。

## 使用SDK V4設定促銷活動興趣點資料整合 {#configuring-campaign-poi-sdkv4}

用來收集位置資料的行動應用程式必須由Adobe Campaign介面 **中的管** 理員設定。

若要搭配使用SDK V4設定的行動應用程式使用興趣點資料功能，您必須：

1. 可存取Adobe Analytics for Mobile。 如需詳細資訊，請查看您的授權合約或與Adobe銷售代表聯絡。
1. 在Adobe Campaign中設定您的行動應用程式。 請參 [閱「在Campaign中設定行動應用程式」](#setting-up-a-mobile-app-in-campaign)。
1. 在Adobe Mobile Services介面中設定您的行動應用程式。 這可讓您確保Adobe Mobile Services收集的資料會傳送至Adobe Campaign。 請參 [閱在Adobe Mobile Services中設定行動應用程式](#configuring-a-mobile-app-in-adobe-mobile-services)。
1. 執行行動應用程式的特定設定：

   * 將從Adobe Mobile Services介面下載的設定檔與行動應用程式封裝。
   * 將Experience Cloud Mobile SDK整合到您的行動應用程式中。 請參 [閱將SDK整合至行動應用程式](#integrating-the-sdk-into-a-mobile-application)。

1. 在Adobe Mobile Services介面中定義地標。 請參 [閱定義Adobe Mobile Services的興趣點](#defining-points-of-interest-in-adobe-mobile-services)。
1. 定義您要向行動應用程式的訂閱者收集的資料。 請參 [閱收集訂閱者的興趣點資料](#collecting-subscribers--points-of-interest-data)。
1. 請確定您存取行動應用程式和Adobe Campaign中收集的位置資料。 請參 [閱存取用於收集位置資料的行動應用程式](#accessing-mobile-apps-used-to-collect-location-data) ，以 [及存取收集的位置資料](#accessing-collected-location-data)。

### 使用SDK V4在Adobe Campaign中設定行動應用程式 {#setting-up-a-mobile-app-in-campaign}

若要能夠透過Adobe Campaign收集興趣點資料，您必須設定Adobe Campaign將從哪些行動應用程式接收資料。

1. 按一下 **[!UICONTROL Adobe Campaign]** 左上角的標誌，然後選取 **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app]**。
1. 按一 **[!UICONTROL Create]** 下以設定應用程式。
1. 在欄位中輸入名 **[!UICONTROL Application name]** 稱，然後按一下 **[!UICONTROL Create]**。

   不要填寫該 **[!UICONTROL Device-specific settings]** 部分。 這僅適用於設定接收推播通知的應用程式。

在區 **[!UICONTROL Mobile application properties]** 段中，列出兩個URL: **[!UICONTROL Collect PII endpoint]** 和 **[!UICONTROL Location Services endpoint]**。 它們將用於Adobe Mobile Services介面。 請參 [閱在Adobe Mobile Services中設定行動應用程式](#configuring-a-mobile-app-in-adobe-mobile-services)。

* URL **[!UICONTROL Collect PII endpoint]** 用於在啟動行動應用程式時，從行動應用程式收集使用者的Experience Cloud ID和註冊Token。 當使用者使用電子郵件、名字、姓氏等憑證登入應用程式時，也會收集此資料，並用來協調使用者的註冊Token與Adobe Campaign設定檔。
* URL **[!UICONTROL Location Services endpoint]** 可用來從地標收集位置資料，例如使用者的緯度、經度和半徑。

您現在可以在Adobe Mobile Services中使用這些值來完成設定，如在Adobe Mobile Services中 [設定行動應用程式一節中所述](#configuring-a-mobile-app-in-adobe-mobile-services) 。

![](assets/poi_mobile_app_properties.png)

### 在Adobe Mobile Services中設定V4行動應用程式 {#configuring-a-mobile-app-in-adobe-mobile-services}

若要將Adobe Mobile Services收集的資料傳送至Adobe Campaign，您必須在Mobile Services介面中設定回傳。

您將需要可在Adobe Campaign中設定的行動應用程式參數中找到的特定資訊(請參閱 [在Campaign中設定行動應用程式](#setting-up-a-mobile-app-in-campaign)):

* **[!UICONTROL IMS Organization ID]**
* **[!UICONTROL Collect PII Endpoint]**
* **[!UICONTROL Location Services endpoint]**

您必須擁有Adobe Analytics的存取權，才能執行下列設定。 如果您不是Adobe Analytics使用者，請連絡您的Adobe Campaign管理員。

1. 登入 [mobilemarketing.adobe.com](https://mobilemarketing.adobe.com/)。
1. 建立應用程式或選取現有的應用程式。
1. 前往頁 **[!UICONTROL Manage App Settings]** 面。
1. 在「訪 **客ID服務** 」區段中，勾選「 **啟用** 」並從下拉式清單中選取您的組織。 按一下 **儲存**。

   >[!CAUTION]
   >
   >此組織必須與您在Adobe Campaign例項上使用的組織相同。

1. 按一下「**[!UICONTROL Manage Postbacks]**」。
1. 建立回傳。

   * 選擇 **[!UICONTROL PII]** 作為 **[!UICONTROL Postback Type]**。
   * 在欄位 **[!UICONTROL URL]** 中，從您在Adobe Campaign介面中設定的行動應用程式複製 **[!UICONTROL Collect PII Endpoint]** URL，前面加上伺服器名稱。 請參 [閱「在Campaign中設定行動應用程式」](#setting-up-a-mobile-app-in-campaign)。
   * 填寫欄 **[!UICONTROL Post Body]** 位如下：

      針對iOS:

      ```
      {
      "userKey": "{userKey}",
      "pushPlatform":"apns",
      "marketingCloudId":"{%mcid%}",
      "cusEmail":"{email}",
      "cusFirstName":"{firstName}",
      "cusLastName":"{lastName}"
      }
      ```

      針對Android:

      ```
      {
      "userKey": "{userKey}",
      "pushPlatform":"gcm",
      "marketingCloudId":"{%mcid%}",
      "cusEmail":"{email}",
      "cusFirstName":"{firstName}",
      "cusLastName":"{lastName}"
      }
      ```

   * 將「 **內容類型** 」設 **[!UICONTROL application/json]**&#x200B;為。
   * 在哪些 **資料標籤中觸發回傳？**，請選擇任何事件，通常 **[!UICONTROL Launched]** 和 **[!UICONTROL exists]**。
   * 按一下「**[!UICONTROL Save & Activate]**」。

1. 建立第二個回傳。

   * 選擇 **[!UICONTROL Postback]** 作為 **[!UICONTROL Postback Type]**。
   * 在欄位 **[!UICONTROL URL]** 中，從您在Adobe Campaign介面中設定的行動應用程式複製 **[!UICONTROL Location Services Endpoint]** URL，前面加上伺服器名稱。 請參 [閱「在Campaign中設定行動應用程式」](#setting-up-a-mobile-app-in-campaign)。
   * 填寫欄 **[!UICONTROL Post Body]** 位如下：

      ```
      {
      "locationData":{
      "distances":"{a.loc.dist}",
      "poiLabel":"{a.loc.poi}",
      "latitude.a":"{a.loc.lat.a}",
      "latitude.b":"{a.loc.lat.b}",
      "latitude.c":"{a.loc.lat.c}",
      "longitude.a":"{a.loc.lon.a}",
      "longitude.b":"{a.loc.lon.b}",
      "longitude.c":"{a.loc.lon.c}",
      "appId":"{a.appid}",
      "marketingCloudId":"{mid}"
      }
      }
      ```

   * 將「 **內容類型** 」設 **[!UICONTROL application/json]**&#x200B;為。
   * 在哪些 **資料標籤中觸發回傳？**，選擇 **[!UICONTROL campaign.test]** 和 **[!UICONTROL exists]**。
   * 按一下「**[!UICONTROL Save & Activate]**」。

>[!NOTE]
>
>如需設定回傳的詳細資訊，請參閱 [Adobe Mobile Services檔案](https://docs.adobe.com/content/help/en/mobile-services/using/manage-app-settings-ug/configuring-app/signals.html)。

### 將SDK整合至行動應用程式 {#integrating-the-sdk-into-a-mobile-application}

Mobile核心服務的軟體開發套件(SDK)可協助將行動應用程式整合至Adobe Campaign。

本頁說明此步 [驟](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html)。

### 定義Adobe Mobile Services的興趣點 {#defining-points-of-interest-in-adobe-mobile-services}

要定義用於收集地點資料的地標：

1. 前往Adobe Mobile Services介面。
1. 新增您的應用程式。

   如需在Mobile Services中管理應用程式的詳細資訊，請參閱 [Adobe Mobile Services檔案](https://docs.adobe.com/content/help/en/mobile-services/using/manage-apps-ug/t-new-app.html)。

1. 定義地標。

   如需有關管理地標的詳細資訊，請參閱 [Adobe Mobile Services檔案](https://docs.adobe.com/content/help/en/mobile-services/using/location-ug/t-manage-points.html)。

### 收集用戶興趣點資料 {#collecting-subscribers--points-of-interest-data}

特定的自訂資源可讓您定義要從應用程式訂閱者收集的資料。

此步驟在「使用SDK V4 [設定行動應用程式」頁面中說明](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html) 。


## 存取用於收集位置資料的行動應用程式 {#accessing-mobile-apps-used-to-collect-location-data}

若要存取Adobe Campaign中成功建立的應用程式：

1. 按一下 **[!UICONTROL Adobe Campaign]** 左上角的標誌。
1. 選取 **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (SDK v4)]** 或視 **[!UICONTROL Mobile app (AEP SDK)]** SDK而定。
1. 從清單中選取行動應用程式以顯示其屬性。

   ![](assets/poi_mobile_app_subscribers.png)

應用程式的訂閱者清單也會顯示在標籤 **[!UICONTROL Mobile application subscribers]** 中。 訂閱者是所有已在其行動裝置上安裝應用程式的使用者。 Adobe Campaign資料庫設定檔會以註冊Token來識別。

## 存取收集的位置資料 {#accessing-collected-location-data}

完成設定後，收集到的地標資料會列在每個描述檔 **[!UICONTROL Places]** 的標籤中。 要訪問清單：

1. 選取描述檔。
1. 按一下 **[!UICONTROL Edit profile properties]** 右側的按鈕。
1. 選擇選 **[!UICONTROL Places]** 項卡。

   ![](assets/poi_profile_places.png)

會列出目前設定檔所收集的地標資料。 位置資料會儲存在Adobe Campaign資料庫中6個月。

有關訪問和編輯配置檔案的詳細資訊，請參 [閱Profiles](../../audiences/using/about-profiles.md)。
