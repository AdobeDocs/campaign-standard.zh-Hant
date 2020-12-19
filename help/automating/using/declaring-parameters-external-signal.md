---
solution: Campaign Standard
product: campaign
title: 使用外部參數呼叫工作流程
description: 本節詳細說明如何使用外部參數調用工作流。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 5%

---


# 聲明外部信號活動{#declaring-the-parameters-in-the-external-signal-activity}中的參數

使用參數呼叫工作流的第一步是在&#x200B;**[!UICONTROL External signal]**&#x200B;活動中聲明這些參數。

1. 開啟&#x200B;**[!UICONTROL External signal]**&#x200B;活動，然後選取&#x200B;**[!UICONTROL Parameters]**&#x200B;標籤。
1. 按一下&#x200B;**[!UICONTROL Create element]**&#x200B;按鈕，然後指定每個參數的名稱和類型。

   >[!CAUTION]
   >
   >請確定參數的名稱和數目與呼叫工作流時定義的相同（請參閱[本頁](../../automating/using/defining-parameters-calling-workflow.md)）。 此外，參數類型必須與預期值一致。

   ![](assets/extsignal_declaringparameters_1.png)

1. 在聲明參數後，完成工作流配置，然後運行它。
