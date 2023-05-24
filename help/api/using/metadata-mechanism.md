---
title: 中繼資料機制
description: 瞭解有關元資料機制的詳細資訊。
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

可以使用 **資源類型** 在GET請求中：

`GET /profileAndServices/resourceType/<resourceName>`

響應從資源返回主元資料（所有其他欄位都是描述性或內部欄位）:

* 的 **內容** node返回資源的欄位。 對於 **內容** 節點，我們可以找到以下欄位：

   * &quot;apiName&quot;:API中使用的屬性的名稱。
   * &quot;類型&quot;:這是高級類型定義（字串、數字、連結、集合、枚舉……）。
   * &quot;dataPolicy&quot;:欄位的值必須遵循給定的策略規則。 例如，如果dataPolicy規則設定為「email」，則該值必須是有效的電子郵件。 在PATCH或POST期間，dataPolicy可以檢查值或修改要轉換的值（例如，smartCase）。
   * &quot;類別&quot;:給出查詢編輯器中欄位的類別。
   * &quot;resType&quot;:這是技術類型。

      如果「type」以值「link」或「collection」完成，則resTarget值是連結所針對的資源的名稱。
如果「type」用值「enumeration」完成，則會添加「values」欄位，並在中詳細列出每個枚舉值 **值** 的下界。

* 的 **篩選器** 節點返回URL以檢索關聯的篩選器。 有關篩選器的詳細資訊，請參閱 [此部分](../../api/using/filtering.md) 的子菜單。

<!-- créer une section au même niveau sur les liens -->
<!-- dans l'exemple: birthdate, email +  mettre 2 liens : un de type 1-1 , 1-N
si on prend l'exemple de l'org unit, on aura un bon exemple lien -->
<!-- plus reparler du node Data -->

<br/>

***示例請求***

對資源執行GET請求。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/resourceType/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

它返回配置檔案資源的完整說明。

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
