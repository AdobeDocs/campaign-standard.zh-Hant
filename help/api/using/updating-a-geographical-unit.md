---
solution: Campaign Standard
product: campaign
title: 更新設定檔的地理單位
description: 瞭解如何使用API管理地理單位。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '98'
ht-degree: 11%

---


# 更新設定檔的地理單位 {#updating-a-geographical-unit}

1. 對&#x200B;**geoUnitBase**&#x200B;資源執行GET請求以檢索地理單元PKey。
1. 對配置檔案PKey執行PATCH請求，並在裝載中使用所需的地理單位PKey。

<br/>

***請求範例***

檢索地理單位清單。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/geoUnitBase/ \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

它返回所有地理單位。 檢索要向其分配配置檔案的設備的PKey。

```
{
 "PKey": "<PKEY>",
 "created": "2019-04-06 22:36:19.089Z",
 "desc": "",
 "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/geoUnitBase/<PKEY>",
 "label": "Europe",
 "lastModified": "2019-04-06 22:36:19.086Z",
 "name": "eu",
 "parentTitle": "All (all)",
 "title": "Europe (eu)"
},
```

對配置檔案執行PATCH請求，並在裝載中使用所需地理單元的PKey。

```
-X PATCH https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
-i
-d {
-d "geoUnit":{
-d    "PKey":"<PKEY>"
-d  }
-d }
```

<!-- + réponse -->
