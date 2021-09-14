---
title: 自訂資源
description: 進一步了解使用API進行自訂資源管理/
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

Adobe Campaign隨附預先定義的資料模型，其中資料會透過不同資源加以定義。 您可以擴充資源，新增您自己的自訂欄位或自訂表格（例如購買或產品表格），以豐富資料模型。

自訂資源可透過API使用&#x200B;**/profileAndServicesExt**&#x200B;端點和自訂資源名稱來存取。

`https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/<resourceName>/`

>[!NOTE]
>
>對於非現成的資源，請一律在資源名稱前使用<b>&quot;cus&quot;</b>前置詞。

只要自訂資源連結至「設定檔」表格，您就可以使用自訂資源執行任何操作。 例如，讓我們考慮下清單格結構：

![替代文字](assets/cusresources.png)

在這種情況下，來自&#x200B;**Transaction**、**TransactionDetails**&#x200B;和&#x200B;**Product**&#x200B;表的所有資源都可用，只要它們連結到&#x200B;**Profile**&#x200B;表。

<br/>

***範例要求***

存取擴充profileAndServicesExt資源的GET要求範例。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/\
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
```

它會傳回所有連結的自訂資源清單。 然後，您就可以使用資源URL來執行本檔案中所述的任何API任務。

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

如需資料模型擴充功能的詳細資訊，請參閱Campaign檔案：

* [資料模型概念](../../developing/using/data-model-concepts.md)
* [擴充API](../../developing/using/about-extending-the-api.md)
* [定義與其他資源的連結](https://helpx.adobe.com/campaign/standard/developing/using/configuring-the-resource-s-data-structure.html#defining-links-with-other-resources)
