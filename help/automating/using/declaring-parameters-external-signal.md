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


# Declaring the parameters in the External signal activity {#declaring-the-parameters-in-the-external-signal-activity}

使用參數呼叫工作流程的第一步是在活動中宣告這 **[!UICONTROL External signal]** 些參數。

1. Open the **[!UICONTROL External signal]** activity, then select the **[!UICONTROL Parameters]** tab.
1. 按一下 **[!UICONTROL Create element]** 按鈕，然後指定每個參數的名稱和類型。

   >[!CAUTION]
   >
   >請確定參數的名稱和數目與呼叫工作流程時所定義的參數相同(請參 [閱本頁](../../automating/using/defining-parameters-calling-workflow.md))。 此外，參數類型必須與預期值一致。

   ![](assets/extsignal_declaringparameters_1.png)

1. 在聲明參數後，完成工作流配置，然後運行它。
