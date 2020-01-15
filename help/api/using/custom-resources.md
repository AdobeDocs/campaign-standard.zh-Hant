---
title: 自訂資源
description: 進一步瞭解使用API進行自訂資源管理/
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
source-git-commit: 538739417c4ed28ff2991186dac5fb69d1af3afd

---


# 自訂資源 {#custom-resources}

Adobe Campaign隨附預先定義的資料模型，其中資料是透過不同的資源來定義。 您可以擴充資源以新增您自己的自訂欄位或自訂表格（例如購買或產品表格），以豐富所提供的資料模型。

自訂資源可透過使用 **/profileAndServicesExt端點的API** ，以及自訂資源名稱來存取。

`https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/<resourceName>/`

>[!NOTE]
>
>對於非現成可用的資源，請始終在資源名稱前 <b>面使用</b> 「cus」前置詞。

只要自訂資源已連結至「描述檔」表格，您就可以使用自訂資源執行任何作業。 例如，讓我們考慮下清單格結構：

![alt text](assets/cusresources.png)

在這種情況下，只要Transaction **、** TransactionDetails **和** Product **表與Profile表連結，就可以使用TransactionDetails和****** TransactionDetails中的所有資源。

<br/>

***請求範例&#x200B;***

存取擴充設定檔AndServicesExt資源的GET要求範例。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/\
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
```

它會傳回所有連結的自訂資源清單。 然後，您可以使用資源URL來執行本檔案所述的任何API任務。

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

有關資料模型擴充功能的詳細資訊，請參閱促銷活動檔案：

* [資料模型概念](../../developing/using/data-model-concepts.md)
* [擴充API](../../developing/using/about-extending-the-api.md)
* [定義與其他資源的連結](https://helpx.adobe.com/campaign/standard/developing/using/configuring-the-resource-s-data-structure.html#defining-links-with-other-resources)
