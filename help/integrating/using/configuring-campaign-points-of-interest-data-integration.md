---
title: 設定促銷活動興趣點資料整合
seo-title: 設定促銷活動興趣點資料整合
description: 設定促銷活動興趣點資料整合
seo-description: 瞭解如何在Adobe Campaign中設定地標資料功能，以根據用戶的位置傳送個人化訊息。
page-status-flag: 從未啓動
uuid: 0689a06c-cc1 a-442f-95b8-a07 fcec85 d79
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 整合
content-type: reference
topic-tags: 使用促銷活動與分析-行動-行動
discoiquuid: a967c6cc-c53 b-41b4-866b-90860d78 f463
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6df0e764750a31f29d6fe3ec4d92e19b3f07f728

---


# Configuring Campaign-Points of Interest data integration{#configuring-campaign-points-of-interest-data-integration}

The mobile applications used to collect location data must be configured by an **administrator** in the Adobe Campaign interface.

若要使用興趣點資料功能，您必須：

1. 存取Adobe Analytics for Mobile。查看您的授權合約，或與您的Adobe銷售代表聯絡，以瞭解更多資訊。
1. 在Adobe Campaign中設定行動應用程式。See [Setting up a mobile app in Campaign](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#setting-up-a-mobile-app-in-campaign).
1. 在Adobe Mobile Services介面中設定您的行動應用程式。這可讓您確保Adobe Mobile Services收集的資料會傳送至Adobe Campaign。See [Configuring a mobile app in Adobe Mobile Services](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#configuring-a-mobile-app-in-adobe-mobile-services).
1. 執行行動應用程式的特定設定：

   * 將從Adobe Mobile Services介面下載的組態檔封裝為行動應用程式。
   * 將Experience Cloud Mobile SDK整合至您的行動應用程式。See [Integrating the SDK into a mobile application](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#integrating-the-sdk-into-a-mobile-application).

1. 在Adobe Mobile Services介面中定義地標。See [Defining Points of Interest in Adobe Mobile Services](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#defining-points-of-interest-in-adobe-mobile-services).
1. 定義您要從行動應用程式訂閱者收集的資料。See [Collecting subscribers' Points of interest data](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#collecting-subscribers--points-of-interest-data).
1. 請確定您在Adobe Campaign中存取行動應用程式和收集的位置資料。See [Accessing mobile apps used to collect location data](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#accessing-mobile-apps-used-to-collect-location-data) and [Accessing collected location data](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#accessing-collected-location-data).

## Setting up a mobile app in Campaign {#setting-up-a-mobile-app-in-campaign}

若要能夠透過Adobe Campaign收集興趣點資料，您必須設定Adobe Campaign將接收資料的行動應用程式。

1. Click the **[!UICONTROL Adobe Campaign]** logo, in the top left corner, then select **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Mobile app]**.
1. Click **[!UICONTROL Create]** to set up an application.
1. Enter a name in the **[!UICONTROL Application name]** field and click **[!UICONTROL Create]**.

   Do not fill in the **[!UICONTROL Device-specific settings]** section. 這僅適用於設定接收推播通知的應用程式。

**[!UICONTROL Mobile application properties]** 在區段中列出兩個URL： **[!UICONTROL Collect PII endpoint]****[!UICONTROL Location Services endpoint]**&#x200B;以及它們會用於Adobe Mobile Services介面中。See [Configuring a mobile app in Adobe Mobile Services](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#configuring-a-mobile-app-in-adobe-mobile-services).

* **[!UICONTROL Collect PII endpoint]** URL是用來在行動應用程式啓動時，用來收集使用者的Experience Cloud ID和註冊Token。當使用者使用電子郵件、名字、姓氏等憑證登入應用程式時，也會收集此資料，並用來將使用者的註冊Token與Adobe Campaign設定檔協調。
* **[!UICONTROL Location Services endpoint]** URL可用來收集位置資料，例如使用者的緯度、經度和半徑。

You can now use these values in Adobe Mobile Services to finish the configuration, as explained in the [Configuring a mobile app in Adobe Mobile Services](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#configuring-a-mobile-app-in-adobe-mobile-services) section.

![](assets/poi_mobile_app_properties.png)

## Configuring a mobile app in Adobe Mobile Services {#configuring-a-mobile-app-in-adobe-mobile-services}

若要將Adobe Mobile Services收集的資料傳送至Adobe Campaign，您必須在Mobile Services介面中設定回傳。

You will need specific information that you can find in the mobile application parameters set in Adobe Campaign (see [Setting up a mobile app in Campaign](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#setting-up-a-mobile-app-in-campaign)):

* **[!UICONTROL IMS Organization ID]**
* **[!UICONTROL Collect PII Endpoint]**
* **[!UICONTROL Location Services endpoint]**

您必須擁有Adobe Analytics的存取權才能進行下列設定。如果您不是Adobe Analytics使用者，請與Adobe Campaign管理員聯絡。

1. Log into [mobilemarketing.adobe.com](http://mobilemarketing.adobe.com/).
1. 建立應用程式或選取現有應用程式。
1. Go to the **[!UICONTROL Manage App Settings]** page.
1. In the **Visitor ID Service ** section, check **Enable** and select your organization from the drop-down list. Click **Save**.

   >[!CAUTION]
   >
   >此組織必須與您在Adobe Campaign例項中使用的相同。

1. Click **[!UICONTROL Manage Postbacks]**.
1. 建立回傳。

   * Select **[!UICONTROL PII]** as the **[!UICONTROL Postback Type]**.
   * **[!UICONTROL URL]** 在欄位中，複製您在Adobe Campaign介面中設定的行動應用程式 **[!UICONTROL Collect PII Endpoint]** 中的URL，然後依照伺服器名稱進行。See [Setting up a mobile app in Campaign](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#setting-up-a-mobile-app-in-campaign).
   * Fill in the **[!UICONTROL Post Body]** field as follows:

      適用於iOS：

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

      適用於Android：

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

   * Set **Content Type** as **[!UICONTROL application/json]**.
   * In the **Which Data Tags Trigger the Postback?**&#x200B;選取任何事件(通常 **[!UICONTROL Launched]****[!UICONTROL exists]**)。
   * Click **[!UICONTROL Save & Activate]**.

1. 建立第二個回傳。

   * Select **[!UICONTROL Postback]** as the **[!UICONTROL Postback Type]**.
   * **[!UICONTROL URL]** 在欄位中，複製您在Adobe Campaign介面中設定的行動應用程式 **[!UICONTROL Location Services Endpoint]** 中的URL，然後依照伺服器名稱進行。See [Setting up a mobile app in Campaign](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#setting-up-a-mobile-app-in-campaign).
   * Fill in the **[!UICONTROL Post Body]** field as follows:

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

   * Set **Content Type** as **[!UICONTROL application/json]**.
   * In the **Which Data Tags Trigger the Postback?**&#x200B;選取 **[!UICONTROL campaign.test]** 和 **[!UICONTROL exists]**。
   * Click **[!UICONTROL Save & Activate]**.

>[!NOTE]
>
>For detailed information on configuring postbacks, refer to the [Adobe Mobile Services documentation](https://marketing.adobe.com/resources/help/en_US/mobile/signals_.html).

## Integrating the SDK into a mobile application {#integrating-the-sdk-into-a-mobile-application}

Mobile核心服務的軟體開發套件(SDK)可協助整合行動應用程式至Adobe Campaign。

This step is described in this [page](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html).

## Defining Points of Interest in Adobe Mobile Services {#defining-points-of-interest-in-adobe-mobile-services}

定義用來收集位置資料的地標：

1. 前往Adobe Mobile Services介面。
1. 新增您的應用程式。

   For more information on managing applications in Mobile Services, refer to the [Adobe Mobile Services documentation](https://marketing.adobe.com/resources/help/en_US/mobile/t_new_app.html).

1. 定義地標。

   For more information on managing Points of Interest, refer to the [Adobe Mobile Services documentation](https://marketing.adobe.com/resources/help/en_US/mobile/t_manage_points.html).

## Collecting subscribers' Points of interest data {#collecting-subscribers--points-of-interest-data}

特定自訂資源可讓您定義要從應用程式的訂閱者收集的資料。

This step is described in the [Configuring a mobile application using SDK V4](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html) page.

## Accessing mobile apps used to collect location data {#accessing-mobile-apps-used-to-collect-location-data}

若要在Adobe Campaign中存取成功建立的應用程式：

1. Click the **[!UICONTROL Adobe Campaign]** logo, in the top left corner.
1. Select **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Mobile app]**.
1. 從清單中選取行動應用程式，以顯示其屬性。

   ![](assets/poi_mobile_app_subscribers.png)

也會顯示應用程式訂閱者的清單。訂閱者是所有已安裝在行動裝置上的使用者。Adobe Campaign資料庫設定檔會以註冊Token識別。

## Accessing collected location data {#accessing-collected-location-data}

Once the setup is done, the collected Points of Interest data is listed in the **[!UICONTROL Places]** tab of each profile. 若要存取清單：

1. 選取描述檔。
1. Click the **[!UICONTROL Edit profile properties]** button on the right.
1. Select the **[!UICONTROL Places]** tab.

   ![](assets/poi_profile_places.png)

列出目前描述檔所收集的興趣點資料。位置資料會儲存在Adobe Campaign資料庫中長達個月。

For more information on accessing and editing profiles, see [Profiles](../../audiences/using/about-profiles.md).
