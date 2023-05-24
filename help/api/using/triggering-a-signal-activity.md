---
title: 觸發訊號活動
description: 瞭解如何使用API觸發信號活動。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 9f94e98f-fe04-4369-8946-1380e02cdece
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 2%

---

# 觸發訊號活動 {#triggering-a-signal-activity}

在Adobe Campaign Standard工作流中，可以有一個或多個 **外部信號** 活動。 這些活動是等待觸發的「監聽器」。

Campaign StandardAPI可觸發 **外部信號** 的子菜單。 API調用可以包括將被引入工作流事件變數（目標的訪問群體名稱、要導入的檔案名、消息內容的一部分等）的參數。 這樣，您就可以輕鬆將促銷活動自動化與外部系統整合。

>[!NOTE]
>
>無法比每10分鐘更頻繁地觸發外部信號活動，並且目標工作流必須已在運行。

要觸發工作流，請執行以下步驟：

1. 執行 **GET** 請求檢索外部信號活動觸發器URL。

   `GET https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>`

1. 執行 **POST** 在返回的URL上請求觸發信號活動， **&quot;源&quot;** 的子目錄。 此屬性是必需的，它允許您指示觸發請求源。

如果要使用參數調用工作流，請使用 **&quot;參數&quot;** 屬性。 語法由參數名稱后跟其值組成(支援以下類型： **字串**。 **數**。 **布爾** 和 **日期/時間**)。

```
  -X POST <TRIGGER_URL>
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>' \
  -H 'Content-Type: application/json;charset=utf-8' \
  -H 'Content-Length:79' \
  -i
  -d {
  -d    "source":"<SOURCE>",
  -d    "parameters":{
  -d      "<PARAMETER_NAME":"<PARAMETER_VALUE>",
  -d      "<PARAMETER_NAME":"<PARAMETER_VALUE>",
  -d      "<PARAMETER_NAME":"<PARAMETER_VALUE>",  
  -d      "<PARAMETER_NAME":"<PARAMETER_VALUE>"
  -d    }
  -d }
```

>[!NOTE]
>
>向負載添加參數時，請確保其 **名稱** 和 **類型** 值與「外部信號」活動中聲明的資訊一致。 此外，有效載荷大小不應超過64Ko。

<br/>

***示例請求***

對工作流執行GET請求。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

它返回工作流信號活動和關聯的觸發器URL。

```
{
"PKey": "<PKEY>",
"activities": {
  "activity": {
    "signal1": {
      ...
      "trigger": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<PKEY>/activities/activity/<PKEY>/trigger/"
        },
        ...
      }
    }
  }
}
```

要觸發信號活動，請在觸發URL上使用「source」執行POST請求。 如果要使用參數調用工作流，請添加「參數」屬性。

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<PKEY>/activities/activity/<PKEY>/trigger \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-i
-d '{
-d "source":"API",
-d "parameters":{
-d    "audience":"audience",
-d    "email":"anna.varney@mail.com",
-d    "template":"05",
-d    "contentURL":"http://www.adobe.com",
-d    "test":"true",
-d    "segmentCode":"my segment",
-d    "attribute":"2019-04-03 08:17:19.100Z"}
-d  }'
```

<!-- + réponse -->

如果某個參數未在「外部信號」活動中聲明，則POST請求將返回以下錯誤，指明缺少哪個參數。

```
RST-360011 An error has occurred - please contact your administrator.
'contentURL' parameter isn't defined in signal activity.
XTK-170006 Unable to parse expression 'HandleTrigger(@name, $(source), $({parameters}))'.
RST-360000 Error while assessing 'HandleTrigger(@name, $(source), $({parameters}))' expression ('xtk:workflow:execution/activities/signal/trigger' resource)
```
