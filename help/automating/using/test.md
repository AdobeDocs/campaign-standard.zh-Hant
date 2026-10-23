---
title: 測試
description: 「測試」活動會根據測試結果啟用轉變。
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: jstest,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 62a064f7-6d0b-49ca-9834-eccb5bf42496
TQID: 'https://experienceleague.adobe.com/oyXhQ4Fgx2-cooFelMxsoFiP1qx48-ZQ1eoAudNivF8'
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
source-wordcount: '190'
ht-degree: 80%
---
# 測試{#test}

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
1. 選取活動，然後使用所顯示快速動作中的 ![](assets/edit_darkgrey-24px.png) 按鈕將其開啟。
1. 定義每個條件的屬性：

   編輯 **[!UICONTROL Condition]** 欄位時，兩個按鈕可提供呼叫事件變數及編輯結合變數和函式的運算式的協助：

   * ![](assets/extsignal_picker.png)：在工作流程中可用的所有變數中選取事件變數（請參閱[此頁面](../../automating/using/customizing-workflow-external-parameters.md)）。

     例如，您可以使用&#x200B;**[!UICONTROL filesCount]**&#x200B;變數檢查[檔案傳輸](../../automating/using/transfer-file.md)活動後的已下載檔案數。

     ![](assets/wkf_test_activity_variables.png)

   * ![](assets/extsignal_expression_editor.png)：編輯結合變數和函式的運算式。 如需運算式編輯器的詳細資訊，請參考[本區段](../../automating/using/advanced-expression-editing.md)。

     ![](assets/wkf_test_activity_variables_expression.png)
