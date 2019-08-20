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
source-git-commit: d857bee3e7cb54ec179a73d9c256a14771cbd474

---


# 設定促銷活動興趣點資料整合{#configuring-campaign-points-of-interest-data-integration}

## 使用Adobe Experience Platform SDK設定促銷活動興趣點資料整合 {#configuring-campaign-poi-aep-sdk}

>[!NOTE]
>
>您的行動應用程式應該已在Adobe Campaign Standard中使用Adobe Experience Platform SDK設定。如需詳細步驟，請參閱本 [頁](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html)。

用來收集位置資料的行動應用程式必須由 **管理員** 在Adobe Campaign介面中設定。

若要使用Adobe Experience Platform Location Services搭配使用Adobe Experience Platform SDK設定的行動應用程式，您必須：

1. 在Adobe **[!UICONTROL Places]** Experience Platform Launch中新增和 **[!UICONTROL Places Monitor]** 擴充您的行動應用程式設定。在Adobe Campaign中設定行動應用程式。請參閱 [在Experience Platform Launch中安裝Adobe Experience Platform Launch](https://placesdocs.com/places-services-by-adobe-documentation/configure-places-in-the-sdk/places-extension#install-the-places-extension-in-adobe-experience-platform-launch) and [Installing Monitor Extension的Place擴充功能](https://placesdocs.com/places-services-by-adobe-documentation/configure-places-in-the-sdk/places-monitor-extension/using-the-places-monitor-extension)。

1. 設定好您的擴充功能後，請在內 **[!UICONTROL Adobe Experience Platform Launch]** 建資料元素，從這些擴充功能擷取資料。請參閱此 [頁面](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Step1Createdataelements) 以建立您的資料元素。

1. 然後，您 **[!UICONTROL Adobe Experience Platform Launch]**&#x200B;需要建立規則，以支援興趣點與Adobe Campaign之間的行動使用案例。\
   當使用者進入地理圍欄 **[!UICONTROL Point of Interest]**&#x200B;時，將觸發此規則。請參閱此 [頁面](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Locationpostback) 以建立規則。

1. 定義您的 **[!UICONTROL Points of Interest]** 地標。請參閱 [建立地標](https://placesdocs.com/places-services-by-adobe-documentation/places-database-management-1/managing-pois-in-the-places-ui#create-a-poi)。

1. 請確定您在Adobe Campaign中存取行動應用程式和收集的位置資料。請參閱 [存取用於收集位置資料](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#accessing-mobile-apps-used-to-collect-location-data) 及 [存取收集位置資料](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#accessing-collected-location-data)的行動應用程式。

## 使用SDK V設定促銷活動興趣點資料整合 {#configuring-campaign-poi-sdkv4}

用來收集位置資料的行動應用程式必須由 **管理員** 在Adobe Campaign介面中設定。

若要使用以SDK V設定的行動應用程式來使用興趣點資料功能，您必須：

1. 存取Adobe Analytics for Mobile。查看您的授權合約，或與您的Adobe銷售代表聯絡，以瞭解更多資訊。
1. 在Adobe Campaign中設定行動應用程式。請參閱 [「在促銷活動中設定行動應用程式](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#setting-up-a-mobile-app-in-campaign)」。
1. 在Adobe Mobile Services介面中設定您的行動應用程式。這可讓您確保Adobe Mobile Services收集的資料會傳送至Adobe Campaign。請參閱 [「在Adobe Mobile Services中設定行動應用程式](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#configuring-a-mobile-app-in-adobe-mobile-services)」。
1. 執行行動應用程式的特定設定：

   * 將從Adobe Mobile Services介面下載的組態檔封裝為行動應用程式。
   * 將Experience Cloud Mobile SDK整合至您的行動應用程式。請參閱 [「將SDK整合至行動應用](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#integrating-the-sdk-into-a-mobile-application)程式」。

1. 在Adobe Mobile Services介面中定義地標。請參閱 [「定義Adobe Mobile Services中的地標](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#defining-points-of-interest-in-adobe-mobile-services)」。
1. 定義您要從行動應用程式訂閱者收集的資料。請參閱 [「收集訂戶的興趣點資料](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#collecting-subscribers--points-of-interest-data)」。
1. 請確定您在Adobe Campaign中存取行動應用程式和收集的位置資料。請參閱 [存取用於收集位置資料](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#accessing-mobile-apps-used-to-collect-location-data) 及 [存取收集位置資料](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#accessing-collected-location-data)的行動應用程式。

### 使用SDK V在Adobe Campaign中設定行動應用程式 {#setting-up-a-mobile-app-in-campaign}

若要能夠透過Adobe Campaign收集興趣點資料，您必須設定Adobe Campaign將接收資料的行動應用程式。

1. 按一下 **[!UICONTROL Adobe Campaign]** 標誌，位於左上角，然後選取 **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Mobile app]**。
1. 按一下 **[!UICONTROL Create]** 以設定應用程式。
1. 在 **[!UICONTROL Application name]** 欄位中輸入名稱，然後按一下 **[!UICONTROL Create]**。

   請勿填寫 **[!UICONTROL Device-specific settings]** 區段。這僅適用於設定接收推播通知的應用程式。

**[!UICONTROL Mobile application properties]** 在區段中列出兩個URL： **[!UICONTROL Collect PII endpoint]****[!UICONTROL Location Services endpoint]**&#x200B;以及它們會用於Adobe Mobile Services介面中。請參閱 [「在Adobe Mobile Services中設定行動應用程式](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#configuring-a-mobile-app-in-adobe-mobile-services)」。

* **[!UICONTROL Collect PII endpoint]** URL是用來在行動應用程式啓動時，用來收集使用者的Experience Cloud ID和註冊Token。當使用者使用電子郵件、名字、姓氏等憑證登入應用程式時，也會收集此資料，並用來將使用者的註冊Token與Adobe Campaign設定檔協調。
* **[!UICONTROL Location Services endpoint]** URL可用來收集位置資料，例如使用者的緯度、經度和半徑。

您現在可以在Adobe Mobile Services中使用這些值來完成設定，如 [「Adobe Mobile Services](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#configuring-a-mobile-app-in-adobe-mobile-services) 」區段中的「設定行動應用程式」所述。

![](assets/poi_mobile_app_properties.png)

### 在Adobe Mobile Services中設定V行動應用程式 {#configuring-a-mobile-app-in-adobe-mobile-services}

若要將Adobe Mobile Services收集的資料傳送至Adobe Campaign，您必須在Mobile Services介面中設定回傳。

您需要在Adobe Campaign中設定的行動應用程式參數中找到特定資訊(請參閱 [「在促銷活動](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#setting-up-a-mobile-app-in-campaign)中設定行動應用程式」)：

* **[!UICONTROL IMS Organization ID]**
* **[!UICONTROL Collect PII Endpoint]**
* **[!UICONTROL Location Services endpoint]**

您必須擁有Adobe Analytics的存取權才能進行下列設定。如果您不是Adobe Analytics使用者，請與Adobe Campaign管理員聯絡。

1. 登入 [mobilemarketing.adobe.com](http://mobilemarketing.adobe.com/)。
1. 建立應用程式或選取現有應用程式。
1. 前往 **[!UICONTROL Manage App Settings]** 頁面。
1. 在 **訪客ID服務** 區段中，勾選 **「啓用」** 並從下拉式清單中選取您的組織。按一下 **「儲存**」。

   >[!CAUTION]
   >
   >此組織必須與您在Adobe Campaign例項中使用的相同。

1. Click **[!UICONTROL Manage Postbacks]**.
1. 建立回傳。

   * 選擇 **[!UICONTROL PII]** 為 **[!UICONTROL Postback Type]**。
   * **[!UICONTROL URL]** 在欄位中，複製您在Adobe Campaign介面中設定的行動應用程式 **[!UICONTROL Collect PII Endpoint]** 中的URL，然後依照伺服器名稱進行。請參閱 [「在促銷活動中設定行動應用程式](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#setting-up-a-mobile-app-in-campaign)」。
   * 填寫 **[!UICONTROL Post Body]** 欄位如下：

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

   * 將 **內容類型設定** 為 **[!UICONTROL application/json]**。
   * 哪些 **資料標籤觸發回傳？**&#x200B;選取任何事件(通常 **[!UICONTROL Launched]****[!UICONTROL exists]**)。
   * Click **[!UICONTROL Save & Activate]**.

1. 建立第二個回傳。

   * 選擇 **[!UICONTROL Postback]** 為 **[!UICONTROL Postback Type]**。
   * **[!UICONTROL URL]** 在欄位中，複製您在Adobe Campaign介面中設定的行動應用程式 **[!UICONTROL Location Services Endpoint]** 中的URL，然後依照伺服器名稱進行。請參閱 [「在促銷活動中設定行動應用程式](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#setting-up-a-mobile-app-in-campaign)」。
   * 填寫 **[!UICONTROL Post Body]** 欄位如下：

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

   * 將 **內容類型設定** 為 **[!UICONTROL application/json]**。
   * 哪些 **資料標籤觸發回傳？**&#x200B;選取 **[!UICONTROL campaign.test]** 和 **[!UICONTROL exists]**。
   * Click **[!UICONTROL Save & Activate]**.

>[!NOTE]
>
>有關設定回傳的詳細資訊，請參閱 [Adobe Mobile Services文件](https://marketing.adobe.com/resources/help/en_US/mobile/signals_.html)。

### 將SDK整合至行動應用程式 {#integrating-the-sdk-into-a-mobile-application}

Mobile核心服務的軟體開發套件(SDK)可協助整合行動應用程式至Adobe Campaign。

本 [步驟說明此步驟](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html)。

### 在Adobe Mobile Services中定義興趣點 {#defining-points-of-interest-in-adobe-mobile-services}

定義用來收集位置資料的地標：

1. 前往Adobe Mobile Services介面。
1. 新增您的應用程式。

   如需在Mobile Services中管理應用程式的詳細資訊，請參閱 [Adobe Mobile Services文件](https://marketing.adobe.com/resources/help/en_US/mobile/t_new_app.html)。

1. 定義地標。

   有關管理地標的更多資訊，請參閱 [Adobe Mobile Services文件](https://marketing.adobe.com/resources/help/en_US/mobile/t_manage_points.html)。

### 收集用戶的興趣點資料 {#collecting-subscribers--points-of-interest-data}

特定自訂資源可讓您定義要從應用程式的訂閱者收集的資料。

此步驟說明在 [使用SDK V](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html) 頁面設定行動應用程式中。


## 存取用於收集位置資料的行動應用程式 {#accessing-mobile-apps-used-to-collect-location-data}

若要在Adobe Campaign中存取成功建立的應用程式：

1. 按一下 **[!UICONTROL Adobe Campaign]** 左上角的標誌。
1. 選取 **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt;或 **[!UICONTROL Mobile app (SDK v4)]****[!UICONTROL Mobile app (AEP SDK)]** 視SDK而定。
1. 從清單中選取行動應用程式，以顯示其屬性。

   ![](assets/poi_mobile_app_subscribers.png)

應用程式的訂閱者清單也會顯示在 **[!UICONTROL Mobile application subscribers]** 標籤中。訂閱者是所有已安裝在行動裝置上的使用者。Adobe Campaign資料庫設定檔會以註冊Token識別。

## 存取收集的位置資料 {#accessing-collected-location-data}

完成設定後，收集的地標資料會列在每個描述檔 **[!UICONTROL Places]** 的索引標籤中。若要存取清單：

1. 選取描述檔。
1. 按一下右邊的 **[!UICONTROL Edit profile properties]** 按鈕。
1. 選取 **[!UICONTROL Places]** 標籤。

   ![](assets/poi_profile_places.png)

列出目前描述檔所收集的興趣點資料。位置資料會儲存在Adobe Campaign資料庫中長達個月。

如需存取和編輯設定檔的詳細資訊，請參閱 [設定檔](../../audiences/using/about-profiles.md)。
