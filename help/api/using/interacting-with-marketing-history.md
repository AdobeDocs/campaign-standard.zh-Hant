---
title: 與行銷歷史記錄互動
description: 瞭解如何與設定檔的行銷歷史記錄互動
feature: API
old-role: Data Architect
role: Developer
level: Experienced
exl-id: 67282d21-b4ed-4af5-b751-848a6d705118
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '147'
ht-degree: 4%

---

# 與行銷歷史記錄互動{#interacting-with-marketing-history}

**history**端點可讓您與設定檔的行銷歷史記錄互動。
舉例來說，如此一來，您便可輕鬆擷取傳送至設定檔之傳送的映象頁面。 要執行此操作，請遵循下列步驟：

1. 使用&#x200B;**history**&#x200B;端點及設定檔的主要金鑰執行GET。
1. 對傳回的&#x200B;**事件** href執行GET要求。
1. 它會傳回設定檔的事件清單，其中包含在&#x200B;**mirrorPage**&#x200B;節點中映象頁面的連結。

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
