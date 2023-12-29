---
title: 使用Adobe Experience Platform SDK在Adobe Campaign Standard中支援的行動使用案例
description: 瞭解如何支援行動使用案例
audience: channels
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 3cd8d756-a271-4e53-8ed0-984ce20298bc
source-git-commit: 597ece8d833a216f0540f801461b08fdc9865024
workflow-type: tm+mt
source-wordcount: '852'
ht-degree: 0%

---

# Adobe Campaign Standard 支援的行動使用案例 {#mobile-use-cases}

在此頁面中，您會找到中支援的所有行動使用案例清單。 [!DNL Adobe Campaign Standard] 使用 [!DNL Adobe Experience Platform SDKs]. 請注意，支援這些使用案例需要安裝和設定 [!DNL Adobe Experience Platform SDKs]， [!DNL tags in Adobe Experience Platform]、和 [!DNL Adobe Campaign Standard]. 如需詳細資訊，請參閱此 [頁面](../../administration/using/configuring-a-mobile-application.md).

Adobe Campaign Standard支援下列使用案例：

* [在Campaign Standard中註冊行動設定檔](../../administration/using/supported-mobile-use-cases.md#register-mobile-profile)
* [傳送推播權杖給Campaign Standard](../../administration/using/supported-mobile-use-cases.md#send-push-token)
* [使用您應用程式的自訂資料擴充行動設定檔](../../administration/using/supported-mobile-use-cases.md#enrich-mobile-profile-custom)
* [使用您應用程式的生命週期資料豐富行動設定檔](../../administration/using/supported-mobile-use-cases.md#enrich-mobile-profile-lifecycle)
* [追蹤使用者與推播通知的互動](../../administration/using/supported-mobile-use-cases.md#track-user-push)
* [在您的行動應用程式中實作自訂事件，以觸發應用程式內訊息](../../administration/using/supported-mobile-use-cases.md#custom-event-inapp)
* [針對以應用程式內訊息為基礎的設定檔範本，設定連結欄位以進行其他驗證](../../administration/using/supported-mobile-use-cases.md#linkage-fields-inapp)

若要設定這些使用案例，您需要下列擴充功能：

* **[!DNL Adobe Campaign Standard]** <br>若要安裝並設定Campaign Standard擴充功能，請參閱 [在資料收集UI中設定Campaign Standard擴充功能](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/#configure-the-campaign-standard-extension).
* **[!DNL Mobile Core]**，會自動安裝。 <br>如需行動核心擴充功能的詳細資訊，請參閱 [行動核心](https://developer.adobe.com/client-sdks/documentation/mobile-core/).
* **[!DNL Profile]**，會自動安裝。 <br>如需設定檔擴充功能的詳細資訊，請參閱 [個人資料](https://developer.adobe.com/client-sdks/documentation/profile/).

## 在Campaign Standard中註冊行動設定檔 {#register-mobile-profile}

### 使用iOS {#register-mobile-profile-ios}

在iOS中，執行下列動作 [!DNL Experience Platform APIs] 必填：

* **[!UICONTROL Lifecycle Start]**，即應用程式啟動時和應用程式處於前景時。
* **[!UICONTROL Lifecycle Pause]**，當應用程式於背景時。

如需詳細資訊，請參閱 [iOS中的生命週期擴充功能](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/ios/).

以下是此使用案例與iOS搭配實施的範例：

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

在Android中，下列 [!DNL Experience Platform APIs] 必填：

* **[!UICONTROL OnResume]**
* **[!UICONTROL OnPause]**

如需詳細資訊，請參閱 [Android中的生命週期擴充功能](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/android/).

以下是此使用案例與Android搭配使用的範例實作：

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

## 傳送推播權杖至Adobe Campaign Standard {#send-push-token}

### 使用iOS {#send-push-token-ios}

在iOS中，執行下列動作 [!DNL Experience Platform SDK] 為必填：

* **[!UICONTROL setPushIdentifier]** <br>如需詳細資訊，請參閱 [setpushidentifier](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/api-reference/).

以下是此使用案例與iOS搭配使用的範例實作：

```
func application(_ application: UIApplication, didRegisterForRemoteNotificationsWithDeviceToken deviceToken: Data) {
  
 // Register Device Token
 ACPCore.setPushIdentifier(deviceToken)
```

### 使用Android {#send-push-token-android}

在Android中，下列 [!DNL Experience Platform SDK] 為必填：

* **[!UICONTROL setPushIdentifier]** <br>如需詳細資訊，請參閱 [setpushidentifier](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/api-reference/).

以下是此使用案例搭配Android使用的範例實作：

```
@Override
public void onNewToken(String token) {
    Log.d(TAG, "Refreshed token: " + token);
    MobileCore.setPushIdentifier(token);
}
```

## 使用您應用程式的自訂資料擴充行動設定檔 {#enrich-mobile-profile-custom}

為了讓此使用案例發揮作用，您需要為PII回傳建立規則。 如需詳細資訊，請參閱 [PII回傳](../../administration/using/configuring-rules-launch.md#pii-postback).

### 使用iOS {#enrich-mobile-profile-custom-ios}

在iOS中，執行下列動作 [!DNL Experience Platform API] 為必填：

* collectPII <br> 如需詳細資訊，請參閱collectPII。

以下是此使用案例與iOS搭配實施的範例：

```
ACPCore.collectPii(["pushPlatform":"apns", "email":email, "firstName":firstName, "lastName":lastName])
```

### 使用Android {#enrich-mobile-profile-custom-android}

在Android中，下列 [!DNL Experience Platform API] 為必填：

* collectPII <br> 如需詳細資訊，請參閱collectPII。

以下是此使用案例與Android搭配使用的範例實作：

```
HashMap<String, String> data = new HashMap<>();
data.put("pushPlatform", "gcm");
data.put("firstName", firstNameText); 
data.put("lastName", lastNameText); 
data.put("email", emailText); 
MobileCore.collectPii(data);
```

## 使用您應用程式的生命週期資料豐富行動設定檔 {#enrich-mobile-profile-lifecycle}

為了讓此使用案例發揮作用，您需要為PII回傳建立規則。 如需詳細資訊，請參閱 [PII回傳](../../administration/using/configuring-rules-launch.md#pii-postback).

>[!NOTE]
>
>Adobe Campaign不會將自訂資料或生命週期資料與行動應用程式區分開來。 這兩種型別的資料都可使用collectPii回傳規則傳送至伺服器，以回應行動應用程式中的事件。

### 使用iOS {#enrich-mobile-profile-lifecycle-ios}

在iOS中，執行下列動作 [!DNL Experience Platform APIs] 必填：

* **[!UICONTROL Lifecycle Start]**，即應用程式啟動時和應用程式處於前景時。
* **[!UICONTROL Lifecycle Pause]**，當應用程式於背景時。

如需詳細資訊，請參閱 [iOS中的生命週期擴充功能](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/ios/).

以下是此使用案例與iOS搭配實施的範例：

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

在Android中，下列 [!DNL Experience Platform APIs] 必填：

* **[!UICONTROL OnResume]**
* **[!UICONTROL OnPause]**

如需詳細資訊，請參閱 [Android中的生命週期擴充功能](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/android/).

以下是此使用案例與Android搭配使用的範例實作：

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

## 追蹤使用者與推播通知的互動 {#track-user-push}

您需要建立推播通知追蹤回傳的規則。 如需詳細資訊，請參閱 [推播通知追蹤回傳](../../administration/using/configuring-rules-launch.md#push-tracking-postback).

### 使用iOS {#track-user-push-ios}

在iOS中，執行下列動作 [!DNL Experience Platform SDK] 為必填：

* **[!UICONTROL trackAction]**. 如需詳細資訊，請參閱 [追蹤應用程式動作](https://developer.adobe.com/client-sdks/documentation/mobile-core/api-reference/#trackaction).

以下是此使用案例與iOS搭配實施的範例：

```
let deliveryId = userInfo["_dId"] as? String
let broadlogId = userInfo["_mId"] as? String
if (deliveryId != nil && broadlogId != nil) {
    ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
}
```

### 使用Android {#track-user-push-android}

在Android中，下列 [!DNL Experience Platform SDK] 為必填：

* **[!UICONTROL trackAction]**
如需詳細資訊，請參閱 [追蹤應用程式動作](https://developer.adobe.com/client-sdks/documentation/mobile-core/api-reference/#trackaction).

以下是此使用案例與Android搭配使用的範例實作：

```
contextData.put("deliveryId", deliveryId);
contextData.put("broadlogId", messageId);
contextData.put("action", "2");
MobileCore.trackAction("tracking", contextData);
```

## 在您的應用程式中實作自訂事件以觸發應用程式內訊息 {#custom-event-inapp}

### 使用iOS {#custom-event-inapp-ios}

在iOS中，執行下列動作 [!DNL Experience Platform SDK] 為必填：

* **[!UICONTROL trackAction]**. 如需詳細資訊，請參閱 [追蹤應用程式動作](https://developer.adobe.com/client-sdks/documentation/mobile-core/api-reference/#trackaction).

以下是此使用案例與iOS搭配實施的範例：

```
ACPCore.trackAction(mobileEventName, data: [:] )
```

### 使用Android {#custom-event-inapp-android}

在Android中，下列 [!DNL Experience Platform SDK] 為必填：

* **[!UICONTROL trackAction]**
如需詳細資訊，請參閱 [追蹤應用程式動作](https://developer.adobe.com/client-sdks/documentation/mobile-core/api-reference/#trackaction).

以下是此使用案例與Android搭配使用的範例實作：

```
MobileCore.trackAction(mobileEventText, new HashMap<String,String>());
```

## 設定連結欄位以進行其他驗證 {#linkage-fields-inapp}

### 使用iOS {#linkage-fields-inapp-ios}

若要根據iOS中的應用程式內訊息設定設定設定檔範本其他驗證的連結欄位，請執行下列動作 [!DNL Experience Platform SDK] 為必填：

* 設定連結欄位 <br>如需詳細資訊，請參閱 [設定連結欄位](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/api-reference/#setlinkagefields).
* 重設連結欄位 <br>如需詳細資訊，請參閱 [重設連結欄位](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/api-reference/#setlinkagefields).

以下是此使用案例與iOS的實施範例。

若要設定連結欄位：

```
var linkageFields = [String: String]()
linkageFields["cusEmail"] = "john.doe@email.com"
ACPCampaign.setLinkageFields(linkageFields)
```

若要重設連結欄位：

```
ACPCampaign.resetLinkageFields(linkageFields)
```

### 使用Android {#linkage-fields-inapp-android}

若要針對以Android應用程式內訊息為基礎之設定檔範本設定連結欄位以進行其他驗證，則需要下列Experience PlatformSDK：

* 設定連結欄位 <br>如需詳細資訊，請參閱 [設定連結欄位](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/api-reference/#setlinkagefields).
* 重設連結欄位 <br>如需詳細資訊，請參閱 [重設連結欄位](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/api-reference/#resetlinkagefields).

以下是此使用案例在Android中的實施範例。

若要設定連結欄位：

```
HashMap<String, String> linkageFields = new HashMap<String, String>();
linkageFields.put("cusEmail", "john.doe@email.com");
Campaign.setLinkageFields(linkageFields);
```

若要重設連結欄位：

```
Campaign.resetLinkageFields()
```
