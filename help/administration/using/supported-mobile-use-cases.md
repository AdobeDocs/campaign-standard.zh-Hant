---
solution: Campaign Standard
product: campaign
title: 使用Adobe Campaign StandardSDK支援的行動使用案例
description: 本檔案提供如何支援行動使用案例的資訊。
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
feature: Instance Settings
role: Administrator
level: Experienced
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '957'
ht-degree: 0%

---


# Adobe Campaign Standard　支援的行動使用案例 {#mobile-use-cases}

在本頁中，您將會找到[!DNL Adobe Campaign Standard]中使用[!DNL Adobe Experience Platform SDKs]支援的每個行動使用案例清單。 請注意，支援這些使用案例需要安裝和設定[!DNL Adobe Experience Platform SDKs]、[!DNL Adobe Experience Platform Launch]和[!DNL Adobe Campaign Standard]。 有關此問題的詳細資訊，請參閱此[頁](../../administration/using/configuring-a-mobile-application.md)。

Adobe Campaign Standard支援以下使用案例：

* [在Campaign Standard中註冊行動設定檔](../../administration/using/supported-mobile-use-cases.md#register-mobile-profile)
* [傳送推播Token至Campaign Standard](../../administration/using/supported-mobile-use-cases.md#send-push-token)
* [運用應用程式的自訂資料豐富行動設定檔](../../administration/using/supported-mobile-use-cases.md#enrich-mobile-profile-custom)
* [運用應用程式的生命週期資料豐富行動設定檔](../../administration/using/supported-mobile-use-cases.md#enrich-mobile-profile-lifecycle)
* [使用推播通知追蹤使用者互動](../../administration/using/supported-mobile-use-cases.md#track-user-push)
* [在行動應用程式中實作自訂事件以觸發應用程式內訊息](../../administration/using/supported-mobile-use-cases.md#custom-event-inapp)
* [為基於應用程式內訊息的描述檔範本設定其他驗證的連結欄位](../../administration/using/supported-mobile-use-cases.md#linkage-fields-inapp)

若要設定這些使用案例，您需要[!DNL Experience Platform Launch]的下列擴充功能：

* **[!DNL Adobe Campaign Standard]** <br>要安裝和配置Campaign Standard擴展，請參 [閱在Experience Platform Launch中配置Campaign Standard擴展](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard#configure-the-campaign-standard-extension-in-experience-platform-launch)。
* **[!DNL Mobile Core]**，會自動安裝。<br>如需行動核心擴充功能的詳細資訊，請參閱 [行動核心](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core)。
* **[!DNL Profile]**，會自動安裝。<br>如需描述檔擴充功能的詳細資訊，請參閱 [描述檔](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/profile)。

## 在{#register-mobile-profile}Campaign Standard中註冊行動設定檔

### 使用iOS {#register-mobile-profile-ios}

在iOS中，需要下列[!DNL Experience Platform APIs]:

* **[!UICONTROL Lifecycle Start]**，當應用程式啟動時，以及應用程式在前景時。
* **[!UICONTROL Lifecycle Pause]**，當應用程式在背景時。

如需詳細資訊，請參閱iOS中的[生命週期擴充功能。](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/lifecycle/lifecycle-extension-in-ios)

以下是iOS中此使用案例的範例實作：

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

在Android中，需要下列[!DNL Experience Platform APIs]:

* **[!UICONTROL OnResume]**
* **[!UICONTROL OnPause]**

如需詳細資訊，請參閱Android中的[生命週期擴充功能](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/lifecycle/lifecycle-extension-in-android)。

以下是Android的此使用案例實作範例：

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

## 傳送推播Token至Adobe Campaign Standard{#send-push-token}

### 使用iOS {#send-push-token-ios}

在iOS中，需要下列[!DNL Experience Platform SDK]:

* **[!UICONTROL setPushIdentifier]** <br>如需詳細資訊，請參 [閱setPushIdentifier](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference#setpushidentifier)。

以下是iOS中此使用案例的範例實作：

```
func application(_ application: UIApplication, didRegisterForRemoteNotificationsWithDeviceToken deviceToken: Data) {
  
 // Register Device Token
 ACPCore.setPushIdentifier(deviceToken)
```

### 使用Android {#send-push-token-android}

在Android中，需要下列[!DNL Experience Platform SDK]:

* **[!UICONTROL setPushIdentifier]** <br>如需詳細資訊，請參 [閱setPushIdentifier](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference#setpushidentifier)。

以下是此Android使用案例的範例實作：

```
@Override
public void onNewToken(String token) {
    Log.d(TAG, "Refreshed token: " + token);
    MobileCore.setPushIdentifier(token);
}
```

## 使用應用程式的自訂資料豐富行動設定檔{#enrich-mobile-profile-custom}

若要使用此使用案例，您必須建立PII回傳的規則。 如需詳細資訊，請參閱[PII回傳](../../administration/using/configuring-rules-launch.md#pii-postback)。

### 使用iOS {#enrich-mobile-profile-custom-ios}

在iOS中，需要下列[!DNL Experience Platform API]:

* collectPII <br>如需詳細資訊，請參閱collectPII。

以下是iOS中此使用案例的範例實作：

```
ACPCore.collectPii(["email":email, "firstName":firstName, "lastName":lastName])
```

### 使用Android {#enrich-mobile-profile-custom-android}

在Android中，需要下列[!DNL Experience Platform API]:

* collectPII <br>如需詳細資訊，請參閱collectPII。

以下是Android的此使用案例實作範例：

```
HashMap<String, String> data = new HashMap<>();
data.put("firstName", firstNameText);
data.put("lastName", lastNameText);
data.put("email", emailText);
MobileCore.collectPii(data);
```

## 使用應用程式的生命週期資料豐富行動設定檔{#enrich-mobile-profile-lifecycle}

若要使用此使用案例，您必須建立PII回傳的規則。 如需詳細資訊，請參閱[PII回傳](../../administration/using/configuring-rules-launch.md#pii-postback)。

>[!NOTE]
>
>Adobe Campaign不會將自訂資料或生命週期資料與行動應用程式區分開來。 這兩種資料都可以使用collectPii回傳規則，以回應行動應用程式中的事件，傳送至伺服器。

### 使用iOS {#enrich-mobile-profile-lifecycle-ios}

在iOS中，需要下列[!DNL Experience Platform APIs]:

* **[!UICONTROL Lifecycle Start]**，當應用程式啟動時，以及應用程式在前景時。
* **[!UICONTROL Lifecycle Pause]**，當應用程式在背景時。

如需詳細資訊，請參閱iOS中的[生命週期擴充功能。](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/lifecycle/lifecycle-extension-in-ios)

以下是iOS中此使用案例的範例實作：

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

在Android中，需要下列[!DNL Experience Platform APIs]:

* **[!UICONTROL OnResume]**
* **[!UICONTROL OnPause]**

如需詳細資訊，請參閱Android中的[生命週期擴充功能](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/lifecycle/lifecycle-extension-in-android)。

以下是Android的此使用案例實作範例：

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

## 使用推播通知追蹤使用者互動{#track-user-push}

您需要建立推播通知追蹤回傳的規則。 如需詳細資訊，請參閱[推播通知追蹤回傳](../../administration/using/configuring-rules-launch.md#push-tracking-postback)。

### 使用iOS {#track-user-push-ios}

在iOS中，需要下列[!DNL Experience Platform SDK]:

* **[!UICONTROL trackAction]**.如需詳細資訊，請參閱[追蹤應用程式動作](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#track-app-actions)。

以下是iOS中此使用案例的範例實作：

```
let deliveryId = userInfo["_dId"] as? String
let broadlogId = userInfo["_mId"] as? String
if (deliveryId != nil && broadlogId != nil) {
    ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
}
```

### 使用Android {#track-user-push-android}

在Android中，需要下列[!DNL Experience Platform SDK]:

* **[!UICONTROL trackAction]**
如需詳細資訊，請參閱「 [追蹤應用程式動作](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#track-app-actions)」。

以下是Android的此使用案例實作範例：

```
contextData.put("deliveryId", deliveryId);
contextData.put("broadlogId", messageId);
contextData.put("action", "2");
MobileCore.trackAction("tracking", contextData);
```

## 在應用程式中實作自訂事件以觸發應用程式內訊息{#custom-event-inapp}

### 使用iOS {#custom-event-inapp-ios}

在iOS中，需要下列[!DNL Experience Platform SDK]:

* **[!UICONTROL trackAction]**.如需詳細資訊，請參閱[追蹤應用程式動作](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#track-app-actions)。

以下是iOS中此使用案例的範例實作：

```
ACPCore.trackAction(mobileEventName, data: [:] )
```

### 使用Android {#custom-event-inapp-android}

在Android中，需要下列[!DNL Experience Platform SDK]:

* **[!UICONTROL trackAction]**
如需詳細資訊，請參閱「 [追蹤應用程式動作](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#track-app-actions)」。

以下是Android的此使用案例實作範例：

```
MobileCore.trackAction(mobileEventText, new HashMap<String,String>());
```

## 設定其他驗證的連結欄位{#linkage-fields-inapp}

### 使用iOS {#linkage-fields-inapp-ios}

若要針對以iOS中的應用程式內訊息為基礎的描述檔範本，設定連結欄位以進行其他驗證，請填寫下列[!DNL Experience Platform SDK]:

* 設定連結欄位<br>有關詳細資訊，請參閱[設定連結欄位](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference#set-linkage-fields)。
* 重設連結欄位<br>有關詳細資訊，請參閱[重設連結欄位](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference#reset-linkage-fields)。

以下是iOS中此使用案例的範例實作。

要設定連結欄位，請執行以下操作：

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

若要設定連結欄位，以針對以Android中應用程式內訊息為基礎的描述檔範本進行其他驗證，必須具備下列Experience PlatformSDK:

* 設定連結欄位<br>有關詳細資訊，請參閱[設定連結欄位](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference#set-linkage-fields)。
* 重設連結欄位<br>有關詳細資訊，請參閱[重設連結欄位](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference#reset-linkage-fields)。

以下是此使用案例在Android中的範例實作。

要設定連結欄位，請執行以下操作：

```
HashMap<String, String> linkageFields = new HashMap<String, String>();
linkageFields.put("cusEmail", "john.doe@email.com");
Campaign.setLinkageFields(linkageFields);
```

要重置連結欄位：

```
Campaign.resetLinkageFields()
```
