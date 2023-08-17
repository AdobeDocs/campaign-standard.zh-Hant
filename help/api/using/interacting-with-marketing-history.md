---
title: 與行銷歷史記錄互動
description: 瞭解如何與設定檔的行銷歷史記錄互動
feature: API
role: Data Engineer
level: Experienced
exl-id: 67282d21-b4ed-4af5-b751-848a6d705118
source-git-commit: 64f24fb692754973331b4fb2f7b95e9a6f31cd0d
workflow-type: tm+mt
source-wordcount: '147'
ht-degree: 10%

---

# 與行銷歷史記錄互動{#interacting-with-marketing-history}

此 **history** 端點可讓您與設定檔的行銷記錄互動。
舉例來說，如此一來，您便可輕鬆擷取傳送至設定檔之傳送的映象頁面。 要執行此操作，請遵循下列步驟：

1. 使用執行GET **history** 端點和設定檔的主索引鍵。
1. 在上執行GET要求 **事件** 已傳回href。
1. 它會傳回設定檔的事件清單，其中包含映象頁面於 **mirrorPage** 節點。

<br/>

***範例要求***

使用GET請求擷取設定檔的行銷記錄。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/history/"<PKEY>" \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

「events」節點會傳回URL，讓您存取設定檔上的事件。

```
{
  "PKey": "<PKEY>",
  "firstName": "John",
  "lastName":"Doe",
  "birthDate": "1980-10-24",
  "events": {
    "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/history/<PKEY>/events/",
    "metadata": "subHisto"
    },
}
```

對傳回的事件href執行GET要求。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/history/<PKEY>/events \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

它會傳回設定檔的事件清單，其中包含在「mirrorPage」節點中映象頁面的連結。

```
    {
      "PKey": "<PKEY>",
      "category": "email",
      "date": "2018-05-17 08:44:49.366Z",
      "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/history/<PKEY>/events/<PKEY>",
      "label": "Send via email",
      "mirrorPage": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/history/<PKEY>/events/<PKEY>/mirrorPage/"
      },
      "type": "outbound"
    }
```
