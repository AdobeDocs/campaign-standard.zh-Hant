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
source-wordcount: '188'
ht-degree: 13%

---


# 在呼叫工作流程時定義參數 {#defining-the-parameters-when-calling-the-workflow}

本節詳細說明如何在調用工作流時定義參數。 如需如何從API呼叫執行此作業的詳細資訊，請參閱 [REST API檔案](../../api/using/triggering-a-signal-activity.md)。

在定義參數之前，請確定：

* 參數已在活動中聲 **[!UICONTROL External Signal]** 明。 請參閱[本頁](../../automating/using/declaring-parameters-external-signal.md)。
* 包含信號活動的工作流正在運行。

要配置活 **[!UICONTROL End]** 動，請執行以下步驟：

1. Open the **[!UICONTROL End]** activity, then select the **[!UICONTROL External signal]** tab.
1. 選擇要調用的工作流和外部信號活動。
1. 按一下 **[!UICONTROL Create element]** 按鈕以新增參數，然後填入其名稱和值。

   * **[!UICONTROL Name]**:已在活動中宣告的名 **[!UICONTROL External signal]** 稱(請參 [閱本頁](../../automating/using/declaring-parameters-external-signal.md))。
   * **[!UICONTROL Value]**:要指派給參數的值。 值應遵循 **Standard語法**，如本 [節所述](../../automating/using/advanced-expression-editing.md#standard-syntax)。

   ![](assets/extsignal_definingparameters_2.png)

   >[!CAUTION]
   >
   >Make sure that all the parameters have been declared in the **[!UICONTROL External signal]** activity. 否則，執行活動時將發生錯誤。

1. 定義參數後，請確認活動，然後儲存您的工作流程。
