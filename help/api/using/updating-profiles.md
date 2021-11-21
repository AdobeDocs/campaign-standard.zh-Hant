---
title: 更新設定檔
description: 進一步了解如何使用API更新設定檔。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: fa3796ee-a00c-4d70-bf3d-e8d2099f1116
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '94'
ht-degree: 4%

---

# 更新設定檔 {#updating-profiles}

更新設定檔是使用 **PATCH** 請求。

`https://mc.adobe.io/<ORGANIZATION>/campaign/<apiName>/<resourceName>/<PKEY>`

1. 第一步是 **擷取設定檔**.

1. 在第二個請求中，執行 **PATCH請求** 填入填入中已完成的資訊。

1. 若要檢查PATCH要求是否已更新設定檔，我們可以執行最終GET要求。

<br/>

***範例要求***

擷取設定檔的GET請求範例。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY>\
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

要求的回應。

```
{
    "content": [
        {
            "PKey": "<PKEY>",
            "firstName": "Amy",
            "lastName":"Dakota",
            "birthDate": "1980-10-24",
            ...
        }
    ]
}
```

PATCH請求更新「phone」屬性。

```
-X PATCH https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-d '{"phone":"3301020304"}'
```

它會傳回PKEY和URL以擷取更新的設定檔。

```
{
    "PKey": "<PKEY>",
    "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/@2v1dr3ZKJveMDhAdh0MPnh9hNQQ93qb7AW6BNVVKknjwXvTZRBAgUqz1SNcB4ZndgjqOofx3BwBZYBftlmObISoM3rs"
}
```
