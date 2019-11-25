---
title: 編頁
description: 瞭解如何執行分頁作業。
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
source-git-commit: c0c0be79613f99a15676343d8ce10d335baf968a

---


# 編頁

依預設，清單中會載入25個資源。

使 **用_lineCount** 參數可以限制響應中列出的資源數。  然後，可以使用下 **一個節** 點來顯示下一個結果。

>[!NOTE]&gt;
>
>請務必使用在下一個節點中傳回 **的** URL值來執行分頁請求。
>
>會計 **算_lineStart** 請求，且必須一律用在下一個節點傳回的URL **中** 。

<!-- serverside pagination. quand table très longue (au delà de 100.000), on peut plus faire de next. doit utiliser à la place les trucs type lineStart etc. si false: voudra dirre que ça a atteint la limite-->

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

<!-- dans l'exemple, avoir le node "next"-->

回應請求。

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
    ...
}
```
