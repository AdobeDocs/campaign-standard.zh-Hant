---
title: 管理地理單位
description: 瞭解如何使用API管理地理單位。
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
source-git-commit: c0c0be79613f99a15676343d8ce10d335baf968a

---


# 管理地理單位 {#managing-geographical-units}

>[!CAUTION]
>
>Campaign Standard 18.7版本已淘汰「地理單位」功能。
因此，從18.7版開始，新的「促銷活動標準」例項以及沒有建立地理單位的現有例項，都無法實作此功能。
如需詳細資訊，請參閱「已過時的 <a href="https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html">功能</a> 」頁面。

geoUnit **** Base端點可讓您與地理單位互動，例如，可讓您更新其屬性或更新描述檔的單位。

在擴 **展配置檔案資源時** ，將「地理單位」欄位添加到配置檔案中。 因此，請記得永遠使用profileAndServicesExt **端點** ，與地理單位互動。 如需描述檔資源擴充功能的詳細資訊，請參閱促銷活 [動檔案](https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html#partitioning-profiles)。

## 檢索配置檔案的地理單元

1. 對配置檔案PKey執行GET請求以檢索 **geoUnit** URL。
1. 在URL上執行GET請求，以擷取有關地理單位的詳細資訊。

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

它會傳回描述檔的geoUnit URL。

```
{
  ...
  "geoUnit": {
    "PKey": "@zYV4vIjP1wpBebml6s71hjGiDhs4_gHgbC_UhuJFk8h7XTZxZ5QnZrPnQPEfB__TxwR2ge6sz61D8RR4zvD75CLDZtc<PKEY>",
    "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/orgUnitBase/<PKEY>",
    "title": "All (all)"
    },
  ...
}
```

對URL執行GET要求以擷取更多資訊。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/geoUnitBase/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

它返回有關地理單位的詳細資訊。

```
{
  "PKey": "<PKEY>",
  "created": "2019-04-02 22:36:13.252Z",
  "desc": "Default geographical entity (accessible to everyone)",
  "label": "All",
  "lastModified": "2019-04-03 08:17:19.100Z",
  "name": "all",
  "parentTitle": "",
  "title": "All (all)"
}
```

## 更新配置檔案的地理單位

1. 對geoUnitBase資源執行GET **請求** ，以檢索地理單位PKey。
1. 對配置檔案PKey執行PATCH請求，並在裝載中使用所需的地理單元PKey。

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

## 更新地理單位屬性

1. 對geoUnitBase資源執行GET **請求** ，以檢索地理單位PKey。
1. 對地理單元執行PATCH請求，並在裝載中更新屬性。

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

它返回所有地理單位。 檢索所需單元的PKey。

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

對地理單元執行PATCH請求，並在裝載中更新屬性。

```
-X PATCH https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/orgUnitBase/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
-i
-d {
-d "label":"Asia",
-d "name":"asia"
-d }
```

<!-- + réponse -->
