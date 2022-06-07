---
title: 設定 Campaign-Points of Interest 資料整合
description: 瞭解如何配置Adobe Campaign的興趣點資料功能，以根據訂閱者的位置發送個性化消息。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics-for-mobile
feature: Audiences
role: Data Architect
level: Intermediate
exl-id: b097b3fa-f949-446e-ad44-cc6ca025ee55
source-git-commit: 7767b39a48502f97e2b3af9d21a3f49b9283ab2e
workflow-type: tm+mt
source-wordcount: '1327'
ht-degree: 2%

---

# 設定 Campaign-Points of Interest 資料整合{#configuring-campaign-points-of-interest-data-integration}

## 配置與Adobe Experience PlatformSDK的活動點資料整合 {#configuring-campaign-poi-aep-sdk}

>[!NOTE]
>
>您的移動應用程式應已在Adobe Campaign Standard使用Adobe Experience PlatformSDK進行配置。 有關詳細步驟，請參閱 [頁](https://helpx.adobe.com/tw/campaign/kb/configuring-app-sdk.html)。

用於收集位置資料的移動應用程式必須由 **管理員** 在Adobe Campaign介面。

要能夠將Adobe Experience Platform位置服務與配置有Adobe Experience PlatformSDK的移動應用程式配合使用，您需要：

1. 添加 **[!UICONTROL Places]** 和 **[!UICONTROL Places Monitor]** 資料收集UI中移動應用配置的擴展。 在Adobe Campaign設定移動應用程式。 請參閱 [安裝Places擴展](https://experienceleague.adobe.com/docs/places/using/places-ext-aep-sdks/places-extension/places-extension.html#install-the-places-extension-in-adobe-experience-platform-launch) 和 [安裝Places Monitor擴展](https://experienceleague.adobe.com/docs/places/using/places-ext-aep-sdks/places-monitor-extension/using-places-monitor-extension.html#install-the-places-monitor-extension-in-experience-platform-launch)。

1. 設定擴展後，在資料收集UI中建立資料元素以從這些擴展中檢索資料。 請參閱此 [頁](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Step1Createdataelements) 建立資料元素。

1. 然後，在資料收集UI中，您需要建立規則來支援興趣點和Adobe Campaign之間的移動使用案例。\
   當用戶進入隔離網時，將觸發此規則 **[!UICONTROL Point of Interest]**。 請參閱此 [頁](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Locationpostback) 建立規則。

1. 定義 **[!UICONTROL Points of Interest]** 的下界。 請參閱 [建立興趣點](https://experienceleague.adobe.com/docs/places/using/poi-mgmt-ui/create-a-poi-ui.html)。

1. 確保您訪問移動應用程式和在Adobe Campaign收集的位置資料。 請參閱 [訪問用於收集位置資料的移動應用](#accessing-mobile-apps-used-to-collect-location-data) 和 [訪問收集的位置資料](#accessing-collected-location-data)。

## 使用SDK V4配置活動興趣點資料整合 {#configuring-campaign-poi-sdkv4}

用於收集位置資料的移動應用程式必須由 **管理員** 在Adobe Campaign介面。

要將興趣點資料功能與配置了SDK V4的移動應用程式配合使用，您需要：

1. 可以訪問Mobile的Adobe Analytics。 檢查您的許可協定，或與Adobe帳戶主管聯繫以瞭解更多資訊。
1. 在Adobe Campaign設定移動應用程式。 請參閱 [在市場活動中設定移動應用](#setting-up-a-mobile-app-in-campaign)。
1. 在Adobe移動服務介面中設定移動應用程式。 這使您能夠確保通過Adobe移動服務收集的資料被發送到Adobe Campaign。 請參閱 [在Adobe移動服務中配置移動應用](#configuring-a-mobile-app-in-adobe-mobile-services)。
1. 執行移動應用程式的特定設定：

   * 將從Adobe移動服務介面下載的配置檔案與移動應用程式打包。
   * 將Experience Cloud移動SDK整合到您的移動應用程式中。 請參閱 [將SDK整合到移動應用程式](#integrating-the-sdk-into-a-mobile-application)。

1. 在Adobe移動服務介面中定義興趣點。 請參閱 [定義Adobe移動服務的興趣點](#defining-points-of-interest-in-adobe-mobile-services)。
1. 定義要從移動應用程式的訂戶收集的資料。 請參閱 [收集用戶興趣點資料](#collecting-subscribers--points-of-interest-data)。
1. 確保您訪問移動應用程式和在Adobe Campaign收集的位置資料。 請參閱 [訪問用於收集位置資料的移動應用](#accessing-mobile-apps-used-to-collect-location-data) 和 [訪問收集的位置資料](#accessing-collected-location-data)。

### 使用SDK V4在Adobe Campaign設定移動應用 {#setting-up-a-mobile-app-in-campaign}

要能夠與Adobe Campaign收集興趣點資料，必須配置Adobe Campaign將從中接收資料的移動應用程式。

1. 按一下 **Adobe** 徽標，在左上角，然後選擇 **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app]**。
1. 按一下 **[!UICONTROL Create]** 來設定應用程式。
1. 在 **[!UICONTROL Application name]** 按一下 **[!UICONTROL Create]**。

   不要填寫 **[!UICONTROL Device-specific settings]** 的子菜單。 這僅適用於配置接收推送通知的應用程式。

在 **[!UICONTROL Mobile application properties]** 列出兩個URL: **[!UICONTROL Collect PII endpoint]** 和 **[!UICONTROL Location Services endpoint]**。 它們將用於Adobe移動服務介面。 請參閱 [在Adobe移動服務中配置移動應用](#configuring-a-mobile-app-in-adobe-mobile-services)。

* 的 **[!UICONTROL Collect PII endpoint]** URL用於在移動應用程式啟動時從其收集用戶的Experience CloudID和註冊令牌。 當用戶使用諸如電子郵件、名字、姓氏等憑據登錄到應用程式時，還收集這些資料，並用於調節用戶的註冊令牌與Adobe Campaign配置檔案。
* 的 **[!UICONTROL Location Services endpoint]** URL用於從興趣點收集位置資料，如用戶的緯度、經度和半徑。

現在，您可以在Adobe移動服務中使用這些值來完成配置，如 [在Adobe移動服務中配置移動應用](#configuring-a-mobile-app-in-adobe-mobile-services) 的子菜單。

![](assets/poi_mobile_app_properties.png)

### 在Adobe移動服務中配置V4移動應用 {#configuring-a-mobile-app-in-adobe-mobile-services}

要將通過Adobe移動服務收集的資料發送到Adobe Campaign，必須在移動服務介面中配置回傳。

您需要在Adobe Campaign的移動應用程式參數集中找到的特定資訊(請參見 [在市場活動中設定移動應用](#setting-up-a-mobile-app-in-campaign)):

* **[!UICONTROL IMS Organization ID]**
* **[!UICONTROL Collect PII Endpoint]**
* **[!UICONTROL Location Services endpoint]**

您必須具有訪問Adobe Analytics的權限才能執行以下配置。 如果您不是Adobe Analytics用戶，請與Adobe Campaign管理員聯繫。

1. 登錄 [移動營銷.adobe.com](https://mobilemarketing.adobe.com/)。
1. 建立應用程式或選擇現有應用程式。
1. 轉到 **[!UICONTROL Manage App Settings]** 的子菜單。
1. 在 **訪問者ID服務** 選項 **啟用** 並從下拉清單中選擇您的組織。 按一下 **保存**。

   >[!CAUTION]
   >
   >此組織必須與您在Adobe Campaign實例上使用的組織相同。

1. 按一下&#x200B;**[!UICONTROL Manage Postbacks]**。
1. 建立回郵。

   * 選擇 **[!UICONTROL PII]** 的 **[!UICONTROL Postback Type]**。
   * 在 **[!UICONTROL URL]** ，複製 **[!UICONTROL Collect PII Endpoint]** 來自您在Adobe Campaign介面中配置的移動應用程式的URL，前面是伺服器名稱。 請參閱 [在市場活動中設定移動應用](#setting-up-a-mobile-app-in-campaign)。
   * 填寫 **[!UICONTROL Post Body]** 欄位：

      iOS:

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

   * 設定 **內容類型** 如 **[!UICONTROL application/json]**。
   * 在 **哪些資料標籤觸發後退？**，通常選擇任何事件 **[!UICONTROL Launched]** 和 **[!UICONTROL exists]**。
   * 按一下&#x200B;**[!UICONTROL Save & Activate]**。

1. 建立第二個後退。

   * 選擇 **[!UICONTROL Postback]** 的 **[!UICONTROL Postback Type]**。
   * 在 **[!UICONTROL URL]** ，複製 **[!UICONTROL Location Services Endpoint]** 來自您在Adobe Campaign介面中配置的移動應用程式的URL，前面是伺服器名稱。 請參閱 [在市場活動中設定移動應用](#setting-up-a-mobile-app-in-campaign)。
   * 填寫 **[!UICONTROL Post Body]** 欄位：

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

   * 設定 **內容類型** 如 **[!UICONTROL application/json]**。
   * 在 **哪些資料標籤觸發後退？**&#x200B;選中 **[!UICONTROL campaign.test]** 和 **[!UICONTROL exists]**。
   * 按一下&#x200B;**[!UICONTROL Save & Activate]**。

>[!NOTE]
>
>有關配置回郵的詳細資訊，請參閱 [Adobe移動服務文檔](https://experienceleague.adobe.com/docs/mobile-services/using/manage-app-settings-ug/configuring-app/signals.html)。

### 將SDK整合到移動應用程式 {#integrating-the-sdk-into-a-mobile-application}

移動核心服務的軟體開發工具包(SDK)有助於將移動應用程式整合到Adobe Campaign。

此步驟在中介紹 [頁](https://helpx.adobe.com/tw/campaign/kb/configuring-app-sdkv4.html)。

### 定義Adobe移動服務的興趣點 {#defining-points-of-interest-in-adobe-mobile-services}

要定義用於收集位置資料的興趣點，請執行以下操作：

1. 轉到Adobe移動服務介面。
1. 添加應用程式。

   有關在移動服務中管理應用程式的詳細資訊，請參閱 [Adobe移動服務文檔](https://experienceleague.adobe.com/docs/mobile-services/using/manage-apps-ug/t-new-app.html)。

1. 定義興趣點。

   有關管理興趣點的詳細資訊，請參閱 [Adobe移動服務文檔](https://experienceleague.adobe.com/docs/mobile-services/using/location-ug/t-manage-points.html)。

### 收集用戶興趣點資料 {#collecting-subscribers--points-of-interest-data}

通過特定的自定義資源，您可以定義要從應用程式訂閱者收集的資料。

此步驟在 [使用SDK V4配置移動應用程式](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html) 的子菜單。

## 訪問用於收集位置資料的移動應用 {#accessing-mobile-apps-used-to-collect-location-data}

要訪問在Adobe Campaign成功建立的應用程式：

1. 按一下 **Adobe** 徽標，位於左上角。
1. 選擇 **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (SDK v4)]** 或 **[!UICONTROL Mobile app (AEP SDK)]** 取決於SDK。
1. 從清單中選擇一個移動應用程式以顯示其屬性。

   ![](assets/poi_mobile_app_subscribers.png)

應用程式的訂戶清單也顯示在 **[!UICONTROL Mobile application subscribers]** 頁籤。 用戶是在其移動設備上安裝了該應用程式的所有用戶。 用註冊令牌標識Adobe Campaign資料庫簡檔。

## 訪問收集的位置資料 {#accessing-collected-location-data}

完成設定後，收集的興趣點資料將列在 **[!UICONTROL Places]** 頁籤。 要訪問清單：

1. 選擇配置檔案。
1. 按一下 **[!UICONTROL Edit profile properties]** 按鈕。
1. 選取 **[!UICONTROL Places]** 索引標籤。

   ![](assets/poi_profile_places.png)

列出當前配置檔案的收集的興趣點資料。 地點資料在Adobe Campaign資料庫中儲存6個月。

有關訪問和編輯配置檔案的詳細資訊，請參閱 [配置檔案](../../audiences/using/about-profiles.md)。
