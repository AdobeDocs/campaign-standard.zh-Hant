---
title: 設定API存取
description: 瞭解如何設定Campaign Standard API的存取權。
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
ht-degree: 2%

---

# 設定 API 存取 {#setting-up-api-access}

Adobe Campaign Standard API存取權是透過下列步驟設定。 這些步驟的詳細內容請參見 [Adobe Developer檔案](https://developer.adobe.com/developer-console/docs/guides/#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!IMPORTANT]
>
>若要管理中的憑證 [Adobe Developer](https://developer.adobe.com/)，確定您擁有 **系統管理員** 對組織或的許可權 [開發人員帳戶](https://helpx.adobe.com/enterprise/using/manage-developers.html) 在Admin Console中。

1. **檢查您是否擁有數位憑證**，或視需要建立一個。 以下步驟需要憑證隨附的公開和私密金鑰。
1. **建立與Adobe Campaign服務的新整合** 在 [Adobe Developer](https://developer.adobe.com/) 並加以設定。 接著會產生您的認證（API金鑰、使用者端密碼……）。
1. **建立JSON Web權杖(JWT)** 從先前產生的認證中，並使用您的私密金鑰加以簽署。 JWT會編碼Adobe驗證您的身分並授與您API存取權所需的所有身分和安全資訊。
1. **交換您的JWT以取得存取權杖** 透過POST請求。 此Access Token必須用於API請求的每個標頭。

若要建立安全的服務對服務Adobe I/OAPI工作階段，對Adobe服務的每個請求都必須在Authorization標頭中包含以下資訊。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

* **&lt;organization>**：這是您的個人組織ID，Adobe會為每個執行個體提供一個組織ID：

   * &lt;organization> ：您的生產執行個體，
   * &lt;organization-mkt-stage>：您的階段執行個體。

   若要取得組織ID值，請洽詢您的管理員或您的Adobe技術連絡人。 您也可以在建立新整合時，在授權清單中將其擷取到Adobe I/O中(請參閱 <a href="https://developer.adobe.com/developer-console/docs/guides/authentication/">Adobe Developer檔案</a>)。

* **&lt;access_token>**：您的個人存取權杖，這是在透過POST要求交換您的JSON Web Token時擷取的。

* **&lt;api_key>**：您的個人API金鑰。 在建立與Adobe Campaign服務的新整合後，以Adobe I/O提供。

   ![替代文字](assets/tenant.png)

## 疑難排解

在AdobeIO整合期間，如果出現以下錯誤：

```
{ 
"code": 502, 
"message": "Oops. Something went wrong. Check your URI and try again." 
}
```


請洽詢您的管理員或您的Adobe技術連絡人，以檢查CNAME引數是否正確建立。
