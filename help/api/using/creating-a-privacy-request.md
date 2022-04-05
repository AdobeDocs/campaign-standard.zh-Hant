---
title: 建立隱私權請求
description: 瞭解如何使用API建立隱私請求
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 06ad2e13-922b-4f35-8726-007427125c63
source-git-commit: 4b0c4fb13cc11c06e2487e531ca96574e49b6beb
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 4%

---

# 建立隱私權請求 {#creating-a-privacy-request}

>[!CAUTION]
>
>的 [隱私核心服務](https://developer.adobe.com/experience-platform-apis/references/privacy-service) 整合是您應用於所有訪問和刪除請求的方法。 <!--Starting 19.4, the use of the Campaign API and interface for access and delete requests is deprecated. For more on Campaign Standard deprecated and removed features, refer to [this page](../../rn/using/deprecated-features.md).-->

使用 **POST** 請求。

在建立請求之前，您需要定義要使用的命名空間。 有關詳細資訊，請參閱 [隱私管理文檔](../../start/using/privacy-requests.md)。

負載必須包含以下參數：

* **名稱**:唯一的內部名稱
* **命名空間**:在Campaign Standard介面中配置的命名空間名稱
* **協調值**:基於命名空間中定義的協調鍵的協調值
* **標籤**:請求標籤
* **類型**:請求類型。 接受的值為&quot;access&quot;或&quot;delete&quot;。
* **規範**:規章類型。 示例：&quot;GDPR&quot;,&quot;CCPA&quot;。 此參數是必需的，可從Campaign Standard19.4版開始使用。 如果您是舊版本，則無需將其添加到負載中。

<br/>

***示例請求***

此POST請求基於命名空間AMCDS2中定義的電子郵件協調密鑰建立隱私請求：

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/privacy/privacyTool \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-H 'Content-Type: application/json;charset=utf-8'

{
"name":"PT11832",
"namespaceName": "AMCDS2",
"reconciliationValue": "customers@adobe.com",
"regulation": "gdpr",
"label":"Delete customers",
"type":"delete"
}
```

響應POST請求。

```
{
    "PKey": "<PKEY>",
    "audit": "",
    "created": "2018-03-21 10:41:58.570Z",
    "desc": "",
    "gdprRequestData": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/head/privacyTool/<PKEY>/gdprRequestData/"
    },
    "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/privacy/privacyTool/<PKEY>",
    "label": "Delete customers",
    "lastModified": "2018-03-21 10:41:58.570Z",
    "name": "PT11832",
    "namespace": {
        "PKey": "<PKEY>",
        "title": "Doc (AMCDS2)"
    },
    "namespaceName": "AMCDS2",
    "reconciliationValue": "customers@adobe.com",
    "regulation": "gdpr",
    "retryCount": 0,
    "status": "new",
    "title": "Delete customers (PT11832)",
    "type": "delete"
}
```
