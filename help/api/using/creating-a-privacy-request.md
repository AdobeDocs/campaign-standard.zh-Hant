---
solution: Campaign Standard
product: campaign
title: 建立隱私權請求
description: 瞭解如何使用API建立隱私權要求
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: ad7322905c69f9575e11efc9d8f68cf909dc425f
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 6%

---


# 建立隱私權請求 {#creating-a-privacy-request}

>[!CAUTION]
>
>[隱私核心服務](https://adobe.io/apis/cloudplatform/gdpr.html)整合是您應用於所有存取和刪除請求的方法。 從19.4開始，已不再使用促銷活動API和介面來存取和刪除請求。 有關Campaign Standard已過時和已移除功能的詳細資訊，請參閱[本頁](../../rn/using/deprecated-features.md)。

隱私權請求是使用&#x200B;**POST**&#x200B;請求建立的。

在建立請求之前，您必須先定義要使用的命名空間。 有關詳細資訊，請參閱[隱私權管理文檔](https://helpx.adobe.com/tw/campaign/kb/acs-privacy.html#ManagingPrivacyRequests)。

裝載必須包含下列參數：

* **名稱**:唯一的內部名稱
* **namespace**:在Campaign Standard介面中設定的命名空間名稱
* **reconsibilityValue**:基於命名空間中定義的協調鍵的協調值
* **標籤**:請求標籤
* **類型**:請求類型。接受的值是「存取」或「刪除」。
* **規章**:監管類型。範例：「GDPR」、「CCPA」。 此參數為必要參數，且可從Campaign Standard 19.4版開始使用。 如果您使用舊版軟體，則不需要將它新增至裝載。

<br/>

***請求範例***

此POST要求會根據命名空間AMCDS2中定義的電子郵件協調金鑰，建立隱私權要求：

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

回應POST請求。

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
