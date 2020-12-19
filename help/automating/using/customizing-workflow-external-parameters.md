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
source-wordcount: '803'
ht-degree: 1%

---


# 使用外部參數{#customizing-a-workflow-with-external-parameters}自訂工作流

觸發工作流程後，參數會被收錄到事件變數中，並可用來自訂工作流程的活動。

例如，它們可用來定義在&#x200B;**[!UICONTROL Read audience]**&#x200B;活動中要讀取的對象、在&#x200B;**[!UICONTROL Transfer file]**&#x200B;活動中要傳輸的檔案的名稱等。 （請參閱[本頁](../../automating/using/customizing-workflow-external-parameters.md)）。

## 使用事件變數{#using-events-variables}

事件變數用於必須遵循[標準語法](../../automating/using/advanced-expression-editing.md#standard-syntax)的運算式中。

使用事件變數的語法必須遵循下列格式，並使用&#x200B;**[!UICONTROL External signal]**&#x200B;活動中定義的參數名稱（請參閱[宣告外部信號活動](../../automating/using/declaring-parameters-external-signal.md)中的參數）:

```
$(vars/@parameterName)
```

在此語法中，**$**&#x200B;函式會傳回&#x200B;**字串**&#x200B;資料類型。 如果您想要指定其他類型的資料，請使用下列函式：

* **$long**:整數。
* **$float**:小數。
* **$boolean**:true/false。
* **$datetime**:時間戳記。

在活動中使用變數時，介面會提供呼叫變數的說明。

![](assets/extsignal_callparameter.png)

* ![](assets/extsignal_picker.png):在工作流程中可用的所有變數中選取事件變數。

   ![](assets/wkf_test_activity_variables.png)

* ![](assets/extsignal_expression_editor.png):編輯結合變數和函式的運算式(請參 [閱本頁](../../automating/using/advanced-expression-editing.md))。

   ![](assets/wkf_test_activity_variables_expression.png)

   此清單提供可讓您執行複雜篩選的函式。 這些函式在[本節](../../automating/using/list-of-functions.md)中有詳細說明。

   此外，您也可以使用下列函式，這些函式可用於所有允許您在使用外部參數呼叫工作流程後使用事件變數的活動（請參閱[本節](../../automating/using/customizing-workflow-external-parameters.md#customizing-activities-with-events-variables)）:

   | 名稱 | 說明 | 語法 |
   ---------|----------|---------
   | 結束於 | 指出字串（第1個參數）是否以特定字串（第2個參數）結尾。 | EndWith(&lt;String>,&lt;String>) |
   | startWith | 指出字串（第1個參數）是否以特定字串（第2個參數）開頭。 | startWith(&lt;String>,&lt;String>) |
   | 摘取 | 使用分隔符返回字串的第一個字元。 | Extract(&lt;String>,&lt;Separator>) |
   | ExtractRight | 使用分隔符返回字串的最後一個字元。 | ExtractRight(&lt;String>,&lt;Separator>) |
   | DateFormat | 使用第2個參數中指定的格式來格式化日期(範例： &#39;%4Y%2M%2D&#39;) | DateFormat(&lt;Date>,&lt;Format>) |
   | 檔案名稱 | 返回檔案路徑的名稱。 | FileName(&lt;String>) |
   | FileExt | 傳回檔案路徑的副檔名。 | FileExt(&lt;String>) |
   | IsNull | 指出字串或日期是否為空值。 | IsNull(&lt;String/date>) |
   | UrlUtf8Encode | 以UTF8編碼URL。 | UrlUtf8Encode(&lt;String>) |

## 使用事件變數{#customizing-activities-with-events-variables}自訂活動

事件變數可用來自訂數個活動，列於下方一節。 有關如何從活動呼叫變數的詳細資訊，請參閱[本節](../../automating/using/customizing-workflow-external-parameters.md#using-events-variables)。

**[!UICONTROL Read audience]** 活動：根據事件變數定義要定位的對象。有關如何使用活動的詳細資訊，請參閱[本節](../../automating/using/read-audience.md)。

![](assets/extsignal_activities_audience.png)

**[!UICONTROL Test]** 活動：根據事件變數建立條件。有關如何使用活動的詳細資訊，請參閱[本節](../../automating/using/test.md)。

![](assets/extsignal_activities_test.png)

**[!UICONTROL Transfer file]** 活動：根據事件變數自訂檔案以進行傳輸。有關如何使用活動的詳細資訊，請參閱[本節](../../automating/using/transfer-file.md)。

![](assets/extsignal_activities_transfer.png)

**[!UICONTROL Query]** 活動：參數可在查詢中參考，方法是使用結合事件變數和函式的運算式。若要這麼做，請新增規則，然後按一下&#x200B;**[!UICONTROL Advanced mode]**&#x200B;連結以存取運算式編輯視窗（請參閱[進階運算式編輯](../../automating/using/advanced-expression-editing.md)）。

有關如何使用活動的詳細資訊，請參閱[本節](../../automating/using/query.md)。

![](assets/extsignal_activities_query.png)

**[!UICONTROL Channels]** 活動：根據事件變數個人化傳送。

>[!NOTE]
>
>每次準備傳送時，都檢索該傳送參數的值。
>
>循環遞送準備基於遞送&#x200B;**聚合期**。 例如，如果匯總期間是「按天」，則每天只重新準備一次傳送。 如果傳送參數的值在當天被修改，則不會在傳送中更新，因為已準備一次。
>
>如果您計畫每天多次呼叫工作流，請使用[!UICONTROL No aggregation]選項，以便每次更新傳送參數。 如需循環傳送設定的詳細資訊，請參閱[本節](/help/automating/using/email-delivery.md#configuration)。

若要根據事件變數個人化傳送，您必須先將您要使用的變數宣告至傳送活動：

1. 選擇活動，然後按一下![](assets/dlv_activity_params-24px.png)按鈕以訪問設定。
1. 選擇&#x200B;**[!UICONTROL General]**&#x200B;標籤，然後新增事件變數，這些變數將可作為傳送中的個人化欄位使用。

   ![](assets/extsignal_activities_delivery.png)

1. 按一下 **[!UICONTROL Confirm]** 按鈕。

個人化欄位清單中現在提供宣告的事件變數。 您可以在傳送中使用它們，以執行下列動作：

* 定義要用於傳送的範本名稱。

   >[!NOTE]
   >
   >此動作僅適用於&#x200B;**recurring**&#x200B;傳送。

   ![](assets/extsignal_activities_template.png)

* 個人化交付：選取個人化欄位以設定傳送時，事件變數可在&#x200B;**[!UICONTROL Workflow parameters]**&#x200B;元素中使用。 您可將其用作任何個人化欄位，例如定義傳送主體、傳送者等。

   傳送個人化詳見[本節](../../designing/using/personalization.md)。

   ![](assets/extsignal_activities_perso.png)

**區段代碼**:根據事件變數定義區段代碼。

>[!NOTE]
>
>此動作可從任何可讓您定義區段代碼的活動執行，例如&#x200B;**[!UICONTROL Query]**&#x200B;或&#x200B;**[!UICONTROL Segmentation]**&#x200B;活動。

![](assets/extsignal_activities_segment.png)

**傳送標籤**:根據事件變數定義傳送標籤。

![](assets/extsignal_activities_label.png)
