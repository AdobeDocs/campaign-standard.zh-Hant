---
title: 擷取訂閱
description: 了解如何使用API擷取訂閱。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 6d935074-3196-45c5-97cd-ccb7c80bbba8
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 2%

---

# 擷取訂閱 {#retrieving-subscriptions}

## 擷取訂閱服務的設定檔

這是兩步驟的程式。

1. 擷取所需服務的訂閱URL。
1. 對訂閱URL執行GET要求。 它會傳回服務的訂閱清單，以及每個相關聯的設定檔。

>[!CAUTION]
>
>REST API會傳回「href」屬性，其中包含要使用的URL。 <b>請一律使用回應中包含的URL，以提出後續的API要求</b>.

<br/>

***範例要求***

執行GET請求以檢索服務。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

它會傳回服務的訂閱URL。

```
  {
    ...
    "messageType": "email",
    "name": "SVC1",
    "subscriptions": {
                "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>/subscriptions/"
    },
    ...
  },
```

對訂閱URL執行GET要求。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>/subscriptions \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

服務的訂閱清單隨即顯示，每個相關聯的設定檔。

```
  {
    ...
    "service": ...,
    "serviceName": "SVC3",
    "subscriber": {
        "PKey": "<PKEY>",
        "email": "",
        "firstName": "John",
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY>",
        "lastName": "Doe",
    },
  }
```

## 擷取設定檔訂閱的服務

這是兩步驟的程式。

1. 擷取指定設定檔的訂閱URL。
1. 對URL執行GET要求。 它會傳回設定檔的訂閱清單，以及每個相關聯的服務。

<br/>

***範例要求***

執行GET請求以擷取設定檔。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

它會傳回設定檔的訂閱URL。

```
  {
    ...
    "postalAddress":...,
    "preferredLanguage": "none",
    "subscriptions": {
      "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY>/subscriptions/"
    },
    ...
  }
```

對訂閱URL執行GET要求。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY>/subscriptions \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

它會傳回設定檔所訂閱的服務清單。

```
  {
    ...
    "PKey": "<PKEY>",
    "created": "2017-03-03 10:54:00.363Z",
    "service": {
      "PKey": "<PKEY>",
      "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>",
      "label": "Sport Newsletter",
      "name": "SVC1",
      "title": "Sport Newsletter (SVC1)"
    },
    ...
  }
```
