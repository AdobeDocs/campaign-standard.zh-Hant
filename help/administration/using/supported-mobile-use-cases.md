---
title: 在Adobe Campaign Standard使用Adobe Experience PlatformSDK支援的移動使用案例
description: 瞭解如何支援移動使用案例
audience: channels
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 3cd8d756-a271-4e53-8ed0-984ce20298bc
source-git-commit: 597ece8d833a216f0540f801461b08fdc9865024
workflow-type: tm+mt
source-wordcount: '947'
ht-degree: 0%

---

# Adobe Campaign Standard 支援的行動使用案例 {#mobile-use-cases}

在此頁中，您將找到支援的每個移動使用案例的清單 [!DNL Adobe Campaign Standard] 使用 [!DNL Adobe Experience Platform SDKs]。 請注意，支援這些使用案例涉及安裝和配置 [!DNL Adobe Experience Platform SDKs]。 [!DNL tags in Adobe Experience Platform], [!DNL Adobe Campaign Standard]。 有關此的詳細資訊，請參閱此 [頁](../../administration/using/configuring-a-mobile-application.md)。

Adobe Campaign Standard支援以下使用案例：

* [在Campaign Standard中註冊移動配置檔案](../../administration/using/supported-mobile-use-cases.md#register-mobile-profile)
* [向Campaign Standard發送推送令牌](../../administration/using/supported-mobile-use-cases.md#send-push-token)
* [使用應用程式中的自定義資料豐富移動配置檔案](../../administration/using/supported-mobile-use-cases.md#enrich-mobile-profile-custom)
* [利用應用程式的生命週期資料豐富移動配置檔案](../../administration/using/supported-mobile-use-cases.md#enrich-mobile-profile-lifecycle)
* [跟蹤使用推送通知的用戶交互](../../administration/using/supported-mobile-use-cases.md#track-user-push)
* [在移動應用中實施自定義事件以觸發In-App消息](../../administration/using/supported-mobile-use-cases.md#custom-event-inapp)
* [為基於In-App消息的配置檔案模板設定其他身份驗證的連結欄位](../../administration/using/supported-mobile-use-cases.md#linkage-fields-inapp)

要配置這些使用情形，您需要以下擴展：

* **[!DNL Adobe Campaign Standard]** <br>要安裝和配置Campaign Standard擴展，請參見 [在資料收集UI中配置Campaign Standard擴展](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/#configure-the-campaign-standard-extension)。
* **[!DNL Mobile Core]**，將自動安裝。 <br>有關移動核心擴展的詳細資訊，請參見 [移動核心](https://developer.adobe.com/client-sdks/documentation/mobile-core/)。
* **[!DNL Profile]**，將自動安裝。 <br>有關「配置檔案」擴展的詳細資訊，請參見 [配置檔案](https://developer.adobe.com/client-sdks/documentation/profile/)。

## 在Campaign Standard中註冊移動配置檔案 {#register-mobile-profile}

### 與iOS {#register-mobile-profile-ios}

在iOS, [!DNL Experience Platform APIs] 是必需的：

* **[!UICONTROL Lifecycle Start]**，當應用啟動時和應用處於前景時。
* **[!UICONTROL Lifecycle Pause]**，在後台。

有關詳細資訊，請參見 [iOS生命週期擴展](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/ios/)。

以下是此使用案例與iOS的示例實現：

```
 func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?) -> Bool {
  
  
 ACPCore.setLogLevel(.debug)
 appId = SettingsBundle.getLaunchAppId()
   
 //===== START Set up Adobe SDK =====
 ACPCore.configure(withAppId: appId)
   
 ACPCampaign.registerExtension()
 ACPIdentity.registerExtension()
 ACPLifecycle.registerExtension()
 ACPUserProfile.registerExtension()
 ACPSignal.registerExtension()
 ACPCore.start()
 ACPCore.lifecycleStart(nil)
   
 return true
 }
  
func applicationDidEnterBackground(_ application: UIApplication) {
 ACPCore.lifecyclePause()
 }
   
 func applicationDidBecomeActive(_ application: UIApplication) {
 // Workaround until jira AMSDK-7411 is fixed.
 sleep(2)
 ACPCore.lifecycleStart(nil)
 }
```

### 使用Android {#register-mobile-profile-android}

在Android中，以下 [!DNL Experience Platform APIs] 是必需的：

* **[!UICONTROL OnResume]**
* **[!UICONTROL OnPause]**

有關詳細資訊，請參見 [Android生命週期擴展](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/android/)。

下面是此Android用例的示例實現：

```
@Override
  
public void onResume() {
 super.onResume();
 MobileCore.setApplication(getApplication());
 MobileCore.lifecycleStart(null);
 handleOpenTracking();
 }
  
 @Override
 public void onPause() {
 super.onPause();
 MobileCore.lifecyclePause();
 }
```

## 向Adobe Campaign Standard發送推令牌 {#send-push-token}

### 與iOS {#send-push-token-ios}

在iOS, [!DNL Experience Platform SDK] 是必需的：

* **[!UICONTROL setPushIdentifier]** <br>有關詳細資訊，請參見 [setPushIdentifier](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/api-reference/)。

以下是此使用案例的示例實現，其中包括iOS:

```
func application(_ application: UIApplication, didRegisterForRemoteNotificationsWithDeviceToken deviceToken: Data) {
  
 // Register Device Token
 ACPCore.setPushIdentifier(deviceToken)
```

### 使用Android {#send-push-token-android}

在Android中，以下 [!DNL Experience Platform SDK] 是必需的：

* **[!UICONTROL setPushIdentifier]** <br>有關詳細資訊，請參見 [setPushIdentifier](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/api-reference/)。

下面是此Android用例的示例實現：

```
@Override
public void onNewToken(String token) {
    Log.d(TAG, "Refreshed token: " + token);
    MobileCore.setPushIdentifier(token);
}
```

## 使用應用程式中的自定義資料豐富移動配置檔案 {#enrich-mobile-profile-custom}

要使此使用案例有效，您需要為PII回傳建立規則。 有關詳細資訊，請參見 [PII回寄](../../administration/using/configuring-rules-launch.md#pii-postback)。

### 與iOS {#enrich-mobile-profile-custom-ios}

在iOS, [!DNL Experience Platform API] 是必需的：

* 收集PII <br> 有關詳細資訊，請參見collectPII。

以下是此使用案例與iOS的示例實現：

```
ACPCore.collectPii(["pushPlatform":"apns", "email":email, "firstName":firstName, "lastName":lastName])
```

### 使用Android {#enrich-mobile-profile-custom-android}

在Android中，以下 [!DNL Experience Platform API] 是必需的：

* 收集PII <br> 有關詳細資訊，請參見collectPII。

下面是此Android用例的示例實現：

```
HashMap<String, String> data = new HashMap<>();
data.put("pushPlatform", "gcm");
data.put("firstName", firstNameText); 
data.put("lastName", lastNameText); 
data.put("email", emailText); 
MobileCore.collectPii(data);
```

## 利用應用程式的生命週期資料豐富移動配置檔案 {#enrich-mobile-profile-lifecycle}

要使此使用案例有效，您需要為PII回傳建立規則。 有關詳細資訊，請參見 [PII回寄](../../administration/using/configuring-rules-launch.md#pii-postback)。

>[!NOTE]
>
>Adobe Campaign不區分自定義資料或生命週期資料與移動應用。 這兩種類型的資料都可以使用collectPii後退規則發送到伺服器以響應移動應用中的事件。

### 與iOS {#enrich-mobile-profile-lifecycle-ios}

在iOS, [!DNL Experience Platform APIs] 是必需的：

* **[!UICONTROL Lifecycle Start]**，當應用啟動時和應用處於前景時。
* **[!UICONTROL Lifecycle Pause]**，在後台。

有關詳細資訊，請參見 [iOS生命週期擴展](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/ios/)。

以下是此使用案例與iOS的示例實現：

```
func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?) -> Bool {
  
  
 ACPCore.setLogLevel(.debug)
 appId = SettingsBundle.getLaunchAppId()
   
 //===== START Set up Adobe SDK =====
 ACPCore.configure(withAppId: appId)
   
 ACPCampaign.registerExtension()
 ACPIdentity.registerExtension()
 ACPLifecycle.registerExtension()
 ACPUserProfile.registerExtension()
 ACPSignal.registerExtension()
 ACPCore.start()
 ACPCore.lifecycleStart(nil)
   
 return true
 }
  
func applicationDidEnterBackground(_ application: UIApplication) {
 ACPCore.lifecyclePause()
 }
   
 func applicationDidBecomeActive(_ application: UIApplication) {
 // Workaround until jira AMSDK-7411 is fixed.
 sleep(2)
 ACPCore.lifecycleStart(nil)
 }
```

### 使用Android {#enrich-mobile-profile-lifecycle-android}

在Android中，以下 [!DNL Experience Platform APIs] 是必需的：

* **[!UICONTROL OnResume]**
* **[!UICONTROL OnPause]**

有關詳細資訊，請參見 [Android生命週期擴展](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/android/)。

下面是此Android用例的示例實現：

```
@Override
  
public void onResume() {
 super.onResume();
 MobileCore.setApplication(getApplication());
 MobileCore.lifecycleStart(null);
 handleOpenTracking();
 }
  
 @Override
 public void onPause() {
 super.onPause();
 MobileCore.lifecyclePause();
 }
```

## 跟蹤使用推送通知的用戶交互 {#track-user-push}

您需要為推式通知跟蹤後退建立規則。 有關詳細資訊，請參見 [推送通知跟蹤後退](../../administration/using/configuring-rules-launch.md#push-tracking-postback)。

### 與iOS {#track-user-push-ios}

在iOS, [!DNL Experience Platform SDK] 是必需的：

* **[!UICONTROL trackAction]**。 有關詳細資訊，請參見 [跟蹤應用操作](https://developer.adobe.com/client-sdks/documentation/mobile-core/api-reference/#trackaction)。

以下是此使用案例與iOS的示例實現：

```
let deliveryId = userInfo["_dId"] as? String
let broadlogId = userInfo["_mId"] as? String
if (deliveryId != nil && broadlogId != nil) {
    ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
}
```

### 使用Android {#track-user-push-android}

在Android中，以下 [!DNL Experience Platform SDK] 是必需的：

* **[!UICONTROL trackAction]**
有關詳細資訊，請參見 [跟蹤應用操作](https://developer.adobe.com/client-sdks/documentation/mobile-core/api-reference/#trackaction)。

下面是此Android用例的示例實現：

```
contextData.put("deliveryId", deliveryId);
contextData.put("broadlogId", messageId);
contextData.put("action", "2");
MobileCore.trackAction("tracking", contextData);
```

## 在應用程式中實施自定義事件以觸發In-App消息 {#custom-event-inapp}

### 與iOS {#custom-event-inapp-ios}

在iOS, [!DNL Experience Platform SDK] 是必需的：

* **[!UICONTROL trackAction]**. 有關詳細資訊，請參見 [跟蹤應用操作](https://developer.adobe.com/client-sdks/documentation/mobile-core/api-reference/#trackaction)。

以下是此使用案例與iOS的示例實現：

```
ACPCore.trackAction(mobileEventName, data: [:] )
```

### 使用Android {#custom-event-inapp-android}

在Android中，以下 [!DNL Experience Platform SDK] 是必需的：

* **[!UICONTROL trackAction]**
有關詳細資訊，請參見 [跟蹤應用操作](https://developer.adobe.com/client-sdks/documentation/mobile-core/api-reference/#trackaction)。

下面是此Android用例的示例實現：

```
MobileCore.trackAction(mobileEventText, new HashMap<String,String>());
```

## 設定附加驗證的連結欄位 {#linkage-fields-inapp}

### 與iOS {#linkage-fields-inapp-ios}

要為基於iOSIn-App消息的配置檔案模板設定附加身份驗證的連結欄位，請執行以下操作 [!DNL Experience Platform SDK] 是必需的：

* 設定連結欄位 <br>有關詳細資訊，請參見 [設定連結欄位](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/api-reference/#setlinkagefields)。
* 重置連結欄位 <br>有關詳細資訊，請參見 [重置連結欄位](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/api-reference/#setlinkagefields)。

以下是此使用案例與iOS的示例實施。

要設定連結欄位：

```
var linkageFields = [String: String]()
linkageFields["cusEmail"] = "john.doe@email.com"
ACPCampaign.setLinkageFields(linkageFields)
```

要重置連結欄位：

```
ACPCampaign.resetLinkageFields(linkageFields)
```

### 使用Android {#linkage-fields-inapp-android}

要為基於Android中In-App消息的配置檔案模板設定附加身份驗證的連結欄位，需要以下Experience PlatformSDK:

* 設定連結欄位 <br>有關詳細資訊，請參見 [設定連結欄位](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/api-reference/#setlinkagefields)。
* 重置連結欄位 <br>有關詳細資訊，請參見 [重置連結欄位](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/api-reference/#resetlinkagefields)。

下面是此用例在Android中的示例實現。

要設定連結欄位：

```
HashMap<String, String> linkageFields = new HashMap<String, String>();
linkageFields.put("cusEmail", "john.doe@email.com");
Campaign.setLinkageFields(linkageFields);
```

要重置連結欄位：

```
Campaign.resetLinkageFields()
```
