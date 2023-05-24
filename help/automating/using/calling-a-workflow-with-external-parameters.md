---
title: 概覽
description: 本節詳細說明如何使用外部參數調用工作流。
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

Campaign Standard允許您使用參數（目標的訪問群體名稱、要導入的檔案名、部分消息內容等）調用工作流。 這樣，您就可以輕鬆將促銷活動自動化與外部系統整合。

讓我們舉下例，我們希望直接從CMS發送電子郵件。 在這種情況下，您可以配置系統以選擇受眾和將電子郵件內容發送到CMS。 按一下「發送」後，將使用這些參數調用市場活動工作流，使您能夠將它們用到工作流中，以定義要在交付中使用的受眾和URL內容。

使用參數調用工作流的過程如下：

1. 在 **[!UICONTROL External signal]** 的子菜單。 請參閱 [在外部信號活動中聲明參數](../../automating/using/declaring-parameters-external-signal.md)。
1. 配置 **[!UICONTROL End]** 活動或API調用，以定義參數並觸發工作流 **[!UICONTROL External signal]** 的子菜單。 請參閱 [此頁](../../automating/using/defining-parameters-calling-workflow.md)
1. 一旦觸發了工作流，這些參數將被引入工作流的事件變數中，並可在工作流中使用。 請參閱[此頁面](../../automating/using/customizing-workflow-external-parameters.md)。

![](assets/extsignal_process.png)
