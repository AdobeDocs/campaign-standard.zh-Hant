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
source-git-commit: bee4da592e0b3727949bc44c6e41b81d4e7e73d4
workflow-type: tm+mt
source-wordcount: '369'
ht-degree: 1%

---

# 設定 API 存取 {#setting-up-api-access}

Adobe Campaign Standard API存取權是透過下列步驟設定。 以下各步驟在 [Adobe Developer檔案](https://developer.adobe.com/developer-console/docs/guides/#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!IMPORTANT]
>
>若要在中管理憑證 [Adobe Developer](https://developer.adobe.com/)，確定您 **系統管理員** 組織或 [開發人員帳戶](https://helpx.adobe.com/enterprise/using/manage-developers.html) 在Admin Console中。

1. **確認您擁有數位憑證**，或視需要建立。 下列步驟需要憑證隨附的公開金鑰和私密金鑰。
1. **建立與Adobe Campaign服務的新整合** in [Adobe Developer](https://developer.adobe.com/) 並加以設定。 接著會產生您的認證（API金鑰、用戶端密碼……）。
1. **建立JSON網頁代號(JWT)** 從先前產生的憑證，並使用您的私密金鑰簽署。 JWT會對Adobe驗證身分並授予您API存取權所需的所有身分和安全資訊進行編碼。
1. **將JWT交換為存取權杖** 透過POST要求。 此存取權杖必須用於API請求的每個標題中。

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

   若要取得組織ID值，請洽詢您的管理員或Adobe技術聯絡人。 建立新整合時，您也可以將其擷取至Adobe I/O中，位於授權清單中(請參閱 <a href="https://developer.adobe.com/developer-console/docs/guides/authentication/">Adobe Developer檔案</a>)。

* **&lt;access_token>**:您的個人存取權杖，此權杖是透過POST要求交換JSON網頁權杖時擷取的。

* **&lt;api_key>**:您的個人API金鑰。 會在建立與Adobe Campaign服務的新整合後以Adobe I/O提供。

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
