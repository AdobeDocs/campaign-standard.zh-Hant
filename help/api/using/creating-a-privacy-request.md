---
title: 建立隱私權請求
description: 瞭解如何使用API建立隱私權請求
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
>此 [隱私權核心服務](https://developer.adobe.com/experience-platform-apis/references/privacy-service) 整合是您應用於處理所有存取和刪除要求的方法。 <!--Starting 19.4, the use of the Campaign API and interface for access and delete requests is deprecated. For more on Campaign Standard deprecated and removed features, refer to [this page](../../rn/using/deprecated-features.md).-->

隱私權請求是使用 **POST** 要求。

在建立請求之前，您需要定義要使用的名稱空間。 如需詳細資訊，請參閱 [隱私權管理檔案](../../start/using/privacy-requests.md).

承載必須包含下列引數：

* **名稱**：唯一的內部名稱
* **名稱空間**：在Campaign Standard介面中設定的名稱空間名稱
* **reconciliationvalue**：根據名稱空間中定義的調解金鑰的調解值
* **標籤**：請求標籤
* **type**：要求型別。 接受的值為「存取」或「刪除」。
* **法規**：法規型別。 範例： 「GDPR」、「CCPA」。 此引數為必要項，自Campaign Standard19.4發行版本起即可使用。 如果您使用舊版組建，就不需要將它新增至您的裝載。

<br/>

***範例要求***

此POST請求會根據名稱空間AMCDS2中定義的電子郵件調解金鑰建立隱私權請求：

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

對POST要求的回應。

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
