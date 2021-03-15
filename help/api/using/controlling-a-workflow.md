---
solution: Campaign Standard
product: campaign
title: 控管工作流程
description: 瞭解如何使用API控制工作流程。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: 資料工程師
level: 經驗豐富
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '100'
ht-degree: 10%

---


# 控管工作流程 {#controlling-a-workflow}

您可以直接從REST API控制工作流，透過包含工作流ID和所需執行命令的POST請求：

`POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>/commands`

>[!CAUTION]
>
>如果在Adobe Campaign更改了工作區ID,API請求將不再有效。

有四個執行命令可用於控制工作流：

* 開始
* 暫停
* 繼續
* 停止

有關執行命令的詳細資訊，請參閱[促銷活動文檔](https://docs.adobe.com/content/help/en/campaign-standard/using/managing-processes-and-data/executing-a-workflow/about-workflow-execution.html)。

<br/>

***請求範例***

* 啟動工作流程。

   ```
   -X POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>/commands \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>' \
   -i
   -d '{"method":"start"}'
   ```

   <!-- + réponse -->

* 停止工作流。

   ```
   -X POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>/commands \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>' \
   -i
   -d '{"method":"stop"}'
   ```

   <!-- + réponse -->
