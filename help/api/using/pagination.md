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

此 **_lineCount** 參數可讓您限制回應中列出的資源數量。  然後，您就可以使用 **next** 節點以顯示下一個結果。

>[!NOTE]
>
>請一律使用 **next** 節點來執行分頁請求。
>
>此 **_lineStart** 請求，且必須一律用於 **next** 節點。

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

回應請求，並搭配 **next** 節點執行分頁。

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

依預設， **next** 與具有大量資料的表交互時，節點不可用。 若要執行分頁，您必須新增 **_forcePagination=true** 參數。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile?_forcePagination=true \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

>[!NOTE]
>
>在Campaign Standard中定義表被視為大的記錄數 **XtkBigTableThreshold** 選項。 預設值為100,000筆記錄。
