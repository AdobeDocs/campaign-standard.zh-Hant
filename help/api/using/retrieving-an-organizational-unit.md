---
solution: Campaign Standard
product: campaign
title: 擷取設定檔的組織單位
description: 瞭解如何使用API來瞭解個人檔案的組織單位。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: 資料工程師
level: 經驗豐富
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '83'
ht-degree: 13%

---


# 擷取設定檔的組織單位 {#retrieving-organizational-units}

1. 對配置檔案PKey執行GET請求以檢索&#x200B;**orgUnit** URL。
1. 在URL上執行GET請求，以擷取有關組織單位的詳細資訊。

<br/>

***請求範例***

擷取描述檔記錄。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

它返回配置檔案的orgUnit URL。

```
{
  ...
  "orgUnit": {
    "PKey": "<PKEY>",
    "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/orgUnitBase/<PKEY>",
    "title": "All (all)"
    },
  ...
}
```

對URL執行GET請求以擷取更多資訊。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/orgUnitBase/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

它返回有關組織單位的詳細資訊。

```
{
  "PKey": "<PKEY>",
  "created": "2019-04-02 22:36:13.252Z",
  "desc": "",
  "label": "Brand 4",
  "lastModified": "2019-04-03 08:17:19.100Z",
  "name": "brand4",
  "parentTitle": "All (all)",
  "title": "Brand 4 (brand4)"
}
```
