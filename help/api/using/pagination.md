---
title: 分頁
description: 了解如何執行分頁作業。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: d6ebce3c-1e84-4b3b-a68d-90df4680af64
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 1%

---

# 分頁

依預設，清單中會載入25個資源。

**_lineCount**&#x200B;參數可讓您限制回應中列出的資源數量。  然後，您可以使用&#x200B;**next**&#x200B;節點來顯示下一個結果。

>[!NOTE]
>
>請一律使用&#x200B;**next**&#x200B;節點中傳回的URL值來執行分頁請求。
>
>會計算&#x200B;**_lineStart**&#x200B;要求，且必須一律用於&#x200B;**next**&#x200B;節點中傳回的URL中。

<br/>

***範例要求***

顯示設定檔資源1個記錄的GET請求範例。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile?_lineCount=1 \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

回應請求，並搭配&#x200B;**next**&#x200B;節點執行分頁。

```
{
    "content": [
        {
            "PKey": "<PKEY>",
            "firstName": "John",
            "lastName":"Doe",
            "birthDate": "1980-10-24",
            ...
        }
    ],
    "next": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email?_lineCount=10&_
        lineStart=@Qy2MRJCS67PFf8soTf4BzF7BXsq1Gbkp_e5lLj1TbE7HJKqc"
    }
    ...
}
```

預設情況下，與具有大量資料的表交互時，**next**&#x200B;節點不可用。 若要執行分頁，您必須將&#x200B;**_forcePagination=true**&#x200B;參數新增至呼叫URL。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile?_forcePagination=true \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

>[!NOTE]
>
>Campaign Standard **XtkBigTableThreshold**&#x200B;選項中定義了表被視為大的記錄數。 預設值為100,000筆記錄。
