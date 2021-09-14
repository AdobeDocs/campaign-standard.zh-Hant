---
title: 設定Adobe Experience Platform Launch規則以支援Adobe Campaign Standard使用案例
description: 設定Adobe Experience Platform Launch規則以支援Adobe Campaign Standard使用案例
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
feature: Instance Settings
role: Admin
level: Experienced
exl-id: b5f4f612-ea23-4007-b427-069777ecdd58
source-git-commit: 8c4e38a3fc66e4d819575fcd64616a822e0e1f82
workflow-type: tm+mt
source-wordcount: '954'
ht-degree: 1%

---

# 設定啟動規則以支援 Adobe Campaign Standard 使用案例 {#configuring-rules-launch}

在[!DNL Adobe Experience Platform Launch]中，您需要建立資料元素和規則，以將PII和其他資料從行動應用程式傳送至[!DNL Adobe Campaign Standard]。

為確保[!DNL Adobe Experience Platform Launch]中的所有配置更改都生效，您必須發佈這些更改。 如需詳細資訊，請參閱[Publishing](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#publish-the-configuration)。

要在[!DNL Experience Platform Launch]中建立規則，請執行以下步驟：

1. [建立資料元素](../../administration/using/configuring-rules-launch.md#create-data-elements)
2. [建立](../../administration/using/configuring-rules-launch.md#create-data-elements) 要支援的使用案例的規則：
   * [PII回傳](../../administration/using/configuring-rules-launch.md#pii-postback)
   * [應用程式內追蹤回傳](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback)
   * [推播通知追蹤回傳](../../administration/using/configuring-rules-launch.md#push-tracking-postback)
   * [位置回傳](../../administration/using/configuring-rules-launch.md#location-postback)

## 建立資料元素 {#create-data-elements}

以下是建議您在[!DNL Experience Platform Launch]中建立的資料元素。
您可以視需要建立其他資料元素。

* **[!UICONTROL Experience Cloud ID]**
* **[!UICONTROL Pkey]**
* **[!UICONTROL Campaign server]**

若要建立這些資料元素：

1. 在[!DNL Experience Platform Launch]中，從行動應用程式控制面板，按一下&#x200B;**[!UICONTROL Data Elements]**&#x200B;標籤。

1. 若要建立&#x200B;**[!UICONTROL Experience Cloud ID]**&#x200B;資料元素，請按一下&#x200B;**[!UICONTROL Create New Data Element]**。

1. 例如，在&#x200B;**[!UICONTROL Name]**&#x200B;欄位中，輸入&#x200B;**mcid**。

1. 從&#x200B;**[!UICONTROL Extension]**&#x200B;下拉式清單中，選取&#x200B;**[!UICONTROL Mobile Core]**。 然後，在&#x200B;**[!UICONTROL Data element]**&#x200B;類型下拉式清單中&#x200B;**[!UICONTROL Experience Cloud ID]**。

   ![](assets/do-not-localize/rules_1.png)

1. 若要建立Pkey資料元素，請按一下&#x200B;**[!UICONTROL Add data element]**。

1. 例如，在&#x200B;**[!UICONTROL Name]**&#x200B;欄位中，鍵入&#x200B;**pkey**。

1. 從&#x200B;**[!UICONTROL Extension]**&#x200B;下拉式清單中，選取&#x200B;**[!UICONTROL Adobe Campaign Standard]**。 然後，在&#x200B;**[!UICONTROL Data element]**&#x200B;類型下拉式清單中&#x200B;**[!UICONTROL pkey]**。

1. 若要建立Campaign伺服器資料元素，請按一下&#x200B;**[!UICONTROL Add data element]**。

1. 在&#x200B;**[!UICONTROL Name]**&#x200B;欄位中輸入名稱，例如&#x200B;**camp-server**。

1. 從&#x200B;**[!UICONTROL Extension]**&#x200B;下拉式清單中，選取&#x200B;**[!UICONTROL Adobe Campaign Standard]**。 然後，**[!UICONTROL Data element]**&#x200B;類型下拉式清單中的&#x200B;**[!UICONTROL Campaign Server]**。

## 建立規則 {#creating-rules}

您需要建立下列規則：

* [PII回傳](../../administration/using/configuring-rules-launch.md#pii-postback)
* [應用程式內追蹤回傳](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback)
* [推播通知追蹤回傳](../../administration/using/configuring-rules-launch.md#push-tracking-postback)
* [位置回傳](../../administration/using/configuring-rules-launch.md#location-postback)

### PII回傳 {#pii-postback}

>[!NOTE]
>
>若要將PII資訊從行動應用程式傳送至Adobe Campaign，您需要實作SDK API。 如需詳細資訊，請前往[CollectPII](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#collect-pii)。

若要將PII資料傳送至[!DNL Adobe Campaign Standard]，請在[!DNL Experience Platform Launch]中建立規則：

1. 在[!DNL Experience Platform Launch]中，從行動應用程式控制面板，依序按一下&#x200B;**[!UICONTROL Rules]**&#x200B;標籤和&#x200B;**[!UICONTROL Create New Rule]**。

1. 輸入名稱，例如&#x200B;**行動核心 — 收集PII**。

1. 在&#x200B;**[!UICONTROL Events]**&#x200B;區段中，按一下&#x200B;**[!UICONTROL Add]**。

1. 從&#x200B;**[!UICONTROL Extension]**&#x200B;下拉式清單中，選取&#x200B;**[!UICONTROL Mobile Core]**。 然後， **[!UICONTROL Event type]**&#x200B;下拉式清單中的&#x200B;**[!UICONTROL Collect PII]**。

1. 按一下&#x200B;**[!UICONTROL Keep changes]**。

1. 在&#x200B;**[!UICONTROL Actions]**&#x200B;區段中，按一下&#x200B;**[!UICONTROL Add]**。

1. 從&#x200B;**[!UICONTROL Extension]**&#x200B;下拉式清單中，選取&#x200B;**[!UICONTROL Mobile Core]**。 然後， **[!UICONTROL Action type]**&#x200B;下拉式清單中的&#x200B;**[!UICONTROL Send PII]**。

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
   "pushPlatform":
   "{%contextdata.pushPlatform%}",
   "cusEmail":
   "{%contextdata.email%}",
   "cusFirstName":
   "{%contextdata.firstName%}",
   "cusLastName":
   "{%contextdata.lastName%}" }
   ```

   marketingCloudId可讓您調解應用程式訂閱者與資料庫中的收件者，因此是必要項目。 您可以根據業務需求指定其他索引鍵值配對。 在上述範例中，會從應用程式傳遞電子郵件、名字和姓氏。

   金鑰（例如cusEmail、cusFirstName和cusLastName）應符合Adobe Campaign Standard例項中自訂資源中定義的欄位ID。 值變數（例如電子郵件、firstName和LastName）應符合行動應用程式在從應用程式程式碼呼叫AMS collectPII API時，從行動應用程式傳送之JSON資料中的索引鍵。

   您也可以根據事件觸發器，在Collect PII回傳或不同的回傳中傳遞生命週期資料。 以下是生命週期資料JSON的範例：

   ```
   {
   "marketingCloudId":"{%%mcid%%}",
   "pushPlatform":"{%contextdata.pushPlatform%}",
   "cusDayslastlaunch": "{%%DaysSinceLastUse%%}", 
   "cusDaysfirstlaunch": "{%%DaysSinceFirstUse%%}", 
   "cusLaunches": "{%%Launches%%}"
   }
   ```

   [!DNL Experience Platform Launch]中定義的資料元素應以雙重百分比括住，例如%mcid%%，而來自應用程式的內容變數應以單一百分比括住，例如%contextdata.email%。

1. 在&#x200B;**[!UICONTROL Content Type]**&#x200B;中，鍵入&#x200B;**application/json**。

1. 在&#x200B;**[!UICONTROL Timeout]**&#x200B;中，選擇0。

   ![](assets/do-not-localize/rules_2.png)

您的使用者資料現在已設定為傳送至Campaign。

### 應用程式內追蹤回傳 {#inapp-tracking-postback}

>[!NOTE]
>
>如果您使用Android ACPCore v1.4.0或更新版本/ iOS ACPCore v2.3.0或更新版本，則不需要設定追蹤回傳。

若要傳送追蹤資料至[!DNL Adobe Campaign Standard]以報告使用者在行動應用程式中與應用程式內訊息的互動情形，請在[!DNL Experience Platform Launch]中建立下列規則：

1. 在[!DNL Experience Platform Launch]中，從行動應用程式控制面板，選取&#x200B;**[!UICONTROL Rules]**&#x200B;標籤，然後按一下&#x200B;**[!UICONTROL Add Rule]**。

1. 輸入名稱，例如&#x200B;**Adobe Campaign — 應用程式內點擊追蹤**。

1. 在&#x200B;**[!UICONTROL Events]**&#x200B;區段中，按一下&#x200B;**[!UICONTROL Add]**。

1. 從&#x200B;**[!UICONTROL Extension]**&#x200B;下拉式清單中，選取&#x200B;**[!UICONTROL Adobe Campaign Standard]**。 然後， **[!UICONTROL Event type]**&#x200B;下拉式清單中的&#x200B;**[!UICONTROL In-App click tracking]**。

1. 按一下&#x200B;**[!UICONTROL Keep changes]**。

1. 在&#x200B;**[!UICONTROL Actions]**&#x200B;區段中，按一下&#x200B;**[!UICONTROL Add]**。

1. 從&#x200B;**[!UICONTROL Extension]**&#x200B;下拉式清單中，選取&#x200B;**[!UICONTROL Mobile Core]**。 然後， **[!UICONTROL Event type]**&#x200B;下拉式清單中的&#x200B;**[!UICONTROL Send postback]**。

1. 在&#x200B;**[!UICONTROL URL]**&#x200B;中，鍵入以下URL:

   ```
   https://{%%camp-server%%}/r/?id={%id%}&mcid={%%mcid%%}
   ```

1. 選中&#x200B;**[!UICONTROL Add post body]**&#x200B;複選框。

1. 在&#x200B;**[!UICONTROL Post Body]**&#x200B;中，鍵入&#x200B;**{}**。

1. 在&#x200B;**[!UICONTROL Content Type]**&#x200B;中，鍵入&#x200B;**application/json**。

1. 在&#x200B;**[!UICONTROL Timeout]**&#x200B;中，選擇0。

   ![](assets/do-not-localize/rules_3.png)

### 推播通知追蹤回傳 {#push-tracking-postback}

>[!NOTE]
>
>如果您使用Android ACPCore v1.4.0或更新版本/ iOS ACPCore v2.3.0或更新版本，則不需要設定追蹤回傳。

若要將追蹤資料傳送至[!DNL Adobe Campaign Standard]（有助於追蹤推播通知傳送以及使用者與行動應用程式的互動），您必須在[!DNL Experience Platform Launch]中建立規則。

如需推播追蹤的詳細資訊，請參閱[推播追蹤](../../administration/using/push-tracking.md)。

若要追蹤應用程式動作，請使用trackAction API。 如需詳細資訊，請參閱[追蹤應用程式動作](https://app.gitbook.com/@aep-sdks/s/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#track-app-actions)。

1. 在[!DNL Experience Platform Launch]中，從您的行動應用程式控制面板，按一下&#x200B;**[!UICONTROL Rules]**&#x200B;標籤，然後按一下&#x200B;**[!UICONTROL Add Rule]**。

1. 輸入名稱，例如&#x200B;**Adobe Campaign — 推播點擊追蹤**。

1. 在&#x200B;**[!UICONTROL Events]**&#x200B;區段中，按一下&#x200B;**[!UICONTROL Add]**。

1. 從&#x200B;**[!UICONTROL Extension]**&#x200B;下拉式清單中，選取&#x200B;**[!UICONTROL Mobile Core]**。 然後， **[!UICONTROL Event type]**&#x200B;下拉式清單中的&#x200B;**[!UICONTROL Track Action]**。

1. 從&#x200B;**[!UICONTROL Action]**&#x200B;下拉式清單中，選取&#x200B;**[!UICONTROL Action]**，選取&#x200B;**[!UICONTROL equals]**，然後輸入&#x200B;**tracking**。

1. 按一下 **[!UICONTROL Keep changes]**。然後，在&#x200B;**[!UICONTROL Actions]**&#x200B;區段中，按一下&#x200B;**[!UICONTROL Add]**。

1. 從&#x200B;**[!UICONTROL Extension]**&#x200B;下拉式清單中，選取&#x200B;**[!UICONTROL Mobile Core]**。 然後， **[!UICONTROL Action type]**&#x200B;下拉式清單中的&#x200B;**[!UICONTROL Send postback]**。

1. 在&#x200B;**[!UICONTROL URL]**&#x200B;中，輸入以下URL:

   ```
   https://{%%camp-server%%}/r/?id={%contextdata.broadlogId%},{%contextdata.deliveryId%},{%contextdata.action%}&mcId={%%mcid%%}
   ```

1. 選中&#x200B;**[!UICONTROL Add post body]**&#x200B;複選框。

1. 新增貼文內文，例如{ }。

1. 在&#x200B;**[!UICONTROL Content Type]**&#x200B;中，鍵入&#x200B;**application/json**。

1. 在&#x200B;**[!UICONTROL Timeout]**&#x200B;中，選擇0。

### 位置回傳 {#location-postback}

1. 在[!DNL Experience Platform Launch]中，從您的行動應用程式控制面板，按一下&#x200B;**[!UICONTROL Rules]**&#x200B;標籤，然後按一下&#x200B;**[!UICONTROL Add Rule]**。

1. 鍵入名稱，例如&#x200B;**Location postback**。

1. 在&#x200B;**[!UICONTROL Events]**&#x200B;區段中，按一下&#x200B;**[!UICONTROL Add]**。

1. 建立事件，例如輸入POI或退出POI。 從&#x200B;**[!UICONTROL Extension]**&#x200B;下拉式清單中，選取&#x200B;**Places - Beta**。 然後，在&#x200B;**[!UICONTROL Event type]**&#x200B;下拉式清單中，**輸入POI**&#x200B;或&#x200B;**退出POI**。

1. 輸入名稱，例如，**Places - Beta - Enter POI**&#x200B;或&#x200B;**Exit POI**。

1. 在&#x200B;**[!UICONTROL Actions]**&#x200B;區段中，按一下&#x200B;**[!UICONTROL Add]**。

1. 從&#x200B;**[!UICONTROL Extension]**&#x200B;下拉式清單中，選取&#x200B;**[!UICONTROL Mobile Core]**。 然後，從&#x200B;**[!UICONTROL Action type]**&#x200B;下拉式清單中&#x200B;**[!UICONTROL Send postback]**。

1. 輸入名稱，例如&#x200B;**行動核心 — 傳送位置回傳**。

1. 在&#x200B;**[!UICONTROL URL]**&#x200B;中，輸入以下URL:

   ```
   https://{%%camp-server%%}/rest/head/mobileAppV5/{%%pkey%%}/locations/
   ```

1. 選取&#x200B;**[!UICONTROL Add post body]**&#x200B;核取方塊並新增貼文內文，例如：

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
   >在上例中，需要利用[建立資料元素](../../administration/using/configuring-rules-launch.md#create-data-elements)中的步驟，在[!DNL Experience Platform Launch]中配置右側的資料元素。 [!DNL Adobe Campaign Standard]支援左側的資料元素，不需要任何配置。 如果需要其他資料，您需要在[!DNL Adobe Campaign Standard]中執行自訂資源擴展。

1. 在&#x200B;**[!UICONTROL Content Type]**&#x200B;中，鍵入&#x200B;**application/json**。

1. 在&#x200B;**[!UICONTROL Timeout]**&#x200B;中，選擇5。

   ![](assets/do-not-localize/rules_4.png)
