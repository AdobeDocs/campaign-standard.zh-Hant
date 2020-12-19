---
solution: Campaign Standard
product: campaign
title: 設定Adobe Experience Platform啟動規則以支援Adobe Campaign Standard使用案例
description: 設定Adobe Experience Platform啟動規則以支援Adobe Campaign Standard使用案例
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '914'
ht-degree: 1%

---


# 設定啟動規則以支援Adobe Campaign Standard 使用案例 {#configuring-rules-launch}

在[!DNL Adobe Experience Platform Launch]中，您需要建立資料元素和規則，將PII和其他資料從行動應用程式傳送至[!DNL Adobe Campaign Standard]。

為確保[!DNL Adobe Experience Platform Launch]中的所有配置更改都生效，您必須發佈這些更改。 如需詳細資訊，請參閱[Publishing](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#publish-the-configuration)。

要在[!DNL Experience Platform Launch]中建立規則，請執行以下步驟：

1. [建立資料元素](../../administration/using/configuring-rules-launch.md#create-data-elements)
2. [為要](../../administration/using/configuring-rules-launch.md#create-data-elements) 支援的使用案例建立規則：
   * [PII回傳](../../administration/using/configuring-rules-launch.md#pii-postback)
   * [應用程式內追蹤回傳](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback)
   * [推播通知追蹤回傳](../../administration/using/configuring-rules-launch.md#push-tracking-postback)
   * [位置回傳](../../administration/using/configuring-rules-launch.md#location-postback)

## 建立資料元素{#create-data-elements}

以下是建議您在[!DNL Experience Platform Launch]中建立的資料元素。
您可以根據需求建立其他資料元素。

* **[!UICONTROL Experience Cloud ID]**
* **[!UICONTROL Pkey]**
* **[!UICONTROL Campaign server]**

要建立這些資料元素：

1. 在[!DNL Experience Platform Launch]的行動應用程式儀表板中，按一下&#x200B;**[!UICONTROL Data Elements]**&#x200B;標籤。

1. 要建立&#x200B;**[!UICONTROL Experience Cloud ID]**&#x200B;資料元素，請按一下&#x200B;**[!UICONTROL Create New Data Element]**。

1. 例如，在&#x200B;**[!UICONTROL Name]**&#x200B;欄位中，鍵入&#x200B;**mcid**。

1. 從&#x200B;**[!UICONTROL Extension]**&#x200B;下拉式清單中，選取&#x200B;**[!UICONTROL Mobile Core]**。 然後，在&#x200B;**[!UICONTROL Data element]**&#x200B;類型下拉式清單中&#x200B;**[!UICONTROL Experience Cloud ID]**。

   ![](assets/do-not-localize/rules_1.png)

1. 要建立Pkey資料元素，請按一下&#x200B;**[!UICONTROL Add data element]**。

1. 例如，在&#x200B;**[!UICONTROL Name]**&#x200B;欄位中，鍵入&#x200B;**pkey**。

1. 從&#x200B;**[!UICONTROL Extension]**&#x200B;下拉式清單中，選取&#x200B;**[!UICONTROL Adobe Campaign Standard]**。 然後，在&#x200B;**[!UICONTROL Data element]**&#x200B;類型下拉式清單中&#x200B;**[!UICONTROL pkey]**。

1. 若要建立促銷活動伺服器資料元素，請按一下&#x200B;**[!UICONTROL Add data element]**。

1. 在&#x200B;**[!UICONTROL Name]**&#x200B;欄位中輸入名稱，例如&#x200B;**camp-server**。

1. 從&#x200B;**[!UICONTROL Extension]**&#x200B;下拉式清單中，選取&#x200B;**[!UICONTROL Adobe Campaign Standard]**。 然後，在&#x200B;**[!UICONTROL Data element]**&#x200B;類型下拉式清單中，**[!UICONTROL Campaign Server]**。

## 建立規則{#creating-rules}

您需要建立下列規則：

* [PII回傳](../../administration/using/configuring-rules-launch.md#pii-postback)
* [應用程式內追蹤回傳](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback)
* [推播通知追蹤回傳](../../administration/using/configuring-rules-launch.md#push-tracking-postback)
* [位置回傳](../../administration/using/configuring-rules-launch.md#location-postback)

### PII回傳{#pii-postback}

>[!NOTE]
>
>若要從行動應用程式傳送PII資訊至Adobe Campaign，您必須實作SDK API。 如需詳細資訊，請前往[CollectPII](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#collect-pii)。

若要將PII資料傳送至[!DNL Adobe Campaign Standard]，請在[!DNL Experience Platform Launch]中建立規則：

1. 在[!DNL Experience Platform Launch]的行動應用程式儀表板中，按一下&#x200B;**[!UICONTROL Rules]**&#x200B;標籤，然後按一下&#x200B;**[!UICONTROL Create New Rule]**。

1. 鍵入名稱，例如&#x200B;**Mobile Core - Collect PII**。

1. 在&#x200B;**[!UICONTROL Events]**&#x200B;區段中，按一下&#x200B;**[!UICONTROL Add]**。

1. 從&#x200B;**[!UICONTROL Extension]**&#x200B;下拉式清單中，選取&#x200B;**[!UICONTROL Mobile Core]**。 然後，在&#x200B;**[!UICONTROL Event type]**&#x200B;下拉式清單中，**[!UICONTROL Collect PII]**。

1. 按一下 **[!UICONTROL Keep changes]**。

1. 在&#x200B;**[!UICONTROL Actions]**&#x200B;區段中，按一下&#x200B;**[!UICONTROL Add]**。

1. 從&#x200B;**[!UICONTROL Extension]**&#x200B;下拉式清單中，選取&#x200B;**[!UICONTROL Mobile Core]**。 然後，在&#x200B;**[!UICONTROL Action type]**&#x200B;下拉式清單中，**[!UICONTROL Send PII]**。

1. 在&#x200B;**[!UICONTROL URL]**&#x200B;中，輸入以下URL:

   ```
   https://{%%camp-server%%}/rest/head/mobileAppV5/{%%pkey%%}/subscriptions/{%%mcid%%}
   ```

1. 選中&#x200B;**[!UICONTROL Add Post Body]**&#x200B;複選框。

1. 在&#x200B;**[!UICONTROL Post Body]**&#x200B;中，鍵入以下內容：

   ```
   {
   "marketingCloudId":
   "{%%mcid%%}",
   "cusEmail":
   "{%contextdata.email%}",
   "cusFirstName":
   "{%contextdata.firstName%}",
   "cusLastName":
   "{%contextdata.lastName%}" }
   ```

   MarketingCloudId可讓您協調應用程式訂閱者與資料庫中的收件者，因此是必要項目。 您可以根據您的業務需求指定其他金鑰值配對。 在上述範例中，會從應用程式傳遞「電子郵件」、「名字」和「姓氏」。

   索引鍵（例如cusEmail、cusFirstName和cusLastName）應符合您在Adobe Campaign Standard例項的自訂資源中定義的欄位ID。 值變數（例如email、firstName和LastName）應符合從行動應用程式傳送的JSON資料中，從應用程式程式碼呼叫AMS collectPII API時的金鑰。

   您也可以根據事件觸發程式，在Collect PII回傳或不同的回傳中傳遞生命週期資料。 以下是生命週期資料JSON的範例：

   ```
   {
   "marketingCloudId":"{%%mcid%%}",
   "cusDayslastlaunch": "{%%DaysSinceLastUse%%}", 
   "cusDaysfirstlaunch": "{%%DaysSinceFirstUse%%}", 
   "cusLaunches": "{%%Launches%%}"
   }
   ```

   [!DNL Experience Platform Launch]中定義的資料元素應以雙重百分比括住，例如%%mcid%%，而應用程式的上下文變數應以單一百分比括住，例如%contextdata.email%。

1. 在&#x200B;**[!UICONTROL Content Type]**&#x200B;中，鍵入&#x200B;**application/json**。

1. 在&#x200B;**[!UICONTROL Timeout]**&#x200B;中，選擇0。

   ![](assets/do-not-localize/rules_2.png)

您的使用者資料現在已設定為傳送至Campaign。

### 應用程式內追蹤回傳{#inapp-tracking-postback}

若要傳送追蹤資料至[!DNL Adobe Campaign Standard]，以報告您的使用者如何與行動應用程式中的應用程式內訊息互動，請在[!DNL Experience Platform Launch]中建立下列規則：

1. 在[!DNL Experience Platform Launch]的行動應用程式儀表板中，選取&#x200B;**[!UICONTROL Rules]**&#x200B;標籤，然後按一下&#x200B;**[!UICONTROL Add Rule]**。

1. 輸入名稱，例如&#x200B;**Adobe Campaign —— 應用程式內點按tracking**。

1. 在&#x200B;**[!UICONTROL Events]**&#x200B;區段中，按一下&#x200B;**[!UICONTROL Add]**。

1. 從&#x200B;**[!UICONTROL Extension]**&#x200B;下拉式清單中，選取&#x200B;**[!UICONTROL Adobe Campaign Standard]**。 然後，在&#x200B;**[!UICONTROL Event type]**&#x200B;下拉式清單中，**[!UICONTROL In-App click tracking]**。

1. 按一下 **[!UICONTROL Keep changes]**。

1. 在&#x200B;**[!UICONTROL Actions]**&#x200B;區段中，按一下&#x200B;**[!UICONTROL Add]**。

1. 從&#x200B;**[!UICONTROL Extension]**&#x200B;下拉式清單中，選取&#x200B;**[!UICONTROL Mobile Core]**。 然後，在&#x200B;**[!UICONTROL Event type]**&#x200B;下拉式清單中，**[!UICONTROL Send postback]**。

1. 在&#x200B;**[!UICONTROL URL]**&#x200B;中，鍵入以下URL:

   ```
   https://{%%camp-server%%}/r/?id={%id%}&mcid={%%mcid%%}
   ```

1. 選中&#x200B;**[!UICONTROL Add post body]**&#x200B;複選框。

1. 在&#x200B;**[!UICONTROL Post Body]**&#x200B;中，鍵入&#x200B;**{}**。

1. 在&#x200B;**[!UICONTROL Content Type]**&#x200B;中，鍵入&#x200B;**application/json**。

1. 在&#x200B;**[!UICONTROL Timeout]**&#x200B;中，選擇0。

   ![](assets/do-not-localize/rules_3.png)

### 推播通知追蹤回傳{#push-tracking-postback}

若要傳送追蹤資料至[!DNL Adobe Campaign Standard]，以協助追蹤您的推播通知傳送以及您的使用者與行動應用程式的互動，您必須在[!DNL Experience Platform Launch]中建立規則。

如需推播追蹤的詳細資訊，請參閱[推播追蹤](../../administration/using/push-tracking.md)。

若要追蹤應用程式動作，請使用trackAction API。 如需詳細資訊，請參閱[追蹤應用程式動作](https://app.gitbook.com/@aep-sdks/s/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#track-app-actions)。

1. 在[!DNL Experience Platform Launch]的行動應用程式儀表板中，按一下&#x200B;**[!UICONTROL Rules]**&#x200B;標籤，然後按一下&#x200B;**[!UICONTROL Add Rule]**。

1. 輸入名稱，例如&#x200B;**Adobe Campaign —— 推播點按追蹤**。

1. 在&#x200B;**[!UICONTROL Events]**&#x200B;區段中，按一下&#x200B;**[!UICONTROL Add]**。

1. 從&#x200B;**[!UICONTROL Extension]**&#x200B;下拉式清單中，選取&#x200B;**[!UICONTROL Mobile Core]**。 然後，在&#x200B;**[!UICONTROL Event type]**&#x200B;下拉式清單中，**[!UICONTROL Track Action]**。

1. 從&#x200B;**[!UICONTROL Action]**&#x200B;下拉式清單中，選擇&#x200B;**[!UICONTROL Action]**，選擇&#x200B;**[!UICONTROL equals]**，然後輸入&#x200B;**tracking**。

1. 按一下 **[!UICONTROL Keep changes]**。然後，在&#x200B;**[!UICONTROL Actions]**&#x200B;區段中，按一下&#x200B;**[!UICONTROL Add]**。

1. 從&#x200B;**[!UICONTROL Extension]**&#x200B;下拉式清單中，選取&#x200B;**[!UICONTROL Mobile Core]**。 然後，在&#x200B;**[!UICONTROL Action type]**&#x200B;下拉式清單中，**[!UICONTROL Send postback]**。

1. 在&#x200B;**[!UICONTROL URL]**&#x200B;中，輸入以下URL:

   ```
   https://{%%camp-server%%}/r/?id={%contextdata.broadlogId%},{%contextdata.deliveryId%},{%contextdata.action%}&mcId={%%mcid%%}
   ```

1. 選中&#x200B;**[!UICONTROL Add post body]**&#x200B;複選框。

1. 新增您的貼文內文，例如{ }。

1. 在&#x200B;**[!UICONTROL Content Type]**&#x200B;中，鍵入&#x200B;**application/json**。

1. 在&#x200B;**[!UICONTROL Timeout]**&#x200B;中，選擇0。

### 位置回傳{#location-postback}

1. 在[!DNL Experience Platform Launch]的行動應用程式儀表板中，按一下&#x200B;**[!UICONTROL Rules]**&#x200B;標籤，然後按一下&#x200B;**[!UICONTROL Add Rule]**。

1. 鍵入名稱，例如&#x200B;**Location postback**。

1. 在&#x200B;**[!UICONTROL Events]**&#x200B;區段中，按一下&#x200B;**[!UICONTROL Add]**。

1. 建立事件，例如輸入POI或退出POI。 從&#x200B;**[!UICONTROL Extension]**&#x200B;下拉式清單中，選擇&#x200B;**Places - Beta**。 然後，在&#x200B;**下拉式清單中輸入POI**&#x200B;或&#x200B;**退出POI**。**[!UICONTROL Event type]**

1. 輸入名稱，例如，**Places - Beta —— 輸入POI**&#x200B;或&#x200B;**Exit POI**。

1. 在&#x200B;**[!UICONTROL Actions]**&#x200B;區段中，按一下&#x200B;**[!UICONTROL Add]**。

1. 從&#x200B;**[!UICONTROL Extension]**&#x200B;下拉式清單中，選取&#x200B;**[!UICONTROL Mobile Core]**。 然後，從&#x200B;**[!UICONTROL Action type]**&#x200B;下拉式清單中&#x200B;**[!UICONTROL Send postback]**。

1. 輸入名稱，例如&#x200B;**Mobile Core - Send Location Postback**。

1. 在&#x200B;**[!UICONTROL URL]**&#x200B;中，輸入以下URL:

   ```
   https://{%%camp-server%%}/rest/head/mobileAppV5/{%%pkey%%}/locations/
   ```

1. 選取&#x200B;**[!UICONTROL Add post body]**&#x200B;核取方塊並新增您的貼文內文，例如：

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
   >在上例中，右側的資料元素需要通過利用[建立資料元素](../../administration/using/configuring-rules-launch.md#create-data-elements)中的步驟在[!DNL Experience Platform Launch]中配置。 左側的資料元素在[!DNL Adobe Campaign Standard]中受支援，不需要任何設定。 如果需要其他資料，則需要在[!DNL Adobe Campaign Standard]中執行自定義資源擴展。

1. 在&#x200B;**[!UICONTROL Content Type]**&#x200B;中，鍵入&#x200B;**application/json**。

1. 在&#x200B;**[!UICONTROL Timeout]**&#x200B;中，選擇5。

   ![](assets/do-not-localize/rules_4.png)
