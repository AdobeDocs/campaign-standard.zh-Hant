---
solution: Campaign Standard
product: campaign
title: 設定API存取
description: 瞭解如何設定Campaign StandardAPI的存取權。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: 資料工程師
level: 經驗豐富
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '365'
ht-degree: 1%

---


# 設定 API 存取 {#setting-up-api-access}

Adobe Campaign StandardAPI存取權是透過下列步驟設定。 [AdobeIO文檔](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)中詳細介紹了這些步驟。

>[!IMPORTANT]
>
>要在AdobeIO中管理證書，請確保您擁有組織的<b>系統管理員</b>權限，或在管理控制台中擁有[開發人員帳戶](https://helpx.adobe.com/enterprise/using/manage-developers.html)</a>權限。

1. **檢查您是否有數位憑證**，或視需要建立憑證。在下列步驟中，需要隨憑證提供的公開金鑰和私密金鑰。
1. **在Adobe CampaignIO中建立與Adobe** 服務的新整合併對其進行配置。然後會產生您的認證（API金鑰、用戶端密碼……）。
1. **從先前產生的認證建立JSON網** 頁Token(JWT)，並使用您的私密金鑰簽名。JWT會對Adobe驗證身分並授予您API存取權所需的所有身分與安全資訊進行編碼。
1. **通過POST請求將JWT交換為訪** 問代號。此存取Token必須用於API請求的每個標題中。

要建立安全的服務對服務Adobe I/OAPI會話，對Adobe服務的每個請求都必須在「授權」標題中包含以下資訊。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

* **&lt;organization>**:這是您的個人組織ID,Adobe會為每個例項提供一個組織ID:

   * &lt;organization> :您的生產實例，
   * &lt;organization-mkt-stage>:您的舞台實例。

   若要取得您的組織ID值，請洽詢您的管理員或Adobe技術聯絡人。 在建立新整合時，您也可以在許可證清單(請參見<a href="https://www.adobe.io/authentication.html">AdobeIO文檔</a>)中將其檢索到Adobe I/O中。

* **&lt;access_token>**:透過POST請求交換JSON Web Token時擷取的個人存取Token。

* **&lt;api_key>**:您的個人API金鑰。在建立與Adobe Campaign服務的新整合後，它會以Adobe I/O方式提供。

   ![alt text](assets/tenant.png)

## 疑難排解

在AdobeIO整合期間，如果出現下列錯誤：

```
{ 
"code": 502, 
"message": "Oops. Something went wrong. Check your URI and try again." 
}
```


請洽詢您的管理員或Adobe技術聯絡人，以檢查CNAME參數是否建立正確。