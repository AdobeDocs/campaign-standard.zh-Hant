---
title: 建立隱私權請求
description: 了解如何使用API建立隱私權要求
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 06ad2e13-922b-4f35-8726-007427125c63
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 22%

---

# 建立隱私權請求 {#creating-a-privacy-request}

>[!CAUTION]
>
>[隱私權核心服務](https://adobe.io/apis/cloudplatform/gdpr.html)整合是您應用於所有存取和刪除請求的方法。 自 19.4 版本以來，不建議使用 Campaign API 和介面來存取和刪除請求。有關 Campaign Standard 已過時和已刪除功能的詳細資訊，請參閱[此頁](../../rn/using/deprecated-features.md)。

隱私權要求是使用&#x200B;**POST**&#x200B;要求建立。

在建立請求之前，您必須定義要使用的命名空間。 如需詳細資訊，請參閱[隱私權管理檔案](https://helpx.adobe.com/tw/campaign/kb/acs-privacy.html#ManagingPrivacyRequests)。

裝載必須包含下列參數：

* **名稱**:唯一的內部名稱
* **命名空間**:在Campaign Standard介面中配置的命名空間名稱
* **reconciliationValue**:調解值是根據命名空間中定義的調解金鑰而定
* **標籤**:請求標籤
* **類型**:請求類型。接受的值為「access」或「delete」。
* **規則**:規範類型。範例：「GDPR」、「CCPA」。 此參數為必要項目，且自Campaign Standard19.4版開始提供。 如果您位在舊的組建中，則不需要將其新增至裝載。

<br/>

***範例要求***

此POST請求會根據命名空間AMCDS2中定義的電子郵件調解金鑰，建立隱私權請求：

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

回應POST要求。

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
