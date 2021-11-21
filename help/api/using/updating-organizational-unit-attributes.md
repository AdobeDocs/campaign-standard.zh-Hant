---
title: 更新組織單位屬性
description: 了解如何更新組織單位屬性
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 90841afd-ebc2-4b6a-895e-a96ef65740d7
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '84'
ht-degree: 11%

---

# 更新組織單位屬性 {#updating-organizational-unit-attributes}

1. 在 **orgUnitBase** 用於檢索組織單位PKey的資源。
1. 在組織單位上執行PATCH請求，並在裝載中更新屬性。

<br/>

***範例要求***

檢索組織單位清單。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/orgUnitBase/ \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

它會傳回所有組織單位。 檢索所需單元的PKey。

```
{
  "PKey": "<PKEY>",
  "created": "2019-04-02 22:36:13.252Z",
  "desc": "",
  "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/orgUnitBase/<PKEY>",
  "label": "Brand 4",
  "lastModified": "2019-04-03 07:34:56.579Z",
  "name": "brand4",
  "parentTitle": "All (all)",
  "title": "Brand 4 (brand1)"
},
```

在組織單位上執行PATCH請求，並在裝載中更新屬性。

```
-X PATCH https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/orgUnitBase/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
-i
-d {
-d "label":"brand1",
-d "name":"brand1"
-d }
```

<!-- + réponse -->
