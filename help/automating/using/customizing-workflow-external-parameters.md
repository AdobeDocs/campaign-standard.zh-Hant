---
title: 使用外部參數呼叫工作流程
description: 本節詳細說明如何使用外部參數呼叫工作流程。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 8c1a47ed-3467-4fcd-8747-86f0e8f15cec
source-git-commit: 13d419c5fc51845ee14f8a3b288f4c467e0a60d9
workflow-type: tm+mt
source-wordcount: '813'
ht-degree: 1%

---

# 使用外部參數自訂工作流程 {#customizing-a-workflow-with-external-parameters}

觸發工作流程後，參數會擷取至事件變數中，並可用來自訂工作流程的活動。

例如，它們可用來定義要在 **[!UICONTROL Read audience]** 活動，即要在 **[!UICONTROL Transfer file]** 活動等。 (請參閱 [本頁](../../automating/using/customizing-workflow-external-parameters.md))。

## 使用事件變數 {#using-events-variables}

事件變數用於必須遵循 [標準語法](../../automating/using/advanced-expression-editing.md#standard-syntax).

使用事件變數的語法必須遵循下列格式，並使用中已定義之參數名稱 **[!UICONTROL External signal]** 活動(請參閱 [在外部信號活動中聲明參數](../../automating/using/declaring-parameters-external-signal.md)):

```
$(vars/@parameterName)
```

在此語法中， **$** 函式返回 **字串** 資料類型。 如果要指定其他類型的資料，請使用下列函式：

* **$long**:整數。
* **浮動**:小數位數。
* **$布林值**:true/false。
* **$datetime**:時間戳記。

在活動中使用變數時，介面會提供呼叫變數的協助。

![](assets/extsignal_callparameter.png)

* ![](assets/extsignal_picker.png):在工作流程中可用的所有變數中選取事件變數。

   ![](assets/wkf_test_activity_variables.png)

* ![](assets/extsignal_expression_editor.png):編輯結合變數和函式的運算式(請參閱 [本頁](../../automating/using/advanced-expression-editing.md))。

   ![](assets/wkf_test_activity_variables_expression.png)

   此清單提供的函式可讓您執行複雜的篩選。 這些函式在 [本節](../../automating/using/list-of-functions.md).

   此外，您也可以使用下列函式，這些函式可在所有允許您在使用外部參數呼叫工作流程後使用事件變數的活動中使用(請參閱 [本節](../../automating/using/customizing-workflow-external-parameters.md#customizing-activities-with-events-variables)):

   | 名稱 | 說明 | 語法 |
   | ---------|----------|---------|
   | EndWith | 指出字串（第1參數）結尾是否為特定字串（第2參數）。 | EndWith(&lt;string>,&lt;string>) |
   | startWith | 指出字串（第1參數）是否以特定字串（第2參數）開頭。 | startWith(&lt;string>,&lt;string>) |
   | Extract | 使用分隔符返回字串的第一個字元。 | Extract(&lt;string>,&lt;separator>) |
   | ExtractRight | 使用分隔符返回字串的最後一個字元。 | ExtractRight(&lt;string>,&lt;separator>) |
   | DateFormat | 使用第2個參數中指定的格式設定日期的格式(範例：「%4Y%2M%2D」) | DateFormat(&lt;date>,&lt;format>) |
   | 檔案名 | 返回檔案路徑的名稱。 | FileName(&lt;string>) |
   | FileExt | 傳回檔案路徑的副檔名。 | FileExt(&lt;string>) |
   | GetOption | 返回指定函式的值。 | GetOption(&lt;optionname>) |
   | IsNull | 指出字串或日期是否為空。 | IsNull(&lt;string date=&quot;&quot;>) |
   | UrlUtf8編碼 | 以UTF8編碼URL。 | UrlUtf8Encode(&lt;string>) |

## 使用事件變數自訂活動 {#customizing-activities-with-events-variables}

事件變數可用來自訂數個活動，如下節所列。 如需如何從活動呼叫變數的詳細資訊，請參閱 [本節](../../automating/using/customizing-workflow-external-parameters.md#using-events-variables).

**[!UICONTROL Read audience]** 活動：根據事件變數定義要定位的對象。 如需如何使用活動的詳細資訊，請參閱 [本節](../../automating/using/read-audience.md).

![](assets/extsignal_activities_audience.png)

**[!UICONTROL Test]** 活動：根據事件變數建立條件。 如需如何使用活動的詳細資訊，請參閱 [本節](../../automating/using/test.md).

![](assets/extsignal_activities_test.png)

**[!UICONTROL Transfer file]** 活動：根據事件變數自訂要傳輸的檔案。 如需如何使用活動的詳細資訊，請參閱 [本節](../../automating/using/transfer-file.md).

![](assets/extsignal_activities_transfer.png)

**[!UICONTROL Query]** 活動：可使用結合事件變數和函式的運算式，在查詢中參考參數。 若要這麼做，請新增規則，然後按一下 **[!UICONTROL Advanced mode]** 連結以存取運算式編輯視窗(請參閱 [進階運算式編輯](../../automating/using/advanced-expression-editing.md))。

如需如何使用活動的詳細資訊，請參閱 [本節](../../automating/using/query.md).

![](assets/extsignal_activities_query.png)

**[!UICONTROL Channels]** 活動：根據事件變數進行個人化傳送。

>[!NOTE]
>
>每次準備傳送時，都會擷取傳送參數的值。
>
>循環傳送準備以傳送為基礎 **匯總期間**. 例如，如果匯總期間為「依日」，則傳送將僅每天重新準備一次。 如果在當天修改了傳送參數的值，則傳送中不會更新，因為已準備一次。
>
>如果您計畫每天呼叫工作流程多次，請使用 [!UICONTROL No aggregation] 選項，以便每次都更新傳送參數。 如需循環傳送設定的詳細資訊，請參閱 [本節](/help/automating/using/email-delivery.md#configuration).

若要根據事件變數個人化傳送，您必須先將您要使用的變數宣告至傳送活動中：

1. 選取活動，然後按一下 ![](assets/dlv_activity_params-24px.png) 按鈕來存取設定。
1. 選取 **[!UICONTROL General]** 標籤，然後新增事件變數，這些變數將可在傳送中作為個人化欄位使用。

   ![](assets/extsignal_activities_delivery.png)

1. 按一下 **[!UICONTROL Confirm]** 按鈕。

現在可從個人化欄位清單中使用宣告事件變數。 您可以在傳送中使用這些欄位來執行下列動作：

* 定義用於傳送的範本名稱。

   >[!NOTE]
   >
   >此動作適用於 **循環** 僅傳送。

   ![](assets/extsignal_activities_template.png)

* 個人化傳送：選取個人化欄位以設定傳送時，事件變數可在 **[!UICONTROL Workflow parameters]** 元素。 您可以將它們用作任何個人化欄位，例如定義傳送主旨、寄件者等。

   傳送個人化在 [本節](../../designing/using/personalization.md).

   ![](assets/extsignal_activities_perso.png)

**區段代碼**:根據事件變數定義區段代碼。

>[!NOTE]
>
>此動作可從任何可讓您定義區段代碼的活動執行，例如 **[!UICONTROL Query]** 或 **[!UICONTROL Segmentation]** 活動。

![](assets/extsignal_activities_segment.png)

**傳遞標籤**:根據事件變數定義傳送標籤。

![](assets/extsignal_activities_label.png)
