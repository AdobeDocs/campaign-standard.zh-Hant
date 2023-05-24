---
title: 使用外部參數自定義工作流
description: 本節詳細說明如何使用外部參數調用工作流。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 8c1a47ed-3467-4fcd-8747-86f0e8f15cec
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '813'
ht-degree: 1%

---

# 使用外部參數自定義工作流 {#customizing-a-workflow-with-external-parameters}

一旦觸發了工作流，這些參數將被引入事件變數中，並可用於定制工作流的活動。

例如，它們可用於定義在 **[!UICONTROL Read audience]** 活動，要在 **[!UICONTROL Transfer file]** 活動等 （請參見） [此頁](../../automating/using/customizing-workflow-external-parameters.md))。

## 使用事件變數 {#using-events-variables}

事件變數在必須與 [標準語法](../../automating/using/advanced-expression-editing.md#standard-syntax)。

使用事件變數的語法必須遵循以下格式，並使用在 **[!UICONTROL External signal]** 活動(請參閱 [在外部信號活動中聲明參數](../../automating/using/declaring-parameters-external-signal.md)):

```
$(vars/@parameterName)
```

在此語法中， **$** 函式返回 **字串** 資料類型。 如果要指定其他類型的資料，請使用以下函式：

* **長**:整數。
* **浮動**:十進位數。
* **$布爾值**:真/假。
* **$datetime**:時間戳。

在活動中使用變數時，介面提供調用該變數的幫助。

![](assets/extsignal_callparameter.png)

* ![](assets/extsignal_picker.png):在工作流中可用的所有變數中選擇事件變數。

   ![](assets/wkf_test_activity_variables.png)

* ![](assets/extsignal_expression_editor.png):編輯組合變數和函式的表達式(請參見 [此頁](../../automating/using/advanced-expression-editing.md))。

   ![](assets/wkf_test_activity_variables_expression.png)

   此清單提供允許您執行複雜篩選的函式。 這些函式在 [此部分](../../automating/using/list-of-functions.md)。

   此外，您還可以使用以下函式，這些函式可用於所有活動，這些活動允許您在調用具有外部參數的工作流後使用事件變數(請參閱 [此部分](../../automating/using/customizing-workflow-external-parameters.md#customizing-activities-with-events-variables)):

   | 名稱 | 說明 | 語法 |
   | ---------|----------|---------|
   | 結尾 | 指示字串（第1個參數）是否以特定字串（第2個參數）結尾。 | 結束方式(&lt;string>。&lt;string>) |
   | startWith | 指示字串（第1個參數）是否以特定字串（第2個參數）開頭。 | startWith(&lt;string>。&lt;string>) |
   | 提取 | 使用分隔符返回字串的第一個字元。 | 提取(&lt;string>。&lt;separator>) |
   | 右提取 | 使用分隔符返回字串的最後字元。 | ExtractRight(&lt;string>。&lt;separator>) |
   | 日期格式 | 使用第2個參數中指定的格式設定日期格式(示例：「%4Y%2M%2D」) | 日期格式(&lt;date>。&lt;format>) |
   | 檔案名 | 返回檔案路徑的名稱。 | 檔案名(&lt;string>) |
   | 檔案擴展 | 返回檔案路徑的副檔名。 | 檔案擴展(&lt;string>) |
   | 獲取選項 | 返回指定函式的值。 | GetOption(&lt;optionname>) |
   | IsNull | 指示字串或日期是否為空。 | IsNull(&lt;string date=&quot;&quot;>) |
   | UrlUtf8Encode | 以UTF8編碼URL。 | URLUTF8Encode(&lt;string>) |

## 使用事件變數自定義活動 {#customizing-activities-with-events-variables}

事件變數可用於自定義以下部分中列出的幾個活動。 有關如何從活動調用變數的詳細資訊，請參閱 [此部分](../../automating/using/customizing-workflow-external-parameters.md#using-events-variables)。

**[!UICONTROL Read audience]** 活動：根據事件變數定義目標受眾。 有關如何使用活動的詳細資訊，請參閱 [此部分](../../automating/using/read-audience.md)。

![](assets/extsignal_activities_audience.png)

**[!UICONTROL Test]** 活動：基於事件變數生成條件。 有關如何使用活動的詳細資訊，請參閱 [此部分](../../automating/using/test.md)。

![](assets/extsignal_activities_test.png)

**[!UICONTROL Transfer file]** 活動：根據事件變數定制要傳輸的檔案。 有關如何使用活動的詳細資訊，請參閱 [此部分](../../automating/using/transfer-file.md)。

![](assets/extsignal_activities_transfer.png)

**[!UICONTROL Query]** 活動：通過使用組合事件變數和函式的表達式，可以在查詢中引用參數。 為此，請添加規則，然後按一下 **[!UICONTROL Advanced mode]** 連結以訪問表達式編輯窗口(請參見 [高級表達式編輯](../../automating/using/advanced-expression-editing.md))。

有關如何使用活動的詳細資訊，請參閱 [此部分](../../automating/using/query.md)。

![](assets/extsignal_activities_query.png)

**[!UICONTROL Channels]** 活動：根據事件變數對交貨進行個性化。

>[!NOTE]
>
>每次準備遞送時都檢索遞送參數的值。
>
>定期交貨準備基於交貨 **聚合期**。 例如，如果聚合期間為「按天」，則每天只重新準備一次交貨。 如果在一天中修改了交貨參數的值，則不會在交貨中更新它，因為已準備過一次。
>
>如果您計畫每天多次調用工作流，請使用 [!UICONTROL No aggregation] 選項，以便每次更新交貨參數。 有關定期交貨配置的詳細資訊，請參閱 [此部分](/help/automating/using/email-delivery.md#configuration)。

要根據事件變數對傳遞進行個性化設定，必須首先在傳遞活動中聲明要使用的變數：

1. 選擇活動，然後按一下 ![](assets/dlv_activity_params-24px.png) 按鈕。
1. 選擇 **[!UICONTROL General]** 頁籤，然後添加可用作傳遞中個性化欄位的事件變數。

   ![](assets/extsignal_activities_delivery.png)

1. 按一下 **[!UICONTROL Confirm]** 按鈕。

聲明的事件變數現在可從個性化設定欄位清單中獲得。 您可以在交貨中使用它們來執行以下操作：

* 定義要用於交貨的模板的名稱。

   >[!NOTE]
   >
   >此操作可用於 **循環** 僅遞送。

   ![](assets/extsignal_activities_template.png)

* 個性化交付：選擇個性化欄位以配置傳遞時，事件變數在 **[!UICONTROL Workflow parameters]** 的子菜單。 您可以將它們用作任何個性化欄位，例如定義交貨主題、發件人等。

   交付個性化在 [此部分](../../designing/using/personalization.md)。

   ![](assets/extsignal_activities_perso.png)

**段代碼**:根據事件變數定義段代碼。

>[!NOTE]
>
>此操作可通過任何允許定義段代碼的活動執行，例如， **[!UICONTROL Query]** 或 **[!UICONTROL Segmentation]** 活動。

![](assets/extsignal_activities_segment.png)

**交貨標籤**:根據事件變數定義交貨標籤。

![](assets/extsignal_activities_label.png)
