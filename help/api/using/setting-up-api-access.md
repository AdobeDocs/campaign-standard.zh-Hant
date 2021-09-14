---
title: 設定API存取
description: 了解如何設定Campaign StandardAPI的存取權。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: efbbd0cd-9c56-4ad0-8bcb-efba4b63c28b
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 1%

---

# 設定 API 存取 {#setting-up-api-access}

Adobe Campaign Standard API存取權是透過下列步驟設定。 在[AdobeIO文檔](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)中詳細說明了這些步驟。

>[!IMPORTANT]
>
>若要在AdobeIO中管理憑證，請確定您在組織上擁有<b>系統管理員</b>權限，或在管理控制台中擁有[開發人員帳戶](https://helpx.adobe.com/enterprise/using/manage-developers.html)</a>權限。

1. **檢查您是否擁有數位憑證**，或視需要建立憑證。下列步驟需要憑證隨附的公開金鑰和私密金鑰。
1. **建立與Adobe Campaign Servicein** AdobeIO的新整合併加以設定。接著會產生您的認證（API金鑰、用戶端密碼……）。
1. **從先前產生的憑證建立JSON網頁代號(JWT)** ，並使用您的私密金鑰簽署。JWT會對Adobe驗證身分並授予您API存取權所需的所有身分和安全資訊進行編碼。
1. **透過POST要求將JWT** 交換為存取代號。此存取權杖必須用於API請求的每個標題中。

若要建立安全的服務對服務Adobe I/OAPI工作階段，對Adobe服務的每個要求都必須在授權標題中包含下列資訊。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

* **&lt;organization>**:這是您的個人組織ID，由Adobe為每個執行個體提供一個組織ID:

   * &lt;organization> :您的生產執行個體，
   * &lt;organization-mkt-stage>:您的stage實例。

   若要取得組織ID值，請洽詢您的管理員或Adobe技術聯絡人。 建立新整合時，您也可以在Adobe I/O清單中(請參閱<a href="https://www.adobe.io/authentication.html">AdobeIO檔案</a>)將其擷取到授權中。

* **&lt;access_token>**:您的個人存取權杖，此權杖是透過POST要求交換JSON網頁權杖時擷取的。

* **&lt;api_key>**:您的個人API金鑰。會在建立與Adobe Campaign服務的新整合後以Adobe I/O提供。

   ![替代文字](assets/tenant.png)

## 疑難排解

在AdobeIO整合期間，如果出現下列錯誤：

```
{ 
"code": 502, 
"message": "Oops. Something went wrong. Check your URI and try again." 
}
```


請洽詢您的管理員或Adobe技術聯絡人，檢查CNAME參數是否已正確建立。
