---
title: 設定 Campaign-Points of Interest 資料整合
description: 瞭解如何在Adobe Campaign中設定興趣點資料功能，以根據訂閱者的位置傳送個人化訊息。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics-for-mobile
feature: Audiences
role: Data Architect
level: Intermediate
exl-id: b097b3fa-f949-446e-ad44-cc6ca025ee55
source-git-commit: 884cd5e9c09aa85e744ca06b202eb46f73a33a76
workflow-type: tm+mt
source-wordcount: '1311'
ht-degree: 2%

---

# 設定 Campaign-Points of Interest 資料整合{#configuring-campaign-points-of-interest-data-integration}

## 使用Adobe Experience Platform SDK設定Campaign-Points of Interest資料整合 {#configuring-campaign-poi-aep-sdk}

>[!NOTE]
>
>您的行動應用程式應已透過Adobe Experience Platform SDK在Adobe Campaign Standard中設定。 如需詳細步驟，請參閱此 [頁面](https://helpx.adobe.com/tw/campaign/kb/configuring-app-sdk.html).

用來收集位置資料的行動應用程式必須由設定 **管理員** 在Adobe Campaign介面中。

若要將Adobe Experience Platform Location Services與已設定Adobe Experience Platform SDK的行動應用程式搭配使用，您需要：

1. 新增 **[!UICONTROL Places]** 資料收集UI中行動應用程式設定的擴充功能。 在Adobe Campaign中設定行動應用程式。 另請參閱 [安裝Places擴充功能](https://experienceleague.adobe.com/docs/places/using/places-ext-aep-sdks/places-extension/places-extension.html#install-the-places-extension-in-adobe-experience-platform-launch).

1. 擴充功能設定完成後，請在資料收集UI中建立資料元素，以從這些擴充功能擷取資料。 請參閱此 [頁面](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Step1Createdataelements) 以建立您的資料元素。

1. 然後，在資料收集UI中，您需要建立規則以支援Point of Interest和Adobe Campaign之間的行動使用案例。\
   當使用者進入地理圍欄時，將觸發此規則 **[!UICONTROL Point of Interest]**. 請參閱此 [頁面](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Locationpostback) 以建立您的規則。

1. 定義您的 **[!UICONTROL Points of Interest]** 於地標中。 另請參閱 [建立地標](https://experienceleague.adobe.com/docs/places/using/poi-mgmt-ui/create-a-poi-ui.html).

1. 請務必存取行動應用程式和在Adobe Campaign中收集的位置資料。 另請參閱 [存取用來收集位置資料的行動應用程式](#accessing-mobile-apps-used-to-collect-location-data) 和 [存取收集的位置資料](#accessing-collected-location-data).

## 使用SDK V4設定Campaign-Points of Interest資料整合 {#configuring-campaign-poi-sdkv4}

用來收集位置資料的行動應用程式必須由設定 **管理員** 在Adobe Campaign介面中。

若要將Point of Interest資料功能用於以SDK V4設定的行動應用程式，您需要：

1. 存取適用於行動裝置的Adobe Analytics。 請檢視授權合約，或聯絡Adobe客戶經理以取得詳細資訊。
1. 在Adobe Campaign中設定行動應用程式。 另請參閱 [在Campaign中設定行動應用程式](#setting-up-a-mobile-app-in-campaign).
1. 在Adobe Mobile Services介面中設定您的行動應用程式。 這可讓您確保Adobe Mobile Services收集的資料傳送至Adobe Campaign。 另請參閱 [在Adobe Mobile Services中設定行動應用程式](#configuring-a-mobile-app-in-adobe-mobile-services).
1. 執行行動應用程式的特定設定：

   * 將從AdobeMobile Services介面下載的設定檔案與行動應用程式封裝。
   * 將Experience Cloud Mobile SDK整合至您的行動應用程式。 另請參閱 [將SDK整合至行動應用程式](#integrating-the-sdk-into-a-mobile-application).

1. 在Adobe行動服務介面中定義地標。 另請參閱 [在Adobe Mobile Services中定義地標](#defining-points-of-interest-in-adobe-mobile-services).
1. 定義您要從行動應用程式訂閱者收集的資料。 另請參閱 [收集訂閱者的興趣點資料](#collecting-subscribers--points-of-interest-data).
1. 請務必存取行動應用程式和在Adobe Campaign中收集的位置資料。 另請參閱 [存取用來收集位置資料的行動應用程式](#accessing-mobile-apps-used-to-collect-location-data) 和 [存取收集的位置資料](#accessing-collected-location-data).

### 使用SDK V4在Adobe Campaign中設定行動應用程式 {#setting-up-a-mobile-app-in-campaign}

若要能夠使用Adobe Campaign收集地標資料，您必須設定Adobe Campaign將接收其資料的行動應用程式。

1. 按一下 **Adobe** 標誌，在左上角，然後選取 **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app]**.
1. 按一下 **[!UICONTROL Create]** 以設定應用程式。
1. 輸入名稱，在 **[!UICONTROL Application name]** 欄位並按一下 **[!UICONTROL Create]**.

   請勿填寫 **[!UICONTROL Device-specific settings]** 區段。 這僅適用於設定接收推播通知的應用程式。

在 **[!UICONTROL Mobile application properties]** 區段中，列出兩個URL： **[!UICONTROL Collect PII endpoint]** 和 **[!UICONTROL Location Services endpoint]**. 這些設定檔將用於Adobe Mobile Services介面。 另請參閱 [在Adobe Mobile Services中設定行動應用程式](#configuring-a-mobile-app-in-adobe-mobile-services).

* 此 **[!UICONTROL Collect PII endpoint]** URL是用來在啟動時從行動應用程式收集使用者的Experience CloudID和註冊權杖。 當使用者使用憑證（例如電子郵件、名字、姓氏等）登入應用程式時，也會收集此資料並用於協調使用者的註冊權杖與Adobe Campaign設定檔。
* 此 **[!UICONTROL Location Services endpoint]** URL可用來收集位置資料，例如使用者從地標的經緯度和半徑。

您現在可以在Adobe Mobile Services中使用這些值來完成設定，如 [在Adobe Mobile Services中設定行動應用程式](#configuring-a-mobile-app-in-adobe-mobile-services) 區段。

![](assets/poi_mobile_app_properties.png)

### 在Adobe Mobile Services中設定V4行動應用程式 {#configuring-a-mobile-app-in-adobe-mobile-services}

若要將Adobe Mobile Services收集的資料傳送至Adobe Campaign，您必須在Mobile Services介面中設定回傳。

您需要特定資訊，以便在Adobe Campaign中設定的行動應用程式引數中找到(請參閱 [在Campaign中設定行動應用程式](#setting-up-a-mobile-app-in-campaign))：

* **[!UICONTROL IMS Organization ID]**
* **[!UICONTROL Collect PII Endpoint]**
* **[!UICONTROL Location Services endpoint]**

您必須擁有Adobe Analytics的存取權才能進行下列設定。 如果您不是Adobe Analytics使用者，請聯絡Adobe Campaign管理員。

1. 登入 [mobilemarketing.adobe.com](https://mobilemarketing.adobe.com/).
1. 建立應用程式或選取現有的應用程式。
1. 前往 **[!UICONTROL Manage App Settings]** 頁面。
1. 在 **訪客ID服務** 部分，檢查 **啟用** 並從下拉式清單中選取您的組織。 按一下「**儲存**」。

   >[!CAUTION]
   >
   >此組織必須與您在Adobe Campaign執行個體上使用的組織相同。

1. 按一下&#x200B;**[!UICONTROL Manage Postbacks]**。
1. 建立回傳。

   * 選取 **[!UICONTROL PII]** 作為 **[!UICONTROL Postback Type]**.
   * 在 **[!UICONTROL URL]** 欄位，複製 **[!UICONTROL Collect PII Endpoint]** 您在Adobe Campaign介面中設定的行動應用程式URL，前面有伺服器名稱。 另請參閱 [在Campaign中設定行動應用程式](#setting-up-a-mobile-app-in-campaign).
   * 填入 **[!UICONTROL Post Body]** 欄位如下：

     若為iOS：

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

     若為Android：

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

   * 設定 **內容型別** 作為 **[!UICONTROL application/json]**.
   * 在 **哪些資料標籤會觸發回傳？**，選取任何事件，通常會 **[!UICONTROL Launched]** 和 **[!UICONTROL exists]**.
   * 按一下&#x200B;**[!UICONTROL Save & Activate]**。

1. 建立第二個回傳。

   * 選取 **[!UICONTROL Postback]** 作為 **[!UICONTROL Postback Type]**.
   * 在 **[!UICONTROL URL]** 欄位，複製 **[!UICONTROL Location Services Endpoint]** 您在Adobe Campaign介面中設定的行動應用程式URL，前面有伺服器名稱。 另請參閱 [在Campaign中設定行動應用程式](#setting-up-a-mobile-app-in-campaign).
   * 填入 **[!UICONTROL Post Body]** 欄位如下：

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

   * 設定 **內容型別** 作為 **[!UICONTROL application/json]**.
   * 在 **哪些資料標籤會觸發回傳？**，選取 **[!UICONTROL campaign.test]** 和 **[!UICONTROL exists]**.
   * 按一下&#x200B;**[!UICONTROL Save & Activate]**。

>[!NOTE]
>
>如需設定回傳的詳細資訊，請參閱 [Adobe Mobile Services檔案](https://experienceleague.adobe.com/docs/mobile-services/using/manage-app-settings-ug/configuring-app/signals.html).

### 將SDK整合至行動應用程式 {#integrating-the-sdk-into-a-mobile-application}

行動核心服務的軟體開發套件(SDK)有助於將行動應用程式整合到Adobe Campaign中。

此步驟的說明如下 [頁面](https://helpx.adobe.com/tw/campaign/kb/configuring-app-sdkv4.html).

### 在Adobe Mobile Services中定義地標 {#defining-points-of-interest-in-adobe-mobile-services}

若要定義用來收集位置資料的地標，請執行下列動作：

1. 前往AdobeMobile Services介面。
1. 新增您的應用程式。

   如需在行動服務中管理應用程式的詳細資訊，請參閱 [Adobe Mobile Services檔案](https://experienceleague.adobe.com/docs/mobile-services/using/manage-apps-ug/t-new-app.html).

1. 定義地標。

   如需管理地標的詳細資訊，請參閱 [Adobe Mobile Services檔案](https://experienceleague.adobe.com/docs/mobile-services/using/location-ug/t-manage-points.html).

### 收集訂閱者的興趣點資料 {#collecting-subscribers--points-of-interest-data}

特定自訂資源可讓您定義要從應用程式訂閱者收集的資料。

此步驟的說明請參閱 [使用SDK V4設定行動應用程式](https://helpx.adobe.com/tw/campaign/kb/configuring-app-sdkv4.html) 頁面。

## 存取用來收集位置資料的行動應用程式 {#accessing-mobile-apps-used-to-collect-location-data}

若要存取Adobe Campaign中成功建立的應用程式：

1. 按一下 **Adobe** 標誌，位於左上角。
1. 選取 **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (SDK v4)]** 或 **[!UICONTROL Mobile app (AEP SDK)]** 取決於SDK。
1. 從清單中選取行動應用程式以顯示其屬性。

   ![](assets/poi_mobile_app_subscribers.png)

應用程式的訂閱者清單也會顯示在 **[!UICONTROL Mobile application subscribers]** 標籤。 訂閱者是指將應用程式安裝在行動裝置上的所有使用者。 Adobe Campaign資料庫設定檔會以註冊Token識別。

## 存取收集的位置資料 {#accessing-collected-location-data}

完成設定後，收集的「地標」資料會列在 **[!UICONTROL Places]** 個設定檔的索引標籤。 若要存取清單：

1. 選取設定檔。
1. 按一下 **[!UICONTROL Edit profile properties]** 按鈕。
1. 選取 **[!UICONTROL Places]** 索引標籤。

   ![](assets/poi_profile_places.png)

系統會列出目前設定檔收集的「興趣點」資料。 位置資料會儲存在Adobe Campaign資料庫六個月。

如需存取和編輯設定檔的詳細資訊，請參閱 [設定檔](../../audiences/using/about-profiles.md).
