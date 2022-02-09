---
title: 與行銷歷史記錄互動
description: 瞭解如何與配置檔案的市場營銷歷史記錄交互
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

的 **歷史** endpoint允許您與配置檔案的市場營銷歷史記錄交互。
這樣，您就可以輕鬆地檢索發送到配置檔案的傳遞的鏡像頁面。 要執行此操作，請遵循下列步驟：

1. 使用 **歷史** 端點和配置檔案的主鍵。
1. 對執行GET請求 **事件** href返回。
1. 它返回配置檔案的事件清單，其中包含指向 **鏡像頁** 的下界。

<br/>

***示例請求***

使用GET請求檢索配置檔案的市場營銷歷史記錄。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/history/"<PKEY>" \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

「事件」節點返回URL，該URL允許您訪問配置檔案中的事件。

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

對返回的事件href執行GET請求。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/history/<PKEY>/events \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

它返回配置檔案的事件清單，該配置檔案具有指向「mirrorPage」節點中鏡像頁的連結。

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
