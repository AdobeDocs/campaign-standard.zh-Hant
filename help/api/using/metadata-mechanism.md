---
title: 中繼資料機制
description: 進一步了解中繼資料機制。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 58ec0999-b28a-4198-8d57-729b074c6a6d
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 1%

---

# 中繼資料機制 {#metadata-mechanism}

您可以使用 **resourceType** 在GET請求中：

`GET /profileAndServices/resourceType/<resourceName>`

回應會從資源傳回主要中繼資料（所有其他欄位都是描述性或內部欄位）:

* 此 **內容** 節點返回資源的欄位。 針對 **內容** 節點，我們可以找到下列欄位：

   * &quot;apiName&quot;:API中使用的屬性名稱。
   * &quot;type&quot;:這是高階類型定義（字串、數字、連結、集合、列舉……）。
   * &quot;dataPolicy&quot;:欄位的值必須遵循指定的策略規則。 例如，如果dataPolicy規則設為「email」，則值必須是有效的電子郵件。 在PATCH或POST期間，dataPolicy可以檢查值或修改要轉換的值（例如，smartCase）。
   * &quot;category&quot;:提供查詢編輯器中欄位的類別。
   * &quot;resType&quot;:這是技術類型。

      如果以「link」或「collection」值完成「type」，resTarget值即為連結所定位之資源的名稱。
如果以值「enumeration」完成「type」，則會新增「values」欄位，且每個分項清單在 **值** 節點。

* 此 **篩選器** node會傳回URL以擷取相關聯的篩選器。 如需篩選器的詳細資訊，請參閱 [本節](../../api/using/filtering.md) 區段。

<!-- créer une section au même niveau sur les liens -->
<!-- dans l'exemple: birthdate, email +  mettre 2 liens : un de type 1-1 , 1-N
si on prend l'exemple de l'org unit, on aura un bon exemple lien -->
<!-- plus reparler du node Data -->

<br/>

***範例要求***

對資源執行GET請求。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/resourceType/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

它會傳回設定檔資源的完整說明。

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
