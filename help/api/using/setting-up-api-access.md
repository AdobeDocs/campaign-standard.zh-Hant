---
solution: Campaign Standard
product: campaign
title: 設定API存取
description: 瞭解如何設定Campaign Standard API的存取權。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 1%

---


# 設定 API 存取 {#setting-up-api-access}

Adobe Campaign Standard API存取權是透過下列步驟設定。 這些步驟在 [Adobe IO檔案中有詳細說明](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)。

>[!IMPORTANT]
>
>若要在Adobe IO中管理憑證，請確定您在「管理控制台」中 <b>擁有組織或開發人</b> 員帳戶的系統管 [理員](https://helpx.adobe.com/enterprise/using/manage-developers.html)</a> 權限。

1. **檢查您是否有數位憑證**，或視需要建立憑證。 在下列步驟中，需要隨憑證提供的公開金鑰和私密金鑰。
1. **在Adobe IO中建立與Adobe Campaign Service的新整合** ，並加以設定。 然後會產生您的認證（API金鑰、用戶端密碼……）。
1. **從先前產生的認證建立JSON Web Token(JWT)** ，並使用您的私密金鑰簽名。 JWT會對Adobe驗證您的身分並授與您API存取權所需的所有身分與安全資訊進行編碼。
1. **透過POST要求將JWT交換為存取Token** 。 此存取Token必須用於API請求的每個標題中。

若要建立安全的服務對服務Adobe I/O API作業階段，對Adobe服務的每個要求都必須在「授權」標題中包含下列資訊。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

* **&lt;ORGANIZATION>**:這是您的個人組織ID,Adobe會針對每個例項提供一個組織ID:

   * &lt;ORGANIZATION> :您的生產實例，
   * &lt;ORGANIZATION-mkt-stage>:您的舞台實例。

   若要取得您的組織ID值，請洽詢您的管理員或Adobe技術聯絡人。 建立新整合時，您也可以在授權清單(請參閱 <a href="https://www.adobe.io/authentication.html">Adobe IO檔案</a>)中擷取它至Adobe I/O。

* **&lt;ACCESS_TOKEN>**:透過POST請求交換您的JSON Web Token時擷取的個人存取Token。

* **&lt;API_KEY>**:您的個人API金鑰。 在建立與Adobe Campaign Service的新整合後，Adobe I/O中就會提供此資訊。

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