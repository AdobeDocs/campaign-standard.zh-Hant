---
title: 設定 Campaign-Points of Interest 資料整合
description: 了解如何在Adobe Campaign中設定地標資料功能，以根據訂閱者的位置傳送個人化訊息。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics-for-mobile
feature: Audiences
role: Data Architect
level: Intermediate
exl-id: b097b3fa-f949-446e-ad44-cc6ca025ee55
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '1328'
ht-degree: 2%

---

# 設定 Campaign-Points of Interest 資料整合{#configuring-campaign-points-of-interest-data-integration}

## 使用Adobe Experience Platform SDK設定Campaign-Points of Interest資料整合 {#configuring-campaign-poi-aep-sdk}

>[!NOTE]
>
>您的行動應用程式應已使用Adobe Experience Platform SDK在Adobe Campaign Standard中設定。 如需詳細步驟，請參閱 [頁面](https://helpx.adobe.com/tw/campaign/kb/configuring-app-sdk.html).

用於收集位置資料的行動應用程式必須由 **管理員** 在Adobe Campaign介面中。

若要搭配以Adobe Experience Platform SDK設定的行動應用程式使用Adobe Experience Platform Location Services，您必須：

1. 新增 **[!UICONTROL Places]** 和 **[!UICONTROL Places Monitor]** 擴充功能至Adobe Experience Platform Launch中的行動應用程式設定。 在Adobe Campaign中設定您的行動應用程式。 請參閱 [在Adobe Experience Platform Launch中安裝Places擴充功能](https://experienceleague.adobe.com/docs/places/using/places-ext-aep-sdks/places-extension/places-extension.html#install-the-places-extension-in-adobe-experience-platform-launch) 和 [在Experience Platform Launch中安裝Places監視器擴充功能](https://experienceleague.adobe.com/docs/places/using/places-ext-aep-sdks/places-monitor-extension/using-places-monitor-extension.html#install-the-places-monitor-extension-in-experience-platform-launch).

1. 設定擴充功能後，在中建立資料元素 **[!UICONTROL Adobe Experience Platform Launch]** 從這些擴充功能擷取資料。 請參閱 [頁面](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Step1Createdataelements) 來建立資料元素。

1. 然後，在 **[!UICONTROL Adobe Experience Platform Launch]**，您需要建立規則，以支援興趣點和Adobe Campaign之間的行動使用案例。\
   當使用者進入包圍型環境時，就會觸發此規則 **[!UICONTROL Point of Interest]**. 請參閱 [頁面](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Locationpostback) 來建立規則。

1. 定義 **[!UICONTROL Points of Interest]** 在地方。 請參閱 [建立地標](https://experienceleague.adobe.com/docs/places/using/poi-mgmt-ui/create-a-poi-ui.html).

1. 請務必存取行動應用程式和Adobe Campaign中收集的位置資料。 請參閱 [存取用於收集位置資料的行動應用程式](#accessing-mobile-apps-used-to-collect-location-data) 和 [存取收集的位置資料](#accessing-collected-location-data).

## 使用SDK V4設定Campaign-Points of Interest資料整合 {#configuring-campaign-poi-sdkv4}

用於收集位置資料的行動應用程式必須由 **管理員** 在Adobe Campaign介面中。

若要搭配使用SDK V4設定的行動應用程式使用興趣點資料功能，您必須：

1. 可存取Adobe Analytics for Mobile。 如需詳細資訊，請查看您的授權合約或聯絡您的Adobe帳戶執行官。
1. 在Adobe Campaign中設定您的行動應用程式。 請參閱 [在Campaign中設定行動應用程式](#setting-up-a-mobile-app-in-campaign).
1. 在AdobeMobile Services介面中設定您的行動應用程式。 這可讓您確保由AdobeMobile Services收集的資料傳送至Adobe Campaign。 請參閱 [在AdobeMobile Services中設定行動應用程式](#configuring-a-mobile-app-in-adobe-mobile-services).
1. 執行行動應用程式的特定設定：

   * 使用行動應用程式封裝從AdobeMobile Services介面下載的設定檔案。
   * 將Experience Cloud行動SDK整合至您的行動應用程式。 請參閱 [將SDK整合至行動應用程式](#integrating-the-sdk-into-a-mobile-application).

1. 在AdobeMobile Services介面中定義地標。 請參閱 [定義AdobeMobile Services中的地標](#defining-points-of-interest-in-adobe-mobile-services).
1. 定義您要從行動應用程式訂閱者收集的資料。 請參閱 [收集訂閱者的地標資料](#collecting-subscribers--points-of-interest-data).
1. 請務必存取行動應用程式和Adobe Campaign中收集的位置資料。 請參閱 [存取用於收集位置資料的行動應用程式](#accessing-mobile-apps-used-to-collect-location-data) 和 [存取收集的位置資料](#accessing-collected-location-data).

### 使用SDK V4在Adobe Campaign中設定行動應用程式 {#setting-up-a-mobile-app-in-campaign}

若要透過Adobe Campaign收集地標資料，您必須設定Adobe Campaign將從哪個行動應用程式接收資料。

1. 按一下 **Adobe** 徽標，在左上角，然後選擇 **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app]**.
1. 按一下 **[!UICONTROL Create]** 來設定應用程式。
1. 在 **[!UICONTROL Application name]** 欄位，按一下 **[!UICONTROL Create]**.

   請勿填入 **[!UICONTROL Device-specific settings]** 區段。 這隻適用於設定接收推播通知的應用程式。

在 **[!UICONTROL Mobile application properties]** 區段中，列出兩個URL: **[!UICONTROL Collect PII endpoint]** 和 **[!UICONTROL Location Services endpoint]**. 它們將用於AdobeMobile Services介面。 請參閱 [在AdobeMobile Services中設定行動應用程式](#configuring-a-mobile-app-in-adobe-mobile-services).

* 此 **[!UICONTROL Collect PII endpoint]** URL可在啟動時，從行動應用程式收集使用者的Experience CloudID和註冊Token。 當使用者使用電子郵件、名字、姓氏等憑證登入應用程式時，系統也會收集這些資料，並用來將使用者的註冊Token與Adobe Campaign設定檔調解。
* 此 **[!UICONTROL Location Services endpoint]** URL可用來收集位置資料，例如使用者從地標經度和半徑的緯度。

您現在可以在AdobeMobile Services中使用這些值來完成設定，如 [在AdobeMobile Services中設定行動應用程式](#configuring-a-mobile-app-in-adobe-mobile-services) 區段。

![](assets/poi_mobile_app_properties.png)

### 在AdobeMobile Services中設定V4行動應用程式 {#configuring-a-mobile-app-in-adobe-mobile-services}

若要將AdobeMobile Services收集的資料傳送至Adobe Campaign，您必須在Mobile Services介面中設定回傳。

您將需要可在Adobe Campaign中設定的行動應用程式參數中找到的特定資訊(請參閱 [在Campaign中設定行動應用程式](#setting-up-a-mobile-app-in-campaign)):

* **[!UICONTROL IMS Organization ID]**
* **[!UICONTROL Collect PII Endpoint]**
* **[!UICONTROL Location Services endpoint]**

您必須擁有Adobe Analytics的存取權，才能進行下列設定。 如果您不是Adobe Analytics使用者，請聯絡您的Adobe Campaign管理員。

1. 登入 [mobilemarketing.adobe.com](https://mobilemarketing.adobe.com/).
1. 建立應用程式或選取現有應用程式。
1. 前往 **[!UICONTROL Manage App Settings]** 頁面。
1. 在 **訪客ID服務** 區段，核取 **啟用** 並從下拉式清單中選取您的組織。 按一下 **儲存**.

   >[!CAUTION]
   >
   >此組織必須與您在Adobe Campaign例項上使用的組織相同。

1. 按一下&#x200B;**[!UICONTROL Manage Postbacks]**。
1. 建立回傳。

   * 選擇 **[!UICONTROL PII]** 作為 **[!UICONTROL Postback Type]**.
   * 在 **[!UICONTROL URL]** 欄位，複製 **[!UICONTROL Collect PII Endpoint]** 來自您在Adobe Campaign介面中設定的行動應用程式的URL，前面加上伺服器名稱。 請參閱 [在Campaign中設定行動應用程式](#setting-up-a-mobile-app-in-campaign).
   * 填入 **[!UICONTROL Post Body]** 欄位，如下所示：

      若為iOS:

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

      對於Android:

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

   * 設定 **內容類型** as **[!UICONTROL application/json]**.
   * 在 **哪些資料標籤會觸發回傳？**，選取任何事件，通常 **[!UICONTROL Launched]** 和 **[!UICONTROL exists]**.
   * 按一下&#x200B;**[!UICONTROL Save & Activate]**。

1. 建立第二個回傳。

   * 選擇 **[!UICONTROL Postback]** 作為 **[!UICONTROL Postback Type]**.
   * 在 **[!UICONTROL URL]** 欄位，複製 **[!UICONTROL Location Services Endpoint]** 來自您在Adobe Campaign介面中設定的行動應用程式的URL，前面加上伺服器名稱。 請參閱 [在Campaign中設定行動應用程式](#setting-up-a-mobile-app-in-campaign).
   * 填入 **[!UICONTROL Post Body]** 欄位，如下所示：

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

   * 設定 **內容類型** as **[!UICONTROL application/json]**.
   * 在 **哪些資料標籤會觸發回傳？**，選取 **[!UICONTROL campaign.test]** 和 **[!UICONTROL exists]**.
   * 按一下&#x200B;**[!UICONTROL Save & Activate]**。

>[!NOTE]
>
>如需設定回傳的詳細資訊，請參閱 [AdobeMobile Services檔案](https://experienceleague.adobe.com/docs/mobile-services/using/manage-app-settings-ug/configuring-app/signals.html).

### 將SDK整合至行動應用程式 {#integrating-the-sdk-into-a-mobile-application}

行動核心服務的軟體開發套件(SDK)有助於將行動應用程式整合至Adobe Campaign。

此步驟將於此 [頁面](https://helpx.adobe.com/tw/campaign/kb/configuring-app-sdkv4.html).

### 定義AdobeMobile Services中的地標 {#defining-points-of-interest-in-adobe-mobile-services}

要定義用於收集位置資料的地標，請執行以下操作：

1. 前往AdobeMobile Services介面。
1. 新增您的應用程式。

   如需在Mobile Services中管理應用程式的詳細資訊，請參閱 [AdobeMobile Services檔案](https://experienceleague.adobe.com/docs/mobile-services/using/manage-apps-ug/t-new-app.html).

1. 定義地標。

   如需管理地標的詳細資訊，請參閱 [AdobeMobile Services檔案](https://experienceleague.adobe.com/docs/mobile-services/using/location-ug/t-manage-points.html).

### 收集訂閱者的地標資料 {#collecting-subscribers--points-of-interest-data}

特定的自訂資源可讓您定義要從應用程式訂閱者收集的資料。

此步驟在 [使用SDK V4設定行動應用程式](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html) 頁面。


## 存取用於收集位置資料的行動應用程式 {#accessing-mobile-apps-used-to-collect-location-data}

若要存取在Adobe Campaign中成功建立的應用程式：

1. 按一下 **Adobe** 徽標，在左上角。
1. 選擇 **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (SDK v4)]** 或 **[!UICONTROL Mobile app (AEP SDK)]** 視SDK而定。
1. 從清單中選取行動應用程式以顯示其屬性。

   ![](assets/poi_mobile_app_subscribers.png)

應用程式的訂閱者清單也會顯示在 **[!UICONTROL Mobile application subscribers]** 標籤。 訂閱者是在其行動裝置上安裝應用程式的所有使用者。 Adobe Campaign資料庫設定檔以註冊Token來識別。

## 存取收集的位置資料 {#accessing-collected-location-data}

完成設定後，收集的地標資料會列在 **[!UICONTROL Places]** 標籤。 若要存取清單：

1. 選取設定檔。
1. 按一下 **[!UICONTROL Edit profile properties]** 按鈕。
1. 選取 **[!UICONTROL Places]** 索引標籤。

   ![](assets/poi_profile_places.png)

會列出目前設定檔所收集的地標資料。 位置資料會儲存在Adobe Campaign資料庫6個月。

如需存取和編輯設定檔的詳細資訊，請參閱 [設定檔](../../audiences/using/about-profiles.md).
