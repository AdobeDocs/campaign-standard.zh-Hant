---
title: 在呼叫工作流程時定義參數
description: 本節詳細說明如何使用外部引數呼叫工作流程。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: f7de0186-4136-4603-8f80-9f58c641cd9d
TQID: https://experienceleague.adobe.com/-YjlK1Op8P08sxb--BOHl8AWyciX4BqPnCPQ3lpD3Co
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
subfeature_v2:
  - id: bf97c196-a4d1-4fa3-a151-e68a114c8ac0
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 189
ht-degree: 13%

---

# 在呼叫工作流程時定義參數 {#defining-the-parameters-when-calling-the-workflow}

本節詳細說明呼叫工作流程時如何定義引數。 如需有關如何從API呼叫執行此作業的詳細資訊，請參閱[REST API檔案](../../api/using/triggering-a-signal-activity.md)。

在定義引數之前，請確定：

* 已在&#x200B;**[!UICONTROL External Signal]**&#x200B;活動中宣告引數。 請參閱[此頁面](../../automating/using/declaring-parameters-external-signal.md)。
* 包含訊號活動的工作流程正在執行。

若要設定&#x200B;**[!UICONTROL End]**&#x200B;活動，請遵循下列步驟：

1. 開啟&#x200B;**[!UICONTROL End]**&#x200B;活動，然後選取&#x200B;**[!UICONTROL External signal]**&#x200B;標籤。
1. 選取您要呼叫的工作流程和外部訊號活動。
1. 按一下&#x200B;**[!UICONTROL Create element]**&#x200B;按鈕以新增引數，然後填寫其名稱和值。

   * **[!UICONTROL Name]**： **[!UICONTROL External signal]**&#x200B;活動中已宣告的名稱（請參閱[此頁面](../../automating/using/declaring-parameters-external-signal.md)）。
   * **[!UICONTROL Value]**：您要指派給引數的值。 值應遵循[本節](../../automating/using/advanced-expression-editing.md#standard-syntax)中說明的&#x200B;**標準語法**。

   ![](assets/extsignal_definingparameters_2.png)

   >[!CAUTION]
   >
   >請確定已在&#x200B;**[!UICONTROL External signal]**&#x200B;活動中宣告所有引數。 否則，執行活動時將發生錯誤。

1. 定義引數後，請確認活動，然後儲存工作流程。
