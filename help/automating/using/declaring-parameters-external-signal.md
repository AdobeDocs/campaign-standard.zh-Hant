---
title: 在外部信號活動中聲明參數
description: 本節詳細說明如何使用外部參數調用工作流。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: e6148b40-f608-4aab-81f6-756608c6828e
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '110'
ht-degree: 0%

---

# 在外部信號活動中聲明參數 {#declaring-the-parameters-in-the-external-signal-activity}

使用參數調用工作流的第一步是在 **[!UICONTROL External signal]** 的子菜單。

1. 開啟 **[!UICONTROL External signal]** 活動，然後選擇 **[!UICONTROL Parameters]** 頁籤。
1. 按一下 **[!UICONTROL Create element]** 按鈕，然後指定每個參數的名稱和類型。

   >[!CAUTION]
   >
   >確保參數的名稱和數量與調用工作流時定義的參數相同(請參見 [此頁](../../automating/using/defining-parameters-calling-workflow.md))。 此外，參數類型必須與預期值一致。

   ![](assets/extsignal_declaringparameters_1.png)

1. 聲明參數後，完成工作流配置，然後運行它。
