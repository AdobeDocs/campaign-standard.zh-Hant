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
source-git-commit: 6b683ccd93e10f78ff643eed9f374a794c085cb1
workflow-type: tm+mt
source-wordcount: '1252'
ht-degree: 1%

---

# 設定 Campaign-Points of Interest 資料整合{#configuring-campaign-points-of-interest-data-integration}

## 使用Adobe Experience Platform SDK設定Campaign-Points of Interest資料整合 {#configuring-campaign-poi-aep-sdk}

>[!NOTE]
>
>您的行動應用程式應已透過Adobe Experience Platform SDK在Adobe Campaign Standard中設定。 如需詳細步驟，請參閱此[頁面](https://helpx.adobe.com/tw/campaign/kb/configuring-app-sdk.html)。

用來收集位置資料的行動應用程式必須由&#x200B;**管理員**&#x200B;在Adobe Campaign介面中設定。

若要將Adobe Experience Platform Location Services與已設定Adobe Experience Platform SDK的行動應用程式搭配使用，您需要：

1. 在資料收集UI中，將&#x200B;**[!UICONTROL Places]**&#x200B;擴充功能新增至您的行動應用程式設定。 在Adobe Campaign中設定行動應用程式。 請參閱[安裝Places擴充功能](https://developer.adobe.com/client-sdks/solution/places)。

1. 擴充功能設定完成後，請在資料收集UI中建立資料元素，以從這些擴充功能擷取資料。 請參閱此[頁面](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Step1Createdataelements)以建立您的資料元素。

1. 然後，在資料收集UI中，您需要建立規則以支援Point of Interest和Adobe Campaign之間的行動使用案例。\
   當使用者進入地理圍欄式&#x200B;**[!UICONTROL Point of Interest]**&#x200B;時，將觸發此規則。 請參閱此[頁面](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Locationpostback)以建立您的規則。

1. 在地標中定義您的&#x200B;**[!UICONTROL Points of Interest]**。 請參閱[建立地標](https://experienceleague.adobe.com/docs/places/using/poi-mgmt-ui/create-a-poi-ui.html)。

1. 請務必存取行動應用程式和在Adobe Campaign中收集的位置資料。 請參閱[存取用來收集位置資料的行動應用程式](#accessing-mobile-apps-used-to-collect-location-data)和[存取收集的位置資料](#accessing-collected-location-data)。

## 使用SDK V4設定Campaign-Points of Interest資料整合 {#configuring-campaign-poi-sdkv4}

用來收集位置資料的行動應用程式必須由&#x200B;**管理員**&#x200B;在Adobe Campaign介面中設定。

若要將Point of Interest資料功能用於以SDK V4設定的行動應用程式，您需要：

1. 存取適用於行動裝置的Adobe Analytics。 請檢視授權合約，或聯絡Adobe客戶經理以取得詳細資訊。
1. 在Adobe Campaign中設定行動應用程式。 請參閱[在Campaign](#setting-up-a-mobile-app-in-campaign)中設定行動應用程式。
1. 在Adobe Mobile Services介面中設定您的行動應用程式。 這可讓您確保Adobe Mobile Services收集的資料傳送至Adobe Campaign。 請參閱[在Adobe Mobile Services中設定行動應用程式](#configuring-a-mobile-app-in-adobe-mobile-services)。
1. 執行行動應用程式的特定設定：

   * 將從AdobeMobile Services介面下載的設定檔案與行動應用程式封裝。
   * 將Experience Cloud Mobile SDK整合至您的行動應用程式。 請參閱[將SDK整合至行動應用程式](#integrating-the-sdk-into-a-mobile-application)。

1. 在Adobe行動服務介面中定義地標。 請參閱[在Adobe行動服務中定義地標](#defining-points-of-interest-in-adobe-mobile-services)。
1. 定義您要從行動應用程式訂閱者收集的資料。 請參閱[收集訂閱者的興趣點資料](#collecting-subscribers--points-of-interest-data)。
1. 請務必存取行動應用程式和在Adobe Campaign中收集的位置資料。 請參閱[存取用來收集位置資料的行動應用程式](#accessing-mobile-apps-used-to-collect-location-data)和[存取收集的位置資料](#accessing-collected-location-data)。

### 使用SDK V4在Adobe Campaign中設定行動應用程式 {#setting-up-a-mobile-app-in-campaign}

若要能夠使用Adobe Campaign收集地標資料，您必須設定Adobe Campaign將接收其資料的行動應用程式。

1. 按一下左上角的&#x200B;**Adobe**&#x200B;標誌，然後選取&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app]**。
1. 按一下&#x200B;**[!UICONTROL Create]**&#x200B;以設定應用程式。
1. 在&#x200B;**[!UICONTROL Application name]**&#x200B;欄位中輸入名稱並按一下&#x200B;**[!UICONTROL Create]**。

   請勿填寫&#x200B;**[!UICONTROL Device-specific settings]**&#x200B;區段。 這僅適用於設定接收推播通知的應用程式。

在&#x200B;**[!UICONTROL Mobile application properties]**&#x200B;區段中列出兩個URL： **[!UICONTROL Collect PII endpoint]**&#x200B;和&#x200B;**[!UICONTROL Location Services endpoint]**。 這些設定檔將用於Adobe Mobile Services介面。 請參閱[在Adobe Mobile Services中設定行動應用程式](#configuring-a-mobile-app-in-adobe-mobile-services)。

* **[!UICONTROL Collect PII endpoint]** URL是用來在啟動時從行動應用程式收集使用者的Experience CloudID和註冊權杖。 當使用者使用憑證（例如電子郵件、名字、姓氏等）登入應用程式時，也會收集此資料並用於協調使用者的註冊權杖與Adobe Campaign設定檔。
* **[!UICONTROL Location Services endpoint]** URL是用來從地標收集位置資料，例如使用者的經緯度和半徑。

您現在可以在Adobe Mobile Services中使用這些值來完成設定，如[在Adobe Mobile Services中設定行動應用程式](#configuring-a-mobile-app-in-adobe-mobile-services)區段中所述。

![](assets/poi_mobile_app_properties.png)

### 在Adobe Mobile Services中設定V4行動應用程式 {#configuring-a-mobile-app-in-adobe-mobile-services}

若要將Adobe Mobile Services收集的資料傳送至Adobe Campaign，您必須在Mobile Services介面中設定回傳。

您需要特定資訊，以便在Adobe Campaign中設定的行動應用程式引數中找到（請參閱[在Campaign中設定行動應用程式](#setting-up-a-mobile-app-in-campaign)）：

* **[!UICONTROL IMS Organization ID]**
* **[!UICONTROL Collect PII Endpoint]**
* **[!UICONTROL Location Services endpoint]**

您必須擁有Adobe Analytics的存取權才能進行下列設定。 如果您不是Adobe Analytics使用者，請聯絡Adobe Campaign管理員。

1. 登入[mobilemarketing.adobe.com](https://mobilemarketing.adobe.com/)。
1. 建立應用程式或選取現有的應用程式。
1. 前往&#x200B;**[!UICONTROL Manage App Settings]**&#x200B;頁面。
1. 在&#x200B;**訪客ID服務**&#x200B;區段中，勾選&#x200B;**啟用**，並從下拉式清單中選取您的組織。 按一下「**儲存**」。

   >[!CAUTION]
   >
   >此組織必須與您在Adobe Campaign執行個體上使用的組織相同。

1. 按一下&#x200B;**[!UICONTROL Manage Postbacks]**。
1. 建立回傳。

   * 選取&#x200B;**[!UICONTROL PII]**&#x200B;做為&#x200B;**[!UICONTROL Postback Type]**。
   * 在&#x200B;**[!UICONTROL URL]**&#x200B;欄位中，從您在Adobe Campaign介面中設定的行動應用程式複製&#x200B;**[!UICONTROL Collect PII Endpoint]** URL，並在前面加上伺服器名稱。 請參閱[在Campaign](#setting-up-a-mobile-app-in-campaign)中設定行動應用程式。
   * 請依照下列方式填寫&#x200B;**[!UICONTROL Post Body]**&#x200B;欄位：

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

   * 將&#x200B;**內容型別**&#x200B;設定為&#x200B;**[!UICONTROL application/json]**。
   * 在&#x200B;**中，哪些資料標籤會觸發回傳？**，選取任何事件，通常是&#x200B;**[!UICONTROL Launched]**&#x200B;和&#x200B;**[!UICONTROL exists]**。
   * 按一下&#x200B;**[!UICONTROL Save & Activate]**。

1. 建立第二個回傳。

   * 選取&#x200B;**[!UICONTROL Postback]**&#x200B;做為&#x200B;**[!UICONTROL Postback Type]**。
   * 在&#x200B;**[!UICONTROL URL]**&#x200B;欄位中，從您在Adobe Campaign介面中設定的行動應用程式複製&#x200B;**[!UICONTROL Location Services Endpoint]** URL，並在前面加上伺服器名稱。 請參閱[在Campaign](#setting-up-a-mobile-app-in-campaign)中設定行動應用程式。
   * 請依照下列方式填寫&#x200B;**[!UICONTROL Post Body]**&#x200B;欄位：

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

   * 將&#x200B;**內容型別**&#x200B;設定為&#x200B;**[!UICONTROL application/json]**。
   * 在&#x200B;**中，哪些資料標籤會觸發回傳？**，選取&#x200B;**[!UICONTROL campaign.test]**&#x200B;和&#x200B;**[!UICONTROL exists]**。
   * 按一下&#x200B;**[!UICONTROL Save & Activate]**。

>[!NOTE]
>
>如需設定回傳的詳細資訊，請參閱[AdobeMobile Services檔案](https://experienceleague.adobe.com/docs/mobile-services/using/manage-app-settings-ug/configuring-app/signals.html)。

### 將SDK整合至行動應用程式 {#integrating-the-sdk-into-a-mobile-application}

行動核心服務的軟體開發套件(SDK)有助於將行動應用程式整合到Adobe Campaign中。

此[頁面](https://helpx.adobe.com/tw/campaign/kb/configuring-app-sdkv4.html)中說明此步驟。

### 在Adobe Mobile Services中定義地標 {#defining-points-of-interest-in-adobe-mobile-services}

若要定義用來收集位置資料的地標，請執行下列動作：

1. 前往AdobeMobile Services介面。
1. 新增您的應用程式。

   如需在Mobile Services中管理應用程式的詳細資訊，請參閱[AdobeMobile Services檔案](https://experienceleague.adobe.com/docs/mobile-services/using/manage-apps-ug/t-new-app.html)。

1. 定義地標。

   如需管理地標的詳細資訊，請參閱[Adobe行動服務檔案](https://experienceleague.adobe.com/docs/mobile-services/using/location-ug/t-manage-points.html)。

### 收集訂閱者的興趣點資料 {#collecting-subscribers--points-of-interest-data}

特定自訂資源可讓您定義要從應用程式訂閱者收集的資料。

此步驟在[使用SDK V4](https://helpx.adobe.com/tw/campaign/kb/configuring-app-sdkv4.html)設定行動應用程式頁面中說明。

## 存取用來收集位置資料的行動應用程式 {#accessing-mobile-apps-used-to-collect-location-data}

若要存取Adobe Campaign中成功建立的應用程式：

1. 按一下左上角的&#x200B;**Adobe**&#x200B;標誌。
1. 根據SDK選取&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (SDK v4)]**&#x200B;或&#x200B;**[!UICONTROL Mobile app (AEP SDK)]**。
1. 從清單中選取行動應用程式以顯示其屬性。

   ![](assets/poi_mobile_app_subscribers.png)

應用程式的訂閱者清單也會顯示在&#x200B;**[!UICONTROL Mobile application subscribers]**&#x200B;索引標籤中。 訂閱者是指將應用程式安裝在行動裝置上的所有使用者。 Adobe Campaign資料庫設定檔會以註冊Token識別。

## 存取收集的位置資料 {#accessing-collected-location-data}

完成設定後，收集的地標資料會列在每個設定檔的&#x200B;**[!UICONTROL Places]**&#x200B;標籤中。 若要存取清單：

1. 選取設定檔。
1. 按一下右側的&#x200B;**[!UICONTROL Edit profile properties]**&#x200B;按鈕。
1. 選取 **[!UICONTROL Places]** 索引標籤。

   ![](assets/poi_profile_places.png)

系統會列出目前設定檔收集的「興趣點」資料。 位置資料會儲存在Adobe Campaign資料庫六個月。

如需存取及編輯設定檔的詳細資訊，請參閱[設定檔](../../audiences/using/about-profiles.md)。
