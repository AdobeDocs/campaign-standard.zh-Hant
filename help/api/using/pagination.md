---
solution: Campaign Standard
product: campaign
title: 編頁
description: 瞭解如何執行分頁作業。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 1%

---


# 編頁

依預設，清單中會載入25個資源。

使 **用_lineCount** 參數可以限制響應中列出的資源數。  然後，可以使用下 **一個節** 點來顯示下一個結果。

>[!NOTE]
>
>請務必使用在下一個節點中傳回 **的** URL值來執行分頁請求。
>
>會計 **算_lineStart** 請求，且必須一律用在下一個節點傳回的URL **中** 。

<br/>

***請求範例***

顯示1個描述檔資源記錄的範例GET請求。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile?_lineCount=1 \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

回應請求，下一個節 **點** ，執行分頁。

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

預設情況下， **與具有大量資料** 的表交互時，下一個節點不可用。 若要能夠執行分頁，您必須將 **_forcePagination=true** 參數新增至呼叫URL。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile?_forcePagination=true \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

>[!NOTE]
>
>在Campaign Standard **XtkBigTableThreshold選項中定義表被視為大的記錄數** 。 預設值為100,000條記錄。
