---
title: 設定API訪問
description: 瞭解如何設定對Campaign StandardAPI的訪問。
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

Adobe Campaign StandardAPI訪問通過以下步驟設定。 以下每個步驟均在 [Adobe Developer文檔](https://developer.adobe.com/developer-console/docs/guides/#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)。

>[!IMPORTANT]
>
>在中管理證書 [Adobe Developer](https://developer.adobe.com/)，確保 **系統管理員** 組織或 [開發者帳戶](https://helpx.adobe.com/enterprise/using/manage-developers.html) Admin Console。

1. **檢查您有數字證書**，或根據需要建立。 在以下步驟中需要隨證書提供的公鑰和私鑰。
1. **建立與Adobe Campaign服務的新整合** 在 [Adobe Developer](https://developer.adobe.com/) 並配置。 然後將生成您的憑據（API密鑰、客戶端密鑰……）。
1. **建立JSON Web令牌(JWT)** 從先前生成的憑據中，使用您的私鑰進行簽名。 JWT對Adobe驗證身份和授予您訪問API的權限所需的所有身份和安全資訊進行編碼。
1. **將JWT交換為訪問令牌** 通過POST。 此訪問令牌必須用於API請求的每個標頭。

要建立安全的服務到服務Adobe I/OAPI會話，對Adobe服務的每個請求都必須在「授權」標頭中包含以下資訊。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

* **&lt;organization>**:這是您的個人組織ID,Adobe為每個實例提供一個組織ID:

   * &lt;organization> :生產實例，
   * &lt;organization-mkt-stage>:您的階段實例。

   要獲取您的組織ID值，請咨詢您的管理員或Adobe技術聯繫人。 建立新整合時，您還可以在許可證清單中將其檢索到Adobe I/O(請參見 <a href="https://developer.adobe.com/developer-console/docs/guides/authentication/">Adobe Developer文檔</a>)。

* **&lt;access_token>**:通過POST請求交換JSON Web令牌時檢索的個人訪問令牌。

* **&lt;api_key>**:您的個人API密鑰。 在建立與Adobe Campaign服務的新整合後，它以Adobe I/O形式提供。

   ![替代文字](assets/tenant.png)

## 疑難排解

在AdobeIO整合期間，如果出現以下錯誤：

```
{ 
"code": 502, 
"message": "Oops. Something went wrong. Check your URI and try again." 
}
```


請咨詢您的管理員或Adobe技術聯繫人，以檢查CNAME參數是否建立正確。
