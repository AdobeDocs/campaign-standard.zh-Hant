---
title: 使用外部引數自訂工作流程
description: 本節詳細說明如何使用外部引數呼叫工作流程。
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

# 使用外部引數自訂工作流程 {#customizing-a-workflow-with-external-parameters}

觸發工作流程後，引數會擷取至事件變數中，並可用於自訂工作流程的活動。

例如，它們可用來定義要在中讀取的對象 **[!UICONTROL Read audience]** 活動，要傳輸到的檔案名稱 **[!UICONTROL Transfer file]** 活動等。 (請參閱 [此頁面](../../automating/using/customizing-workflow-external-parameters.md))。

## 使用事件變數 {#using-events-variables}

事件變數用於必須遵守 [標準語法](../../automating/using/advanced-expression-editing.md#standard-syntax).

使用事件變數的語法必須遵循以下格式，並使用中定義的引數名稱 **[!UICONTROL External signal]** 活動(請參閱 [在外部訊號活動中宣告引數](../../automating/using/declaring-parameters-external-signal.md))：

```
$(vars/@parameterName)
```

在此語法中， **$** 函式傳回 **字串** 資料型別。 如果要指定其他型別的資料，請使用下列函式：

* **$long**：整數。
* **$float**：十進位數字。
* **$boolean**： true/false。
* **$datetime**：時間戳記。

在活動中使用變數時，介面會提供呼叫變數的說明。

![](assets/extsignal_callparameter.png)

* ![](assets/extsignal_picker.png)：在工作流程中可用的所有變數中選取事件變數。

  ![](assets/wkf_test_activity_variables.png)

* ![](assets/extsignal_expression_editor.png)：編輯結合變數和函式的運算式(請參閱 [此頁面](../../automating/using/advanced-expression-editing.md))。

  ![](assets/wkf_test_activity_variables_expression.png)

  此清單提供的功能可讓您執行複雜的篩選。 這些函式的詳細資訊，請參見 [本節](../../automating/using/list-of-functions.md).

  此外，您可以使用下列函式，這些函式可用於所有活動，讓您在使用外部引數呼叫工作流程後可以使用事件變數(請參閱 [本節](../../automating/using/customizing-workflow-external-parameters.md#customizing-activities-with-events-variables))：

  | 名稱 | 說明 | 語法 |
  | ---------|----------|---------|
  | EndWith | 指示字串（第1個引數）是否以特定字串（第2個引數）結尾。 | EndWith(&lt;string>，&lt;string>) |
  | startWith | 指出字串（第1個引數）是否以特定字串（第2個引數）開頭。 | startWith(&lt;string>，&lt;string>) |
  | Extract | 使用分隔符號傳回字串的第一個字元。 | Extract(&lt;string>，&lt;separator>) |
  | ExtractRight | 使用分隔符號傳回字串的最後一個字元。 | ExtractRight(&lt;string>，&lt;separator>) |
  | 日期格式 | 使用在第2個引數中指定的格式來格式化日期（範例：&#39;%4Y%2M%2D&#39;） | 日期格式(&lt;date>，&lt;format>) |
  | 檔案名稱 | 傳回檔案路徑的名稱。 | 檔案名稱(&lt;string>) |
  | 檔案分機 | 傳回檔案路徑的副檔名。 | FileExt(&lt;string>) |
  | GetOption | 傳回指定函式的值。 | GetOption(&lt;optionname>) |
  | IsNull | 指示字串或日期是否為空。 | IsNull(&lt;string date=&quot;&quot;>) |
  | UrlUtf8Encode | 以UTF8編碼URL。 | UrlUtf8Encode(&lt;string>) |

## 使用事件變數自訂活動 {#customizing-activities-with-events-variables}

事件變數可用來自訂數個活動，如下節所列。 有關如何從活動呼叫變數的詳細資訊，請參閱 [本節](../../automating/using/customizing-workflow-external-parameters.md#using-events-variables).

**[!UICONTROL Read audience]** 活動：根據事件變數定義要定位的對象。 有關如何使用活動的詳細資訊，請參閱 [本節](../../automating/using/read-audience.md).

![](assets/extsignal_activities_audience.png)

**[!UICONTROL Test]** 活動：根據事件變數建立條件。 有關如何使用活動的詳細資訊，請參閱 [本節](../../automating/using/test.md).

![](assets/extsignal_activities_test.png)

**[!UICONTROL Transfer file]** 活動：根據事件變數自訂要傳輸的檔案。 有關如何使用活動的詳細資訊，請參閱 [本節](../../automating/using/transfer-file.md).

![](assets/extsignal_activities_transfer.png)

**[!UICONTROL Query]** 活動：引數可透過使用結合事件變數和函式的運算式在查詢中參考。 若要這麼做，請新增規則，然後按一下 **[!UICONTROL Advanced mode]** 連結以存取運算式編輯視窗(請參閱 [進階運算式編輯](../../automating/using/advanced-expression-editing.md))。

有關如何使用活動的詳細資訊，請參閱 [本節](../../automating/using/query.md).

![](assets/extsignal_activities_query.png)

**[!UICONTROL Channels]** 活動：根據事件變數個人化傳遞。

>[!NOTE]
>
>每次準備傳送時，都會擷取傳送引數的值。
>
>週期性傳送準備是以傳送為基礎 **彙總期間**. 例如，如果彙總期間為「依日」，則每天僅會重新準備一次傳送。 如果傳送引數的值在當天被修改，則不會在傳送中更新，因為它已經準備過一次。
>
>如果您打算一天呼叫工作流程多次，請使用 [!UICONTROL No aggregation] 選項，以便傳送引數每次都會更新。 有關循環傳送設定的詳細資訊，請參閱 [本節](/help/automating/using/email-delivery.md#configuration).

若要根據事件變數個人化傳遞，您必須先將您要使用的變數宣告至傳遞活動：

1. 選取活動，然後按一下 ![](assets/dlv_activity_params-24px.png) 按鈕以存取設定。
1. 選取 **[!UICONTROL General]** 標籤，然後新增可在傳送中作為個人化欄位使用的事件變數。

   ![](assets/extsignal_activities_delivery.png)

1. 按一下 **[!UICONTROL Confirm]** 按鈕。

個人化欄位清單現在提供已宣告的事件變數。 您可以在傳送中使用這些變數，以執行下列動作：

* 定義用於傳遞的範本名稱。

  >[!NOTE]
  >
  >此動作適用於 **週期性** 僅限傳遞。

  ![](assets/extsignal_activities_template.png)

* 個人化傳遞：選取個人化欄位以設定傳遞時，事件變數位於 **[!UICONTROL Workflow parameters]** 元素。 您可以使用它們做為任何個人化欄位，例如定義傳送主題、寄件者等。

  傳遞個人化的詳細資訊，請參閱 [本節](../../designing/using/personalization.md).

  ![](assets/extsignal_activities_perso.png)

**區段代碼**：根據事件變數定義區段代碼。

>[!NOTE]
>
>此動作可從任何可讓您定義區段代碼的活動執行，例如 **[!UICONTROL Query]** 或 **[!UICONTROL Segmentation]** 活動。

![](assets/extsignal_activities_segment.png)

**傳遞標籤**：根據事件變數定義傳送標籤。

![](assets/extsignal_activities_label.png)
