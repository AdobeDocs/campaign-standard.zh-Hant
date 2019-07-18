---
title: 測試
seo-title: 測試
description: 測試
seo-description: 測試活動會根據測試結果啓用轉場。
page-status-flag: 從未啓動
uuid: 1562ec7a-253a-4f4f-b66 a-c2948 b57775 a
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: reference
topic-tags: 執行活動
discoiquuid: 2650fb1f-0bce-4049-a226-2369f6666 b95
context-tags: jstest，main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Test{#test}

## Description {#description}

![](assets/test.png)

**[!UICONTROL Test]** 活動會根據測試結果啓用轉場。

## Context of use {#context-of-use}

**測試** 活動會啓動第一個符合與其相關聯條件的轉場。

If no condition is satisfied and if the **Use default transition** option is activated, a default transition will be activated.

![](assets/wkf_test_activity_example.png)

Conditions can be based on **functions**, or on **variables**, for example events variables that have been declared into the workflow's **[!UICONTROL External signal]** activity.

**相關主題：**

* [函數清單](../../automating/using/list-of-functions.md)
* [使用外部參數來呼叫工作流程](../../automating/using/calling-a-workflow-with-external-parameters.md)

## Configuration {#configuration}

1. Drag and drop a **[!UICONTROL Test]** activity into the workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. 定義每個條件的屬性：

   When editing the **[!UICONTROL Condition]** field, two buttons provide help to call events variables and edit expressions combining variables and functions:

   * ![](assets/extsignal_picker.png)：選取工作流程中所有可用變數之間的事件變數(請參閱 [使用外部參數自訂工作流程](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-a-workflow-with-external-parameters))

      ![](assets/wkf_test_activity_variables.png)

   * ![](assets/extsignal_expression_editor.png)：編輯結合變數和函數的運算式。For more on the Expression editor, refer to [this section](../../automating/using/advanced-expression-editing.md).

      ![](assets/wkf_test_activity_variables_expression.png)

