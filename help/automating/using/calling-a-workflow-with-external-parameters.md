---
title: 概覽
description: 本節詳細說明如何使用外部參數呼叫工作流程。
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

Campaign Standard可讓您使用參數（要鎖定的對象名稱、要匯入的檔案名稱、訊息內容的一部分等）呼叫工作流程。 這樣，您就可以輕鬆整合Campaign自動化與外部系統。

我們以下列範例為例，說明如何直接從CMS傳送電子郵件。 在此情況下，您可以設定您的系統以選取對象，並將內容透過電子郵件傳送至CMS。 按一下「傳送」之後，會使用這些參數呼叫行銷活動工作流程，以便您將這些參數用於工作流程，以定義要在傳送中使用的對象和URL內容。

使用參數呼叫工作流程的程式如下：

1. 宣告&#x200B;**[!UICONTROL External signal]**&#x200B;活動中的參數。 請參閱[在外部信號活動中聲明參數](../../automating/using/declaring-parameters-external-signal.md)。
1. 設定&#x200B;**[!UICONTROL End]**&#x200B;活動或API呼叫，以定義參數並觸發工作流程&#x200B;**[!UICONTROL External signal]**&#x200B;活動。 請參閱[此頁面](../../automating/using/defining-parameters-calling-workflow.md)
1. 觸發工作流程後，參數會擷取至工作流程的事件變數中，並可在工作流程中使用。 請參閱[此頁面](../../automating/using/customizing-workflow-external-parameters.md)。

![](assets/extsignal_process.png)
