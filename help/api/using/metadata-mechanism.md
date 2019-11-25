---
title: 中繼資料機制
description: 進一步瞭解中繼資料機制。
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


# 中繼資料機制 {#metadata-mechanism}

您可以使用GET請求中的 **resourceType** ，擷取資源中繼資料：

`GET /profileAndServices/resourceType/<resourceName>`

回應會從資源傳回主要中繼資料（所有其他欄位皆為描述性或內部）:

* 「內 **容** 」節點返回資源的欄位。 對於內容節點中的 **每個欄位** ，我們可以找到以下欄位：

   * "apiName":API中使用的屬性名稱。
   * 「類型」:這是高階類型定義（字串、數字、連結、集合、列舉……）。
   * "dataPolicy":欄位的值必須遵循給定的策略規則。 例如，若dataPolicy規則設為「email」，則值必須是有效的電子郵件。 在PATCH或POST期間，dataPolicy可以檢查值或修改要轉換的值（例如，smartCase）。
   * 「類別」:給出查詢編輯器中欄位的類別。
   * "resType":這是技術類型。

      如果「type」已填入值「link」或「collection」,resTarget值即為連結所定位之資源的名稱。
如果「type」已完成，且值為「enumeration」，則會新增「values」欄位，而每個enumeration值都會在值節點中詳 **細說** 明。

* 「篩 **選器** 」節點會傳回URL以擷取相關的篩選器。 For more on filters, refer to [this section](../../api/using/filtering.md) section.

<!-- créer une section au même niveau sur les liens -->
<!-- dans l'exemple: birthdate, email +  mettre 2 liens : un de type 1-1 , 1-N
si on prend l'exemple de l'org unit, on aura un bon exemple lien -->
<!-- plus reparler du node Data -->

<br/>

***請求範例***

對資源執行GET請求。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/resourceType/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

它會傳回描述檔資源的完整說明。

```
{
...
"content": {
  "email": {...},
    ...
    },
"data": "/profileAndServices/profile/",
"filters": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/resourceType/<PKEY>"
    },
"help": "Identified profiles",
"href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/metadata",
"label": "Profiles",
"mandatory": false,
"name": "profile",
"pkgStatus": "never",
"readOnly": false,
"schema": "nms:recipient",
"type": "item"
}
```
