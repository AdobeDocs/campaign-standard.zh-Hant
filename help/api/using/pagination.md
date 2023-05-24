---
title: 分頁
description: 瞭解如何執行分頁操作。
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

預設情況下，將在清單中載入25個資源。

的 **行計數(_L)** 參數允許您限制響應中列出的資源數。  然後，您可以使用 **下** 的子菜單。

>[!NOTE]
>
>始終使用在 **下** 執行分頁請求。
>
>的 **行開始(_L)** 請求是計算的，並且必須始終在返回的URL中使用 **下** 的下界。

<br/>

***示例請求***

顯示配置檔案資源的1條記錄的示例GET請求。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile?_lineCount=1 \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

響應請求， **下** 執行分頁。

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

預設情況下， **下** 與具有大量資料的表交互時，節點不可用。 要能夠執行分頁，必須添加 **_forcePagination=true** 調用URL的參數。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile?_forcePagination=true \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

>[!NOTE]
>
>在Campaign Standard中定義表被視為大的記錄數 **XtkBigTableThreshold** 的雙曲餘切值。 預設值為100,000條記錄。
