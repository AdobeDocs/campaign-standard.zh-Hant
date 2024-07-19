---
title: 概覽
description: 本節詳細說明如何使用外部引數呼叫工作流程。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 538056e6-b5c0-4258-a34b-524fe6e3cbbe
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 2%

---

# 概覽 {#calling-a-workflow-with-external-parameters}

Campaign Standard可讓您使用引數（要定位的對象名稱、要匯入的檔案名稱、部分訊息內容等）呼叫工作流程。 如此一來，您便可輕鬆將Campaign自動化與外部系統整合。

以下列範例為例，我們想要直接從CMS傳送電子郵件。 在這種情況下，您可以設定系統以選取對象，並將電子郵件內容放入CMS中。 按一下「傳送」 ，接著會使用這些引數呼叫Campaign工作流程，好讓您在工作流程中使用這些引數，以定義要用於傳送的對象和URL內容。

使用引數呼叫工作流程的流程如下：

1. 在&#x200B;**[!UICONTROL External signal]**&#x200B;活動中宣告引數。 請參閱[在外部訊號活動](../../automating/using/declaring-parameters-external-signal.md)中宣告引數。
1. 設定&#x200B;**[!UICONTROL End]**&#x200B;活動或API呼叫以定義引數並觸發工作流程&#x200B;**[!UICONTROL External signal]**&#x200B;活動。 檢視[此頁面](../../automating/using/defining-parameters-calling-workflow.md)
1. 觸發工作流程後，引數會擷取至工作流程的事件變數中，並可用於工作流程中。 請參閱[此頁面](../../automating/using/customizing-workflow-external-parameters.md)。

![](assets/extsignal_process.png)
