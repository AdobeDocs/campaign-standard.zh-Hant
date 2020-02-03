---
title: 與行銷歷史記錄互動
description: 瞭解如何與個人檔案的行銷記錄互動。
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
source-git-commit: e60ec7790da46d234b66baf4c3db23815056b9fb

---


# 與行銷歷史記錄互動 {#interacting-with-marketing-history}

歷史 **記錄端點** ，可讓您與描述檔的行銷記錄互動。
例如，您可以通過這種方式，輕鬆檢索發送到配置檔案的傳送的鏡像頁面。 要執行此操作，請遵循下列步驟：

1. 使用歷史端點 **和配置** 檔案的主鍵執行GET。
1. 對傳回的事件 **href執行** GET請求。
1. 它返回配置式的事件清單，該配置式具有指向 **mirrorPage節點中鏡像頁的鏈** 接。

<br/>

***請求範例&#x200B;***

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
