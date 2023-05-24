---
title: 自訂資源
description: 瞭解有關使用API進行自定義資源管理的詳細資訊/
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: d7b2231d-46ff-4966-9ea7-27a775e5236b
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '204'
ht-degree: 5%

---

# 自訂資源 {#custom-resources}

Adobe Campaign提供了一個預定義的資料模型，資料通過不同的資源進行定義。 您可以通過擴展資源來添加您自己的自定義欄位或自定義表（如採購表或產品表）來豐富所提供的資料模型。

可通過API使用 **/profileAndServicesExt** 終結點和自定義資源名稱。

`https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/<resourceName>/`

>[!NOTE]
>
>對於非現成資源，請始終使用 <b>&quot;cus&quot;</b> 資源名稱前的前置詞。

只要自定義資源連結到「配置檔案」(Profile)表，您就可以使用它們執行任何操作。 例如，讓我們考慮下面的表結構：

![替代文字](assets/cusresources.png)

在這種情況下， **交易記錄**。 **事務詳細資訊** 和 **產品** 只要表連結到 **配置檔案** 的子菜單。

<br/>

***示例請求***

訪問擴展profileAndServicesExt資源的GET請求示例。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/\
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
```

它返回所有連結的自定義資源的清單。 然後，可以使用資源URL執行本文檔中描述的任何API任務。

```
{
"apiName": "resourceType",
"cusProduct": {
        "content": ...,
        "data": "/profileAndServicesExt/cusProduct/",
        "help": "Product",
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/cusProduct/metadata",
        "name": "cusProduct",
        "type": "collection"
    },
"cusTransaction": {
        "content": ...,
        "data": "/profileAndServicesExt/cusTransaction/",
        "help": "Product",
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/cusTransaction/metadata",
        "name": "cusProduct",
        "type": "collection"
    },
    ...
}
```

有關資料模型擴展的詳細資訊，請參閱市場活動文檔：

* [資料模型概念](../../developing/using/data-model-concepts.md)
* [擴展API](../../developing/using/about-extending-the-api.md)
* [定義與其他資源的連結](https://helpx.adobe.com/campaign/standard/developing/using/configuring-the-resource-s-data-structure.html#defining-links-with-other-resources)
