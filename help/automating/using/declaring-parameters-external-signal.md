---
title: 在外部訊號活動中宣告引數
description: 本節詳細說明如何使用外部引數呼叫工作流程。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: e6148b40-f608-4aab-81f6-756608c6828e
TQID: 'https://experienceleague.adobe.com/au0xUZ7C8m3hiK9wbm3QBiHd9RtpZQW-AEoc-SvnhfE'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '110'
ht-degree: 0%
---
# 在外部訊號活動中宣告引數 {#declaring-the-parameters-in-the-external-signal-activity}

使用引數呼叫工作流程的第一步是在&#x200B;**[!UICONTROL External signal]**&#x200B;活動中宣告它們。

1. 開啟&#x200B;**[!UICONTROL External signal]**&#x200B;活動，然後選取&#x200B;**[!UICONTROL Parameters]**&#x200B;標籤。
1. 按一下&#x200B;**[!UICONTROL Create element]**&#x200B;按鈕，然後指定每個引數的名稱和型別。

   >[!CAUTION]
   >
   >請確定引數的名稱和數目與呼叫工作流程時所定義的相同（請參閱[此頁面](../../automating/using/defining-parameters-calling-workflow.md)）。 此外，引數的型別必須與預期值一致。

   ![](assets/extsignal_declaringparameters_1.png)

1. 宣告引數後，請完成工作流程設定，然後執行。
