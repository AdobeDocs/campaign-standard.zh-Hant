---
solution: Campaign Standard
product: campaign
title: 概觀
description: 本節詳細說明如何使用外部參數調用工作流。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 2%

---


# 概觀 {#calling-a-workflow-with-external-parameters}

Campaign Standard可讓您使用參數（要定位的對象名稱、要匯入的檔案名稱、訊息內容的一部分等）來呼叫工作流程。 如此，您就可輕鬆將Campaign自動化與外部系統整合。

讓我們舉下列範例，其中我們要直接從CMS傳送電子郵件。 在這種情況下，您可以設定系統以選擇觀眾，並將內容以電子郵件形式傳送至CMS。 按一下「傳送」將會使用這些參數呼叫促銷活動工作流程，讓您將這些參數用在工作流程中，以定義要用於傳送的對象和URL內容。

使用參數調用工作流的過程如下：

1. 在活動中聲明參 **[!UICONTROL External signal]** 數。 See [Declaring the parameters in the External signal activity](../../automating/using/declaring-parameters-external-signal.md).
1. 設定活 **[!UICONTROL End]** 動或API呼叫，以定義參數並觸發工作流程 **[!UICONTROL External signal]** 活動。 See [this page](../../automating/using/defining-parameters-calling-workflow.md)
1. 觸發工作流程後，這些參數便會被收錄到工作流程的事件變數中，並可在工作流程中使用。 請參閱[本頁](../../automating/using/customizing-workflow-external-parameters.md)。

![](assets/extsignal_process.png)
