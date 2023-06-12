---
title: 分頁
description: 瞭解如何執行分頁作業。
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

此 **_lineCount** 引數可讓您限制回應中列出的資源數量。  然後，您可以使用 **下一個** 節點以顯示下一個結果。

>[!NOTE]
>
>一律使用中傳回的URL值 **下一個** 節點，以執行分頁要求。
>
>此 **_lineStart** 會計算請求，且必須一律用於 **下一個** 節點。

<br/>

***範例請求***

顯示設定檔資源1個記錄的範例GET要求。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile?_lineCount=1 \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

使用對請求的回應 **下一個** 節點以執行分頁。

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

根據預設， **下一個** 節點在與具有大量資料的表格互動時無法使用。 若要執行分頁，您必須新增 **_forcePagination=true** 引數至呼叫URL。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile?_forcePagination=true \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

>[!NOTE]
>
>表格被視為大型的記錄數會定義在Campaign Standard中 **XtkBigTableThreshold** 選項。 預設值為100,000筆記錄。
