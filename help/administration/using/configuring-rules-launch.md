---
title: 配置Adobe Experience Platform Launch規則以支援Adobe Campaign Standard使用案例
description: 瞭解如何配置Adobe Experience Platform Launch規則以支援Adobe Campaign Standard使用案例
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
feature: Instance Settings
role: Admin
level: Experienced
exl-id: b5f4f612-ea23-4007-b427-069777ecdd58
source-git-commit: bfba6b156d020e8d2656239e713d2d24625bda54
workflow-type: tm+mt
source-wordcount: '949'
ht-degree: 1%

---

# 設定啟動規則以支援 Adobe Campaign Standard 使用案例 {#configuring-rules-launch}

在 [!DNL Adobe Experience Platform Launch]，建立資料元素和規則，將PII和其他資料從移動應用程式發送到 [!DNL Adobe Campaign Standard]。

確保在 [!DNL Adobe Experience Platform Launch] 生效後，必須發佈這些更改。 有關詳細資訊，請參見 [發佈](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#publish-the-configuration)。

在中建立規則 [!DNL Experience Platform Launch]，請執行以下步驟：

1. [建立資料元素](../../administration/using/configuring-rules-launch.md#create-data-elements)
2. [建立規則](../../administration/using/configuring-rules-launch.md#create-data-elements) 對於要支援的使用情形：
   * [PII後退](../../administration/using/configuring-rules-launch.md#pii-postback)
   * [應用內跟蹤後退](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback)
   * [推送通知跟蹤後退](../../administration/using/configuring-rules-launch.md#push-tracking-postback)
   * [位置後退](../../administration/using/configuring-rules-launch.md#location-postback)

## 建立資料元素 {#create-data-elements}

下面是我們建議您在中建立的資料元素 [!DNL Experience Platform Launch]。
您可以根據需要建立其他資料元素。

* **[!UICONTROL Experience Cloud ID]**
* **[!UICONTROL Pkey]**
* **[!UICONTROL Campaign server]**

要建立這些資料元素：

1. 在 [!DNL Experience Platform Launch]，在您的移動應用程式儀表板中，按一下 **[!UICONTROL Data Elements]** 頁籤。

1. 建立 **[!UICONTROL Experience Cloud ID]** 資料元素，按一下 **[!UICONTROL Create New Data Element]**。

1. 在 **[!UICONTROL Name]** 欄位，例如鍵入 **密碼**。

1. 從 **[!UICONTROL Extension]** 下拉，選擇 **[!UICONTROL Mobile Core]**。 然後 **[!UICONTROL Experience Cloud ID]** 的 **[!UICONTROL Data element]** 下拉菜單。

   ![](assets/do-not-localize/rules_1.png)

1. 要建立Pkey資料元素，請按一下 **[!UICONTROL Add data element]**。

1. 在 **[!UICONTROL Name]** 欄位，例如鍵入 **按鍵**。

1. 從 **[!UICONTROL Extension]** 下拉，選擇 **[!UICONTROL Adobe Campaign Standard]**。 然後 **[!UICONTROL pkey]** 的 **[!UICONTROL Data element]** 下拉菜單。

1. 要建立市場活動伺服器資料元素，請按一下 **[!UICONTROL Add data element]**。

1. 在 **[!UICONTROL Name]** 欄位，鍵入名稱，例如， **營地伺服器**。

1. 從 **[!UICONTROL Extension]** 下拉，選擇 **[!UICONTROL Adobe Campaign Standard]**。 然後， **[!UICONTROL Campaign Server]** 的 **[!UICONTROL Data element]** 下拉菜單。

## 建立規則 {#creating-rules}

必須為以下項建立規則：

* [PII後退](../../administration/using/configuring-rules-launch.md#pii-postback)
* [應用內跟蹤後退](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback)
* [推送通知跟蹤後退](../../administration/using/configuring-rules-launch.md#push-tracking-postback)
* [位置後退](../../administration/using/configuring-rules-launch.md#location-postback)

### PII後退 {#pii-postback}

>[!NOTE]
>
>要將PII資訊從移動應用發送到Adobe Campaign，必須實現SDK API。 有關詳細資訊，請轉至 [收集PII](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#collect-pii)。

將PII資料發送到 [!DNL Adobe Campaign Standard]，在中建立規則 [!DNL Experience Platform Launch]:

1. 在 [!DNL Experience Platform Launch]，在您的移動應用程式儀表板中，按一下 **[!UICONTROL Rules]** 頁籤 **[!UICONTROL Create New Rule]**。

1. 鍵入名稱，例如， **移動核心 — 收集PII**。

1. 在 **[!UICONTROL Events]** ，按一下 **[!UICONTROL Add]**。

1. 從 **[!UICONTROL Extension]** 下拉，選擇 **[!UICONTROL Mobile Core]**。 然後， **[!UICONTROL Collect PII]** 的 **[!UICONTROL Event type]** 下拉。

1. 按一下&#x200B;**[!UICONTROL Keep changes]**。

1. 在 **[!UICONTROL Actions]** ，按一下 **[!UICONTROL Add]**。

1. 從 **[!UICONTROL Extension]** 下拉，選擇 **[!UICONTROL Mobile Core]**。 然後， **[!UICONTROL Send PII]** 的 **[!UICONTROL Action type]** 下拉。

1. 在 **[!UICONTROL URL]**，輸入以下URL:

   ```
   https://{%%camp-server%%}/rest/head/mobileAppV5/{%%pkey%%}/subscriptions/{%%mcid%%}
   ```

1. 選擇 **[!UICONTROL Add Post Body]** 的子菜單。

1. 在 **[!UICONTROL Post Body]**，鍵入以下內容：

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

   marketingCloudId使您能夠協調您的應用程式訂閱者與資料庫中的收件人，因此是必需的。 您可以根據業務需要指定其他鍵值對。 在上例中，正在從應用傳遞電子郵件、名字和姓氏。

   鍵（例如cusEmail、cusFirstName和cusLastName）應與在Adobe Campaign Standard實例的自定義資源中定義的欄位ID匹配。 值變數（例如，email、firstName和LastName）應與從移動應用程式發送的JSON資料中的鍵匹配，同時從應用程式碼調用AMS collectPII API。

   您還可以在收集PII後退或其他後退中傳遞生命週期資料，具體取決於您的事件觸發器。 下面是生命週期資料JSON的示例：

   ```
   {
   "marketingCloudId":"{%%mcid%%}",
   "pushPlatform":"{%contextdata.pushPlatform%}",
   "cusDayslastlaunch": "{%%DaysSinceLastUse%%}", 
   "cusDaysfirstlaunch": "{%%DaysSinceFirstUse%%}", 
   "cusLaunches": "{%%Launches%%}"
   }
   ```

   在中定義的資料元素 [!DNL Experience Platform Launch] 應以雙百分比括起來，例如%%mcid%%，而應用程式的上下文變數應以單個百分比括起來，例如%contextdata.email%。

1. 在 **[!UICONTROL Content Type]**&#x200B;鍵 **應用程式/json**。

1. 在 **[!UICONTROL Timeout]**，選擇0。

   ![](assets/do-not-localize/rules_2.png)

您的用戶資料現在已配置為發送到市場活動。

### 應用內跟蹤後退 {#inapp-tracking-postback}

>[!NOTE]
>
>如果您使用的是Android ACPCore v1.4.0或更高版本/iOSACPCore v2.3.0或更高版本，則無需配置跟蹤回傳。

將跟蹤資料發送到 [!DNL Adobe Campaign Standard] 要報告您的用戶如何與移動應用程式中的In-App消息交互，請在中建立以下規則 [!DNL Experience Platform Launch]:

1. 在 [!DNL Experience Platform Launch]，從您的移動應用程式儀表板中選擇 **[!UICONTROL Rules]** 頁籤 **[!UICONTROL Add Rule]**。

1. 鍵入名稱，例如， **Adobe Campaign — 應用內點擊跟蹤**。

1. 在 **[!UICONTROL Events]** ，按一下 **[!UICONTROL Add]**。

1. 從 **[!UICONTROL Extension]** 下拉，選擇 **[!UICONTROL Adobe Campaign Standard]**。 然後， **[!UICONTROL In-App click tracking]** 的 **[!UICONTROL Event type]** 下拉。

1. 按一下&#x200B;**[!UICONTROL Keep changes]**。

1. 在 **[!UICONTROL Actions]** ，按一下 **[!UICONTROL Add]**。

1. 從 **[!UICONTROL Extension]** 下拉，選擇 **[!UICONTROL Mobile Core]**。 然後， **[!UICONTROL Send postback]** 的 **[!UICONTROL Event type]** 下拉。

1. 在 **[!UICONTROL URL]**，鍵入以下URL:

   ```
   https://{%%camp-server%%}/r/?id={%id%}&mcid={%%mcid%%}
   ```

1. 選擇 **[!UICONTROL Add post body]** 的子菜單。

1. In **[!UICONTROL Post Body]**, type **{}**.

1. 在 **[!UICONTROL Content Type]**&#x200B;鍵 **應用程式/json**。

1. 在 **[!UICONTROL Timeout]**，選擇0。

   ![](assets/do-not-localize/rules_3.png)

### 推送通知跟蹤後退 {#push-tracking-postback}

>[!NOTE]
>
>如果您使用的是Android ACPCore v1.4.0或更高版本/iOSACPCore v2.3.0或更高版本，則無需配置跟蹤回傳。

將跟蹤資料發送到 [!DNL Adobe Campaign Standard]，這有助於跟蹤推送通知遞送和用戶與移動應用程式的交互，您必須在 [!DNL Experience Platform Launch]。

有關推式跟蹤的詳細資訊，請參見 [推送跟蹤](../../administration/using/push-tracking.md)。

要跟蹤應用程式操作，請使用trackAction API。 有關詳細資訊，請參見 [跟蹤應用操作](https://app.gitbook.com/@aep-sdks/s/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#track-app-actions)。

1. 在 [!DNL Experience Platform Launch]，在您的移動應用程式儀表板中，按一下 **[!UICONTROL Rules]** 頁籤 **[!UICONTROL Add Rule]**。

1. 鍵入名稱，例如， **Adobe Campaign — 推式點擊跟蹤**。

1. 在 **[!UICONTROL Events]** ，按一下 **[!UICONTROL Add]**。

1. 從 **[!UICONTROL Extension]** 下拉，選擇 **[!UICONTROL Mobile Core]**。 然後， **[!UICONTROL Track Action]** 的 **[!UICONTROL Event type]** 下拉。

1. 從 **[!UICONTROL Action]** 下拉，選擇 **[!UICONTROL Action]**&#x200B;選中 **[!UICONTROL equals]**&#x200B;的 **跟蹤**。

1. 按一下 **[!UICONTROL Keep changes]**。然後，在 **[!UICONTROL Actions]** ，按一下 **[!UICONTROL Add]**。

1. 從 **[!UICONTROL Extension]** 下拉，選擇 **[!UICONTROL Mobile Core]**。 然後， **[!UICONTROL Send postback]** 的 **[!UICONTROL Action type]** 下拉。

1. 在 **[!UICONTROL URL]**，輸入以下URL:

   ```
   https://{%%camp-server%%}/r/?id={%contextdata.broadlogId%},{%contextdata.deliveryId%},{%contextdata.action%}&mcId={%%mcid%%}
   ```

1. 選擇 **[!UICONTROL Add post body]** 的子菜單。

1. 添加帖子正文，例如{ }。

1. 在 **[!UICONTROL Content Type]**&#x200B;鍵 **應用程式/json**。

1. 在 **[!UICONTROL Timeout]**，選擇0。

### 位置後退 {#location-postback}

1. 在 [!DNL Experience Platform Launch]，在您的移動應用程式儀表板中，按一下 **[!UICONTROL Rules]** 頁籤 **[!UICONTROL Add Rule]**。

1. 鍵入名稱，例如， **位置後退**。

1. 在 **[!UICONTROL Events]** ，按一下 **[!UICONTROL Add]**。

1. 建立事件，例如，輸入POI或退出POI。 從 **[!UICONTROL Extension]** 下拉，選擇 **位置 — Beta**。 然後， **輸入POI** 或 **退出POI** 的 **[!UICONTROL Event type]** 下拉。

1. 輸入名稱，例如， **位置 — Beta — 輸入POI** 或 **退出POI**。

1. 在 **[!UICONTROL Actions]** ，按一下 **[!UICONTROL Add]**。

1. 從 **[!UICONTROL Extension]** 下拉，選擇 **[!UICONTROL Mobile Core]**。 然後， **[!UICONTROL Send postback]** 從 **[!UICONTROL Action type]** 下拉。

1. 輸入名稱，例如， **移動核心 — 發送位置回傳**。

1. 在 **[!UICONTROL URL]**，輸入以下URL:

   ```
   https://{%%camp-server%%}/rest/head/mobileAppV5/{%%pkey%%}/locations/
   ```

1. 選擇 **[!UICONTROL Add post body]** 複選框並添加帖子正文，例如：

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
   >在上例中，右側的資料元素必須在 [!DNL Experience Platform Launch] 通過利用 [建立資料元素](../../administration/using/configuring-rules-launch.md#create-data-elements)。 支援左側的資料元素 [!DNL Adobe Campaign Standard] 不需要任何配置。 如果需要其他資料，則必須在 [!DNL Adobe Campaign Standard]。

1. 在 **[!UICONTROL Content Type]**&#x200B;鍵 **應用程式/json**。

1. 在 **[!UICONTROL Timeout]**，選擇5。

   ![](assets/do-not-localize/rules_4.png)
