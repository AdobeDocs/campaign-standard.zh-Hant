---
title: 在呼叫工作流程時定義參數
description: 本節詳細說明如何使用外部參數調用工作流。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: f7de0186-4136-4603-8f80-9f58c641cd9d
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 13%

---

# 在呼叫工作流程時定義參數 {#defining-the-parameters-when-calling-the-workflow}

本節詳細介紹在調用工作流時如何定義參數。 有關如何通過API調用執行此操作的詳細資訊，請參閱 [REST API文檔](../../api/using/triggering-a-signal-activity.md)。

在定義參數之前，請確保：

* 參數已在 **[!UICONTROL External Signal]** 的子菜單。 請參閱[此頁面](../../automating/using/declaring-parameters-external-signal.md)。
* 包含信號活動的工作流正在運行。

配置 **[!UICONTROL End]** 活動，請執行以下步驟：

1. 開啟 **[!UICONTROL End]** 活動，然後選擇 **[!UICONTROL External signal]** 頁籤。
1. 選擇要調用的工作流和外部信號活動。
1. 按一下 **[!UICONTROL Create element]** 的子菜單。

   * **[!UICONTROL Name]**:在 **[!UICONTROL External signal]** 活動(請參閱 [此頁](../../automating/using/declaring-parameters-external-signal.md))。
   * **[!UICONTROL Value]**:要分配給參數的值。 值應跟在 **標準語法**，說明 [此部分](../../automating/using/advanced-expression-editing.md#standard-syntax)。

   ![](assets/extsignal_definingparameters_2.png)

   >[!CAUTION]
   >
   >確保已在 **[!UICONTROL External signal]** 的子菜單。 否則，執行活動時將發生錯誤。

1. 定義參數後，確認活動，然後保存工作流。
