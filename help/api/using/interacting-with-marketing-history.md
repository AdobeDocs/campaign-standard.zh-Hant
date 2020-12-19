---
solution: Campaign Standard
product: campaign
title: 與行銷歷史記錄互動
description: 瞭解如何與個人檔案的行銷記錄互動。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '147'
ht-degree: 10%

---


# 與行銷歷史記錄互動 {#interacting-with-marketing-history}

**history**端點可讓您與描述檔的行銷歷史記錄互動。
例如，您可以通過這種方式，輕鬆檢索發送到配置檔案的傳送的鏡像頁面。 要執行此操作，請遵循下列步驟：

1. 使用&#x200B;**history**&#x200B;端點和配置檔案的主鍵執行GET。
1. 對傳回的&#x200B;**events** href執行GET請求。
1. 它返回配置式的事件清單，該配置式在&#x200B;**mirrorPage**&#x200B;節點中具有指向鏡像頁的連結。

<br/>

***請求範例***

使用GET請求擷取描述檔的行銷記錄。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/history/"<PKEY>" \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

「事件」節點會傳回URL，讓您存取設定檔中的事件。

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

對傳回的事件href執行GET請求。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/history/<PKEY>/events \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

它返回配置式的事件清單，該配置式具有「mirrorPage」節點中鏡像頁的連結。

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
