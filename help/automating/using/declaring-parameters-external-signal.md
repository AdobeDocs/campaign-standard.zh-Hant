---
title: 在外部訊號活動中宣告引數
description: 本節詳細說明如何使用外部引數呼叫工作流程。
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

# 在外部訊號活動中宣告引數 {#declaring-the-parameters-in-the-external-signal-activity}

使用引數呼叫工作流程的第一步，是在中宣告它們 **[!UICONTROL External signal]** 活動。

1. 開啟 **[!UICONTROL External signal]** 活動，然後選取 **[!UICONTROL Parameters]** 標籤。
1. 按一下 **[!UICONTROL Create element]** 按鈕，然後指定每個引數的名稱和型別。

   >[!CAUTION]
   >
   >請確定引數的名稱和數目與呼叫工作流程時所定義的相同(請參閱 [此頁面](../../automating/using/defining-parameters-calling-workflow.md))。 此外，引數的型別必須與預期值一致。

   ![](assets/extsignal_declaringparameters_1.png)

1. 宣告引數後，請完成工作流程設定，然後執行。
