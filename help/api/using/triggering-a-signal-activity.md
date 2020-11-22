---
solution: Campaign Standard
product: campaign
title: 觸發信號活動
description: 瞭解如何使用API觸發訊號活動。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 2%

---


# 觸發信號活動 {#triggering-a-signal-activity}

在Adobe Campaign Standard工作流程中，可能有一或多個外部 **訊號** 。 這些活動是等待觸發的&quot;聽眾&quot;。

Campaign Standard API可讓您觸發 **External Signal** 活動來呼叫工作流程。 API呼叫可包含將納入工作流程事件變數的參數（要定位的對象名稱、要匯入的檔案名稱、訊息內容的一部分等）。 如此，您就可輕鬆將Campaign自動化與外部系統整合。

>[!NOTE]
>
>外部信號活動無法比每10分鐘更頻繁地觸發，而且目標工作流必須已運行。

要觸發工作流，請執行以下步驟：

1. 對工作流 **程執行GET** 要求，以擷取「外部訊號」活動觸發URL。

   `GET https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>`

1. 在傳 **回的URL上執行POST** 要求，以觸發訊號活動，並在裝載 **中使用** 「source」參數。 此屬性為必填屬性，可讓您指出觸發請求來源。

如果您想要使用參數呼叫工作流程，請使用「參數」屬性將 **它們新增至裝載** 。 語法由參數的名稱及其值組成(支援下列類型： **字串**、 **數字**、 **布爾****和日期／時間**)。

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
>將參數新增至負載時，請確定其名 **稱****** 和類型值與「外部信號」活動中宣告的資訊一致。 此外，有效載荷大小不應超過64Ko。

<br/>

***請求範例***

對工作流執行GET請求。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

它會傳回工作流程訊號活動和相關的觸發url。

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

若要觸發信號活動，請在觸發URL上使用「來源」執行POST要求。 如果您想使用參數呼叫工作流，請新增「參數」屬性。

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

如果其中一個參數未在「外部信號」活動中宣告，POST請求會傳回以下錯誤，指出缺少哪個參數。

```
RST-360011 An error has occurred - please contact your administrator.
'contentURL' parameter isn't defined in signal activity.
XTK-170006 Unable to parse expression 'HandleTrigger(@name, $(source), $({parameters}))'.
RST-360000 Error while assessing 'HandleTrigger(@name, $(source), $({parameters}))' expression ('xtk:workflow:execution/activities/signal/trigger' resource)
```
