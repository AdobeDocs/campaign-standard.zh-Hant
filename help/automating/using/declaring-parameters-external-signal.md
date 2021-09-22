---
title: 使用外部參數呼叫工作流程
description: 本節詳細說明如何使用外部參數呼叫工作流程。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: e6148b40-f608-4aab-81f6-756608c6828e
source-git-commit: 13d419c5fc51845ee14f8a3b288f4c467e0a60d9
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 5%

---

# 在外部信號活動中聲明參數 {#declaring-the-parameters-in-the-external-signal-activity}

使用參數呼叫工作流程的第一步，是在&#x200B;**[!UICONTROL External signal]**&#x200B;活動中宣告這些參數。

1. 開啟&#x200B;**[!UICONTROL External signal]**&#x200B;活動，然後選取&#x200B;**[!UICONTROL Parameters]**&#x200B;標籤。
1. 按一下&#x200B;**[!UICONTROL Create element]**&#x200B;按鈕，然後指定每個參數的名稱和類型。

   >[!CAUTION]
   >
   >請確定參數的名稱和數目與呼叫工作流程時所定義的相同（請參閱[此頁面](../../automating/using/defining-parameters-calling-workflow.md)）。 此外，參數的類型必須與預期值一致。

   ![](assets/extsignal_declaringparameters_1.png)

1. 聲明參數後，完成工作流配置，然後運行它。
