---
title: 建立隱私權要求
description: 瞭解如何使用API建立隱私權要求
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: aee0e0437cbfe578cb2f715a2433099c79dd1748

---


# 建立隱私權要求 {#creating-a-privacy-request}

>[!CAUTION]
>
>隱 [私權核心服務](https://adobe.io/apis/cloudplatform/gdpr.html) 「整合」是您應用於所有存取和刪除要求的方法。 從19.4開始，已不再使用促銷活動API和介面來存取和刪除請求。 如需Campaign Standard已停用和移除功能的詳細資訊，請參 [閱此頁](https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html)。

隱私權要求是使用 **POST要求** 。

在建立請求之前，您必須先定義要使用的命名空間。 如需詳細資訊，請參閱隱私 [權管理檔案](https://helpx.adobe.com/campaign/kb/acs-privacy.html#ManagingPrivacyRequests)。

裝載必須包含下列參數：

* **名稱**:唯一的內部名稱
* **namespace**:在Campaign Standard介面中設定的命名空間名稱
* **reconsiblitionValue**:基於命名空間中定義的協調鍵的協調值
* **標籤**:請求標籤
* **類型**:請求類型。 接受的值是「存取」或「刪除」。
* **規章**:監管類型。 範例：「GDPR」、「CCPA」。 此參數為必要參數，且可從Campaign Standard 19.4版開始使用。 如果您使用舊版軟體，則不需要將它新增至裝載。

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
