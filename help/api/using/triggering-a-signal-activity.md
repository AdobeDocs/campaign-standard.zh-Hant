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

Campaign StandardAPI可讓您觸發 **外部信號** 呼叫工作流程的活動。 API呼叫可包含要擷取至工作流程事件變數的參數（要定位的對象名稱、要匯入的檔案名稱、訊息內容的一部分等）。 This way, you can easily integrate your Campaign automations with your external system.

>[!NOTE]
>
>外部訊號活動的觸發頻率不能超過每10分鐘，且目標工作流程必須已執行。

To trigger a workflow, follow the steps below:

1. 執行 **GET** 要求擷取外部訊號活動觸發器URL。

   `GET https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>`

1. 執行 **POST** 傳回URL上的要求以觸發訊號活動，並搭配 **&quot;source&quot;** 參數。 此屬性為必要屬性，可讓您指出觸發請求來源。

If you want to call the workflow with parameters, add them into the payload with the **&quot;parameters&quot;** attribute. 語法由參數的名稱及其值組成(支援下列類型： **字串**, **數字**, **布林值** 和 **日期/時間**)。

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
>When adding a parameter to the payload, make sure that its **name** and **type** values are consistent with the information declared in the External signal activity. Moreover, the payload size should not exceed 64Ko.

<br/>

***範例要求***

Perform a GET request on the workflow.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

It returns the workflow signal activity and the associated trigger url.

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

若要觸發訊號活動，請對具有「來源」的觸發url執行POST要求。 Add the &quot;parameters&quot; attributes if you want to call the workflow with parameters.

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

If one of the parameters is not declared in the External signal activity, the POST request returns the error below, indicating which parameter is missing.

```
RST-360011 An error has occurred - please contact your administrator.
'contentURL' parameter isn't defined in signal activity.
XTK-170006 Unable to parse expression 'HandleTrigger(@name, $(source), $({parameters}))'.
RST-360000 Error while assessing 'HandleTrigger(@name, $(source), $({parameters}))' expression ('xtk:workflow:execution/activities/signal/trigger' resource)
```
