---
title: Adobe Campaign Standard支援的行動使用案例：使用Adobe Experience Platform SDK
description: 了解如何支援行動使用案例
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

在本頁面中，您會找到 [!DNL Adobe Campaign Standard] 使用 [!DNL Adobe Experience Platform SDKs]. 請注意，支援這些使用案例需要安裝和設定 [!DNL Adobe Experience Platform SDKs], [!DNL tags in Adobe Experience Platform]，和 [!DNL Adobe Campaign Standard]. 有關詳細資訊，請參閱 [頁面](../../administration/using/configuring-a-mobile-application.md).

Adobe Campaign Standard支援下列使用案例：

* [在Campaign Standard中註冊行動設定檔](../../administration/using/supported-mobile-use-cases.md#register-mobile-profile)
* [傳送推送代號至Campaign Standard](../../administration/using/supported-mobile-use-cases.md#send-push-token)
* [使用您應用程式的自訂資料擴充行動設定檔](../../administration/using/supported-mobile-use-cases.md#enrich-mobile-profile-custom)
* [使用應用程式的生命週期資料豐富行動設定檔](../../administration/using/supported-mobile-use-cases.md#enrich-mobile-profile-lifecycle)
* [透過推播通知追蹤使用者互動](../../administration/using/supported-mobile-use-cases.md#track-user-push)
* [在您的行動應用程式中實作自訂事件，以觸發應用程式內訊息](../../administration/using/supported-mobile-use-cases.md#custom-event-inapp)
* [為基於應用程式內訊息的設定檔範本設定其他驗證的連結欄位](../../administration/using/supported-mobile-use-cases.md#linkage-fields-inapp)

若要設定這些使用案例，您需要下列擴充功能：

* **[!DNL Adobe Campaign Standard]** <br>若要安裝並設定Campaign Standard擴充功能，請參閱 [在資料收集UI中設定Campaign Standard擴充功能](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/#configure-the-campaign-standard-extension).
* **[!DNL Mobile Core]**，會自動安裝。 <br>如需行動核心擴充功能的詳細資訊，請參閱 [行動核心](https://developer.adobe.com/client-sdks/documentation/mobile-core/).
* **[!DNL Profile]**，會自動安裝。 <br>如需設定檔擴充功能的詳細資訊，請參閱 [設定檔](https://developer.adobe.com/client-sdks/documentation/profile/).

## 在Campaign Standard中註冊行動設定檔 {#register-mobile-profile}

### 使用iOS {#register-mobile-profile-ios}

在iOS中， [!DNL Experience Platform APIs] 為必要項目：

* **[!UICONTROL Lifecycle Start]**、應用程式啟動時，以及應用程式於前景執行時。
* **[!UICONTROL Lifecycle Pause]**，而非應用程式於背景時。

如需詳細資訊，請參閱 [iOS中的生命週期擴充功能](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/ios/).

以下是此使用案例的範例實作(搭配iOS):

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

在Android中， [!DNL Experience Platform APIs] 為必要項目：

* **[!UICONTROL OnResume]**
* **[!UICONTROL OnPause]**

如需詳細資訊，請參閱 [Android中的生命週期擴充功能](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/android/).

以下是此Android使用案例的範例實作：

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

## 傳送推送代號至Adobe Campaign Standard {#send-push-token}

### 使用iOS {#send-push-token-ios}

在iOS中， [!DNL Experience Platform SDK] 為必要項目：

* **[!UICONTROL setPushIdentifier]** <br>如需詳細資訊，請參閱 [setPushIdentifier](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/api-reference/).

以下是此使用案例的範例實作(搭配iOS):

```
func application(_ application: UIApplication, didRegisterForRemoteNotificationsWithDeviceToken deviceToken: Data) {
  
 // Register Device Token
 ACPCore.setPushIdentifier(deviceToken)
```

### 使用Android {#send-push-token-android}

在Android中， [!DNL Experience Platform SDK] 為必要項目：

* **[!UICONTROL setPushIdentifier]** <br>如需詳細資訊，請參閱 [setPushIdentifier](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/api-reference/).

以下是此Android使用案例的範例實作：

```
@Override
public void onNewToken(String token) {
    Log.d(TAG, "Refreshed token: " + token);
    MobileCore.setPushIdentifier(token);
}
```

## 使用您應用程式的自訂資料擴充行動設定檔 {#enrich-mobile-profile-custom}

若要讓此使用案例發揮作用，您需要建立PII回傳的規則。 如需詳細資訊，請參閱 [PII回傳](../../administration/using/configuring-rules-launch.md#pii-postback).

### 使用iOS {#enrich-mobile-profile-custom-ios}

在iOS中， [!DNL Experience Platform API] 為必要項目：

* collectPII <br> 如需詳細資訊，請參閱collectPII。

以下是此使用案例的範例實作(搭配iOS):

```
ACPCore.collectPii(["pushPlatform":"apns", "email":email, "firstName":firstName, "lastName":lastName])
```

### 使用Android {#enrich-mobile-profile-custom-android}

在Android中， [!DNL Experience Platform API] 為必要項目：

* collectPII <br> 如需詳細資訊，請參閱collectPII。

以下是此Android使用案例的範例實作：

```
HashMap<String, String> data = new HashMap<>();
data.put("pushPlatform", "gcm");
data.put("firstName", firstNameText); 
data.put("lastName", lastNameText); 
data.put("email", emailText); 
MobileCore.collectPii(data);
```

## 使用應用程式的生命週期資料豐富行動設定檔 {#enrich-mobile-profile-lifecycle}

若要讓此使用案例發揮作用，您需要建立PII回傳的規則。 如需詳細資訊，請參閱 [PII回傳](../../administration/using/configuring-rules-launch.md#pii-postback).

>[!NOTE]
>
>Adobe Campaign不會區分自訂資料或行動應用程式的生命週期資料。 這兩種資料都可使用collectPii回傳規則，以回應行動應用程式中的事件，傳送至伺服器。

### 使用iOS {#enrich-mobile-profile-lifecycle-ios}

在iOS中， [!DNL Experience Platform APIs] 為必要項目：

* **[!UICONTROL Lifecycle Start]**、應用程式啟動時，以及應用程式於前景執行時。
* **[!UICONTROL Lifecycle Pause]**，而非應用程式於背景時。

如需詳細資訊，請參閱 [iOS中的生命週期擴充功能](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/ios/).

以下是此使用案例的範例實作(搭配iOS):

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

在Android中， [!DNL Experience Platform APIs] 為必要項目：

* **[!UICONTROL OnResume]**
* **[!UICONTROL OnPause]**

如需詳細資訊，請參閱 [Android中的生命週期擴充功能](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/android/).

以下是此Android使用案例的範例實作：

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

## 透過推播通知追蹤使用者互動 {#track-user-push}

您必須建立推播通知追蹤回傳的規則。 如需詳細資訊，請參閱 [推播通知追蹤回傳](../../administration/using/configuring-rules-launch.md#push-tracking-postback).

### 使用iOS {#track-user-push-ios}

在iOS中， [!DNL Experience Platform SDK] 為必要項目：

* **[!UICONTROL trackAction]**. 如需詳細資訊，請參閱 [追蹤應用程式動作](https://developer.adobe.com/client-sdks/documentation/mobile-core/api-reference/#trackaction).

以下是此使用案例的範例實作(搭配iOS):

```
let deliveryId = userInfo["_dId"] as? String
let broadlogId = userInfo["_mId"] as? String
if (deliveryId != nil && broadlogId != nil) {
    ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
}
```

### 使用Android {#track-user-push-android}

在Android中， [!DNL Experience Platform SDK] 為必要項目：

* **[!UICONTROL trackAction]**
如需詳細資訊，請參閱 [追蹤應用程式動作](https://developer.adobe.com/client-sdks/documentation/mobile-core/api-reference/#trackaction).

以下是此Android使用案例的範例實作：

```
contextData.put("deliveryId", deliveryId);
contextData.put("broadlogId", messageId);
contextData.put("action", "2");
MobileCore.trackAction("tracking", contextData);
```

## 在您的應用程式中實作自訂事件以觸發應用程式內訊息 {#custom-event-inapp}

### 使用iOS {#custom-event-inapp-ios}

在iOS中， [!DNL Experience Platform SDK] 為必要項目：

* **[!UICONTROL trackAction]**. 如需詳細資訊，請參閱 [追蹤應用程式動作](https://developer.adobe.com/client-sdks/documentation/mobile-core/api-reference/#trackaction).

以下是此使用案例的範例實作(搭配iOS):

```
ACPCore.trackAction(mobileEventName, data: [:] )
```

### 使用Android {#custom-event-inapp-android}

在Android中， [!DNL Experience Platform SDK] 為必要項目：

* **[!UICONTROL trackAction]**
如需詳細資訊，請參閱 [追蹤應用程式動作](https://developer.adobe.com/client-sdks/documentation/mobile-core/api-reference/#trackaction).

以下是此Android使用案例的範例實作：

```
MobileCore.trackAction(mobileEventText, new HashMap<String,String>());
```

## 設定其他驗證的連結欄位 {#linkage-fields-inapp}

### 使用iOS {#linkage-fields-inapp-ios}

若要為以iOS中的應用程式內訊息為基礎的設定檔範本設定其他驗證的連結欄位，請執行下列動作 [!DNL Experience Platform SDK] 為必要項目：

* 設定連結欄位 <br>如需詳細資訊，請參閱 [設定連結欄位](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/api-reference/#setlinkagefields).
* 重置連結欄位 <br>如需詳細資訊，請參閱 [重置連結欄位](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/api-reference/#setlinkagefields).

以下是此使用案例在iOS中的範例實作。

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

若要為以Android中的應用程式內訊息為基礎的設定檔範本設定額外驗證的連結欄位，需要下列Experience PlatformSDK:

* 設定連結欄位 <br>如需詳細資訊，請參閱 [設定連結欄位](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/api-reference/#setlinkagefields).
* 重置連結欄位 <br>如需詳細資訊，請參閱 [重置連結欄位](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/api-reference/#resetlinkagefields).

以下是此使用案例在Android中的範例實作。

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
