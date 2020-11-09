---
title: 測試
description: 「測試」活動會根據測試結果啟用轉變。
page-status-flag: never-activated
uuid: 1562ec7a-253a-4f4f-b66a-c2948b57775a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 2650bf1f-0bce-4049-a226-2369f6666b95
context-tags: jstest,main
translation-type: tm+mt
source-git-commit: 121b36056317cc89909607220f988c02ae470f08
workflow-type: tm+mt
source-wordcount: '172'
ht-degree: 90%

---


# 測試 {#test}

## 說明 {#description}

![](assets/test.png)

**[!UICONTROL Test]** 活動會根據測試結果啟用轉換。

## 使用內容 {#context-of-use}

「**測試**」活動會啟動滿足與其相關的條件的第一個轉變。

如果未滿足任何條件，並且啟動了「**使用預設過渡**」選項，則將啟動預設轉變。

![](assets/wkf_test_activity_example.png)

條件能以&#x200B;**函式**&#x200B;為基礎，或以&#x200B;**變數**&#x200B;為基礎，例如已宣告至工作流程 **[!UICONTROL External signal]** 活動中的事件變數。

**相關主題：**

* [函式清單](../../automating/using/list-of-functions.md)
* [使用外部參數呼叫工作流程](../../automating/using/calling-a-workflow-with-external-parameters.md)

## 設定 {#configuration}

1. 將 **[!UICONTROL Test]** 活動拖放至工作流程中。
1. 選取活動，然後使用所顯示快速操作中的 ![](assets/edit_darkgrey-24px.png) 按鈕將其開啟。
1. 定義每個條件的屬性：

   編輯 **[!UICONTROL Condition]** 欄位時，兩個按鈕可提供呼叫事件變數及編輯結合變數和函式的運算式的協助：

   * ![](assets/extsignal_picker.png):在工作流程中可用的所有變數中選取事件變數(請參 [閱本頁](../../automating/using/customizing-workflow-external-parameters.md))

      ![](assets/wkf_test_activity_variables.png)

   * ![](assets/extsignal_expression_editor.png)：編輯結合變數和函式的運算式。如需運算式編輯器的詳細資訊，請參考[本區段](../../automating/using/advanced-expression-editing.md)。

      ![](assets/wkf_test_activity_variables_expression.png)
