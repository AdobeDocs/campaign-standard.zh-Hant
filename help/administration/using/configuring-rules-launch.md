---
title: 設定標籤規則以支援 Adobe Campaign Standard 使用案例
description: 瞭解如何設定標籤規則以支援Adobe Campaign Standard使用案例
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
feature: Instance Settings
role: Admin
level: Experienced
exl-id: b5f4f612-ea23-4007-b427-069777ecdd58
source-git-commit: 597ece8d833a216f0540f801461b08fdc9865024
workflow-type: tm+mt
source-wordcount: '983'
ht-degree: 2%

---

# 設定標籤規則以支援 Adobe Campaign Standard 使用案例 {#configuring-rules-launch}

在資料收集UI中，建立資料元素和規則，以將PII和其他資料從行動應用程式傳送至 [!DNL Adobe Campaign Standard].

為確保資料收集UI中的所有設定變更生效，您必須發佈這些變更。 如需詳細資訊，請參閱 [發佈](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/#publish-the-configuration).

若要在資料收集UI中建立規則，請遵循下列步驟：

1. [建立資料元素](../../administration/using/configuring-rules-launch.md#create-data-elements)
2. [建立規則](../../administration/using/configuring-rules-launch.md#create-data-elements) 若您想要支援的使用案例：
   * [PII回傳](../../administration/using/configuring-rules-launch.md#pii-postback)
   * [應用程式內追蹤回傳](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback)
   * [推播通知追蹤回傳](../../administration/using/configuring-rules-launch.md#push-tracking-postback)
   * [位置回傳](../../administration/using/configuring-rules-launch.md#location-postback)

## 建立資料元素 {#create-data-elements}

以下是建議您在資料收集UI中建立的資料元素。
您可以視需要建立其他資料元素。

* **[!UICONTROL Experience Cloud ID]**
* **[!UICONTROL Pkey]**
* **[!UICONTROL Campaign server]**

若要建立這些資料元素：

1. 在資料收集UI中，從您的行動應用程式控制面板，按一下 **[!UICONTROL Data Elements]** 標籤。

1. 若要建立 **[!UICONTROL Experience Cloud ID]** 資料元素，按一下 **[!UICONTROL Create New Data Element]**.

1. 在 **[!UICONTROL Name]** 欄位，例如，輸入 **mcid**.

1. 從 **[!UICONTROL Extension]** 下拉式清單，選取 **[!UICONTROL Mobile Core]**. 則 **[!UICONTROL Experience Cloud ID]** 在 **[!UICONTROL Data element]** 型別下拉式清單。

   ![](assets/do-not-localize/rules_1.png)

1. 若要建立索引鍵資料元素，請按一下 **[!UICONTROL Add data element]**.

1. 在 **[!UICONTROL Name]** 欄位，例如，輸入 **pkey**.

1. 從 **[!UICONTROL Extension]** 下拉式清單，選取 **[!UICONTROL Adobe Campaign Standard]**. 則 **[!UICONTROL pkey]** 在 **[!UICONTROL Data element]** 型別下拉式清單。

1. 若要建立Campaign伺服器資料元素，請按一下 **[!UICONTROL Add data element]**.

1. 在 **[!UICONTROL Name]** 欄位，輸入名稱，例如， **camp-server**.

1. 從 **[!UICONTROL Extension]** 下拉式清單，選取 **[!UICONTROL Adobe Campaign Standard]**. 然後 **[!UICONTROL Campaign Server]** 在 **[!UICONTROL Data element]** 型別下拉式清單。

## 建立規則 {#creating-rules}

您必須針對下列專案建立規則：

* [PII回傳](../../administration/using/configuring-rules-launch.md#pii-postback)
* [應用程式內追蹤回傳](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback)
* [推播通知追蹤回傳](../../administration/using/configuring-rules-launch.md#push-tracking-postback)
* [位置回傳](../../administration/using/configuring-rules-launch.md#location-postback)

### PII回傳 {#pii-postback}

>[!NOTE]
>
>若要從行動應用程式傳送PII資訊至Adobe Campaign，您必須實作SDK API。 如需詳細資訊，請前往 [CollectPII](https://developer.adobe.com/client-sdks/documentation/mobile-core/api-reference/#collectpii).

傳送PII資料給 [!DNL Adobe Campaign Standard]，在資料收集UI中建立規則：

1. 在資料收集UI中，從您的行動應用程式控制面板，按一下 **[!UICONTROL Rules]** 按Tab鍵然後 **[!UICONTROL Create New Rule]**.

1. 輸入名稱，例如， **行動核心 — 收集PII**.

1. 在 **[!UICONTROL Events]** 區段，按一下 **[!UICONTROL Add]**.

1. 從 **[!UICONTROL Extension]** 下拉式清單，選取 **[!UICONTROL Mobile Core]**. 然後 **[!UICONTROL Collect PII]** 在 **[!UICONTROL Event type]** 下拉式清單。

1. 按一下&#x200B;**[!UICONTROL Keep changes]**。

1. 在 **[!UICONTROL Actions]** 區段，按一下 **[!UICONTROL Add]**.

1. 從 **[!UICONTROL Extension]** 下拉式清單，選取 **[!UICONTROL Mobile Core]**. 然後 **[!UICONTROL Send PII]** 在 **[!UICONTROL Action type]** 下拉式清單。

1. 在 **[!UICONTROL URL]**，輸入下列URL：

   ```
   https://{%%camp-server%%}/rest/head/mobileAppV5/{%%pkey%%}/subscriptions/{%%mcid%%}
   ```

1. 選取 **[!UICONTROL Add Post Body]** 核取方塊。

1. 在 **[!UICONTROL Post Body]**，輸入下列內容：

   ```
   {
   "marketingCloudId":
   "{%%mcid%%}",
   "pushPlatform":
   "{%contextdata.pushPlatform%}",
   "cusEmail":
   "{%contextdata.email%}",
   "cusFirstName":
   "{%contextdata.firstName%}",
   "cusLastName":
   "{%contextdata.lastName%}" }
   ```

   marketingCloudId可讓您調解應用程式訂閱者與資料庫中的收件者，因此是必要專案。 您可以根據業務需求指定其他索引鍵值配對。 在上述範例中，電子郵件、名字和姓氏是從應用程式傳遞。

   金鑰（例如cusEmail、cusFirstName和cusLastName）應符合Adobe Campaign Standard執行個體的自訂資源中所定義的欄位ID。 值變數（例如電子郵件、firstName和LastName）應與從應用程式程式碼呼叫AMS collectPII API時，從行動應用程式傳送的JSON資料中的金鑰相符。

   您也可以在「收集PII」回傳或不同的回傳中傳遞生命週期資料（視您的事件觸發程式而定）。 以下是生命週期資料JSON的範例：

   ```
   {
   "marketingCloudId":"{%%mcid%%}",
   "pushPlatform":"{%contextdata.pushPlatform%}",
   "cusDayslastlaunch": "{%%DaysSinceLastUse%%}", 
   "cusDaysfirstlaunch": "{%%DaysSinceFirstUse%%}", 
   "cusLaunches": "{%%Launches%%}"
   }
   ```

   例如，在資料收集UI中定義的資料元素應以雙百分比括住 `%%mcid%%`、和應用程式中的內容變數應以單一百分比括住，例如%contextdata.email%。

1. 在 **[!UICONTROL Content Type]**，型別 **application/json**.

1. 在 **[!UICONTROL Timeout]**，選取0。

   ![](assets/do-not-localize/rules_2.png)

您的使用者資料現在已設定為傳送至Campaign。

### 應用程式內追蹤回傳 {#inapp-tracking-postback}

>[!NOTE]
>
>如果您使用Android ACPCore v1.4.0或更新版本/ iOS ACPCore v2.3.0或更新版本，則不需要設定追蹤回傳。

若要傳送追蹤資料至 [!DNL Adobe Campaign Standard] 若要報告使用者在您的行動應用程式中與應用程式內訊息的互動方式，請在資料收集UI中建立下列規則：

1. 在資料收集UI中，從您的行動應用程式儀表板中，選取 **[!UICONTROL Rules]** 標籤並按一下 **[!UICONTROL Add Rule]**.

1. 輸入名稱，例如， **Adobe Campaign — 應用程式內點選追蹤**.

1. 在 **[!UICONTROL Events]** 區段，按一下 **[!UICONTROL Add]**.

1. 從 **[!UICONTROL Extension]** 下拉式清單，選取 **[!UICONTROL Adobe Campaign Standard]**. 然後 **[!UICONTROL In-App click tracking]** 在 **[!UICONTROL Event type]** 下拉式清單。

1. 按一下&#x200B;**[!UICONTROL Keep changes]**。

1. 在 **[!UICONTROL Actions]** 區段，按一下 **[!UICONTROL Add]**.

1. 從 **[!UICONTROL Extension]** 下拉式清單，選取 **[!UICONTROL Mobile Core]**. 然後 **[!UICONTROL Send postback]** 在 **[!UICONTROL Event type]** 下拉式清單。

1. 在 **[!UICONTROL URL]**，輸入下列URL：

   ```
   https://{%%camp-server%%}/r/?id={%id%}&mcid={%%mcid%%}
   ```

1. 選取 **[!UICONTROL Add post body]** 核取方塊。

1. 在 **[!UICONTROL Post Body]**，型別 **{}**.

1. 在 **[!UICONTROL Content Type]**，型別 **application/json**.

1. 在 **[!UICONTROL Timeout]**，選取0。

   ![](assets/do-not-localize/rules_3.png)

### 推播通知追蹤回傳 {#push-tracking-postback}

>[!NOTE]
>
>如果您使用Android ACPCore v1.4.0或更新版本/ iOS ACPCore v2.3.0或更新版本，則不需要設定追蹤回傳。

若要傳送追蹤資料至 [!DNL Adobe Campaign Standard]，以協助追蹤推播通知傳遞內容，以及使用者與行動應用程式的互動，您必須在資料收集UI中建立規則。

如需推播追蹤的詳細資訊，請參閱 [推播追蹤](../../administration/using/push-tracking.md).

若要追蹤應用程式動作，請使用trackAction API。 如需詳細資訊，請參閱 [追蹤應用程式動作](https://app.gitbook.com/@aep-sdks/s/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#track-app-actions).

1. 在資料收集UI中，從您的行動應用程式控制面板，按一下 **[!UICONTROL Rules]** 標籤並按一下 **[!UICONTROL Add Rule]**.

1. 輸入名稱，例如， **Adobe Campaign — 推送點選追蹤**.

1. 在 **[!UICONTROL Events]** 區段，按一下 **[!UICONTROL Add]**.

1. 從 **[!UICONTROL Extension]** 下拉式清單，選取 **[!UICONTROL Mobile Core]**. 然後 **[!UICONTROL Track Action]** 在 **[!UICONTROL Event type]** 下拉式清單。

1. 從 **[!UICONTROL Action]** 下拉式清單，選取 **[!UICONTROL Action]**，選取 **[!UICONTROL equals]**，和型別 **追蹤**.

1. 按一下 **[!UICONTROL Keep changes]**。然後，在 **[!UICONTROL Actions]** 區段，按一下 **[!UICONTROL Add]**.

1. 從 **[!UICONTROL Extension]** 下拉式清單，選取 **[!UICONTROL Mobile Core]**. 然後 **[!UICONTROL Send postback]** 在 **[!UICONTROL Action type]** 下拉式清單。

1. 在 **[!UICONTROL URL]**，輸入下列URL：

   ```
   https://{%%camp-server%%}/r/?id={%contextdata.broadlogId%},{%contextdata.deliveryId%},{%contextdata.action%}&mcId={%%mcid%%}
   ```

1. 選取 **[!UICONTROL Add post body]** 核取方塊。

1. 新增您的貼文內文，例如{ }。

1. 在 **[!UICONTROL Content Type]**，型別 **application/json**.

1. 在 **[!UICONTROL Timeout]**，選取0。

### 位置回傳 {#location-postback}

1. 在資料收集UI中，從您的行動應用程式控制面板，按一下 **[!UICONTROL Rules]** 標籤並按一下 **[!UICONTROL Add Rule]**.

1. 輸入名稱，例如， **位置回傳**.

1. 在 **[!UICONTROL Events]** 區段，按一下 **[!UICONTROL Add]**.

1. 建立事件，例如，輸入POI或退出POI。 從 **[!UICONTROL Extension]** 下拉式清單，選取 **地點 — Beta版**. 然後 **輸入POI** 或 **退出POI** 在 **[!UICONTROL Event type]** 下拉式清單。

1. 輸入名稱，例如 **地點 — 測試版 — 輸入POI** 或 **退出POI**.

1. 在 **[!UICONTROL Actions]** 區段，按一下 **[!UICONTROL Add]**.

1. 從 **[!UICONTROL Extension]** 下拉式清單，選取 **[!UICONTROL Mobile Core]**. 然後 **[!UICONTROL Send postback]** 從 **[!UICONTROL Action type]** 下拉式清單。

1. 輸入名稱，例如 **行動核心 — 傳送位置回傳**.

1. 在 **[!UICONTROL URL]**，輸入下列URL：

   ```
   https://{%%camp-server%%}/rest/head/mobileAppV5/{%%pkey%%}/locations/
   ```

1. 選取 **[!UICONTROL Add post body]** 核取方塊並新增您的貼文內文，例如：

   ```
   {
   "locationData": {
       "distances": "{%%Distance%%}",
       "poiLabel": "{%%POILabel%%}",
       "latitude": "{%%Latitude%%}",
       "longitude": "{%%Longitude%%}",
       "appId": "{%%AppId%%}",
       "marketingCloudId": "{%%ECID%%}"
   }
   }
   ```

   >[!NOTE]
   >
   >在上述範例中，您必須運用中的步驟，在資料收集UI中設定右側的資料元素 [建立資料元素](../../administration/using/configuring-rules-launch.md#create-data-elements). 支援左側的資料元素 [!DNL Adobe Campaign Standard] 而且不需要任何設定。 如果您需要其他資料，您必須在中執行自訂資源擴充功能 [!DNL Adobe Campaign Standard].

1. 在 **[!UICONTROL Content Type]**，型別 **application/json**.

1. 在 **[!UICONTROL Timeout]**，選取5。

   ![](assets/do-not-localize/rules_4.png)
