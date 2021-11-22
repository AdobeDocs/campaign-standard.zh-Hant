---
title: 觸發訊號活動
description: 了解如何使用API觸發訊號活動。
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

在Adobe Campaign Standard工作流程中，可以有一或多個 **外部信號** 活動。 這些活動是等待觸發的「監聽器」。

Campaign StandardAPI可讓您觸發 **外部信號** 呼叫工作流程的活動。 API呼叫可包含要擷取至工作流程事件變數的參數（要定位的對象名稱、要匯入的檔案名稱、訊息內容的一部分等）。 這樣，您就可以輕鬆整合Campaign自動化與外部系統。

>[!NOTE]
>
>外部訊號活動的觸發頻率不能超過每10分鐘，且目標工作流程必須已執行。

若要觸發工作流程，請遵循下列步驟：

1. 執行 **GET** 要求擷取外部訊號活動觸發器URL。

   `GET https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>`

1. 執行 **POST** 傳回URL上的要求以觸發訊號活動，並搭配 **&quot;source&quot;** 參數。 此屬性為必要屬性，可讓您指出觸發請求來源。

如果您想要使用參數呼叫工作流程，請將它們新增至搭配 **&quot;parameters&quot;** 屬性。 語法由參數的名稱及其值組成(支援下列類型： **字串**, **數字**, **布林值** 和 **日期/時間**)。

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
>將參數新增至裝載時，請確定其 **名稱** 和 **type** 值與外部訊號活動中宣告的資訊一致。 此外，有效載荷大小不應超過64Ko。

<br/>

***範例要求***

在工作流程上執行GET請求。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

它會傳回工作流程訊號活動和相關聯的觸發器url。

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

若要觸發訊號活動，請對具有「來源」的觸發url執行POST要求。 如果您要使用參數呼叫工作流程，請新增「參數」屬性。

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

如果外部訊號活動中未宣告其中一個參數，POST要求會傳回下列錯誤，指出缺少哪個參數。

```
RST-360011 An error has occurred - please contact your administrator.
'contentURL' parameter isn't defined in signal activity.
XTK-170006 Unable to parse expression 'HandleTrigger(@name, $(source), $({parameters}))'.
RST-360000 Error while assessing 'HandleTrigger(@name, $(source), $({parameters}))' expression ('xtk:workflow:execution/activities/signal/trigger' resource)
```
