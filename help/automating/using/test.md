---
title: 測試
description: 「測試」活動會根據測試結果啟用轉換。
page-status-flag: 從未激活
uuid: 1562ec7a-253a-4f4f-b66a-c2948b57775a
contentOwner: 紹維亞
products: SG_CAMPAIGN/STANDARD
audience: 自動化
content-type: 參考
topic-tags: 執行活動
discoiquuid: 2650bf1f-0bce-4049-a226-2369f6666b95
context-tags: jstest,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 測試{#test}

## 說明 {#description}

![](assets/test.png)

此活 **[!UICONTROL Test]** 動會根據測試結果啟用轉換。

## 使用內容 {#context-of-use}

「測 **試** 」活動激活滿足與其相關的條件的第一個轉變。

如果未滿足任何條件，並且激活了「 **使用預設過渡** 」選項，則將激活預設過渡。

![](assets/wkf_test_activity_example.png)

條件可以以函 **數為基礎**，或以變 **數為基礎**，例如已宣告至工作流程活動中的事件變 **[!UICONTROL External signal]** 數。

**相關主題：**

* [函式清單](../../automating/using/list-of-functions.md)
* [使用外部參數呼叫工作流程](../../automating/using/calling-a-workflow-with-external-parameters.md)

## 配置 {#configuration}

1. 將活動拖放 **[!UICONTROL Test]** 到工作流程中。
1. 選擇活動，然後使用顯示的快 ![](assets/edit_darkgrey-24px.png) 速操作中的按鈕將其開啟。
1. 定義每個條件的屬性：

   編輯欄位時， **[!UICONTROL Condition]** 兩個按鈕可提供呼叫事件變數及編輯結合變數和函式的運算式的協助：

   * ![](assets/extsignal_picker.png):在工作流程中可用的所有變數中選取事件變數(請參閱使 [用外部參數自訂工作流程](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-a-workflow-with-external-parameters))

      ![](assets/wkf_test_activity_variables.png)

   * ![](assets/extsignal_expression_editor.png):編輯結合變數和函式的運算式。 有關「表達式」編輯器的詳細資訊，請參 [閱本節](../../automating/using/advanced-expression-editing.md)。

      ![](assets/wkf_test_activity_variables_expression.png)

