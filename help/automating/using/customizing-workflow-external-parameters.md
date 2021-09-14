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
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '813'
ht-degree: 1%

---

# 使用外部參數自訂工作流程 {#customizing-a-workflow-with-external-parameters}

觸發工作流程後，參數會擷取至事件變數中，並可用來自訂工作流程的活動。

例如，它們可用來定義要在&#x200B;**[!UICONTROL Read audience]**&#x200B;活動中讀取的對象、要在&#x200B;**[!UICONTROL Transfer file]**&#x200B;活動中傳輸的檔案名稱等。 （請參閱[此頁面](../../automating/using/customizing-workflow-external-parameters.md)）。

## 使用事件變數 {#using-events-variables}

事件變數用於必須遵循[標準語法](../../automating/using/advanced-expression-editing.md#standard-syntax)的運算式中。

使用事件變數的語法必須遵循以下格式，並使用&#x200B;**[!UICONTROL External signal]**&#x200B;活動中已定義的參數名稱（請參閱[在外部信號活動](../../automating/using/declaring-parameters-external-signal.md)中聲明參數）:

```
$(vars/@parameterName)
```

在此語法中，**$**&#x200B;函式返回&#x200B;**string**&#x200B;資料類型。 如果要指定其他類型的資料，請使用下列函式：

* **$long**:整數。
* **$float**:小數位數。
* **$布林值**:true/false。
* **$datetime**:時間戳記。

在活動中使用變數時，介面會提供呼叫變數的協助。

![](assets/extsignal_callparameter.png)

* ![](assets/extsignal_picker.png):在工作流程中可用的所有變數中選取事件變數。

   ![](assets/wkf_test_activity_variables.png)

* ![](assets/extsignal_expression_editor.png):編輯結合變數和函式的運算式(請參 [閱本頁面](../../automating/using/advanced-expression-editing.md))。

   ![](assets/wkf_test_activity_variables_expression.png)

   此清單提供的函式可讓您執行複雜的篩選。 在[本節](../../automating/using/list-of-functions.md)中詳細介紹了這些函式。

   此外，您也可以使用下列函式，這些函式可在所有允許您在使用外部參數呼叫工作流程後使用事件變數的活動中使用（請參閱[此區段](../../automating/using/customizing-workflow-external-parameters.md#customizing-activities-with-events-variables)）:

   | 名稱 | 說明 | 語法 |
   | ---------|----------|---------|
   | EndWith | 指出字串（第1參數）結尾是否為特定字串（第2參數）。 | EndWith(&lt;String>,&lt;String>) |
   | startWith | 指出字串（第1參數）是否以特定字串（第2參數）開頭。 | startWith(&lt;String>,&lt;String>) |
   | Extract | 使用分隔符返回字串的第一個字元。 | Extract(&lt;String>,&lt;Separator>) |
   | ExtractRight | 使用分隔符返回字串的最後一個字元。 | ExtractRight(&lt;String>,&lt;Separator>) |
   | DateFormat | 使用第2個參數中指定的格式設定日期的格式(範例： 「%4Y%2M%2D」) | DateFormat(&lt;Date>,&lt;Format>) |
   | 檔案名 | 返回檔案路徑的名稱。 | FileName(&lt;String>) |
   | FileExt | 傳回檔案路徑的副檔名。 | FileExt(&lt;String>) |
   | GetOption | 返回指定函式的值。 | GetOption(&lt;optionName>) |
   | IsNull | 指出字串或日期是否為空。 | IsNull(&lt;String/date>) |
   | UrlUtf8編碼 | 以UTF8編碼URL。 | UrlUtf8Encode(&lt;String>) |

## 使用事件變數自訂活動 {#customizing-activities-with-events-variables}

事件變數可用來自訂數個活動，如下節所列。 如需如何從活動呼叫變數的詳細資訊，請參閱[此區段](../../automating/using/customizing-workflow-external-parameters.md#using-events-variables)。

**[!UICONTROL Read audience]** 活動：根據事件變數定義要定位的對象。有關如何使用活動的詳細資訊，請參閱[此區段](../../automating/using/read-audience.md)。

![](assets/extsignal_activities_audience.png)

**[!UICONTROL Test]** 活動：根據事件變數建立條件。有關如何使用活動的詳細資訊，請參閱[此區段](../../automating/using/test.md)。

![](assets/extsignal_activities_test.png)

**[!UICONTROL Transfer file]** 活動：根據事件變數自訂要傳輸的檔案。有關如何使用活動的詳細資訊，請參閱[此區段](../../automating/using/transfer-file.md)。

![](assets/extsignal_activities_transfer.png)

**[!UICONTROL Query]** 活動：可使用結合事件變數和函式的運算式，在查詢中參考參數。要執行此操作，請新增規則，然後按一下&#x200B;**[!UICONTROL Advanced mode]**&#x200B;連結以存取運算式編輯視窗（請參閱[進階運算式編輯](../../automating/using/advanced-expression-editing.md)）。

有關如何使用活動的詳細資訊，請參閱[此區段](../../automating/using/query.md)。

![](assets/extsignal_activities_query.png)

**[!UICONTROL Channels]** 活動：根據事件變數進行個人化傳送。

>[!NOTE]
>
>每次準備傳送時，都會擷取傳送參數的值。
>
>循環傳送準備是根據傳送&#x200B;**匯總期間**。 例如，如果匯總期間為「依日」，則傳送將僅每天重新準備一次。 如果在當天修改了傳送參數的值，則傳送中不會更新，因為已準備一次。
>
>如果您計畫每天呼叫工作流程多次，請使用[!UICONTROL No aggregation]選項，以便每次都更新傳送參數。 如需循環傳送設定的詳細資訊，請參閱[此區段](/help/automating/using/email-delivery.md#configuration)。

若要根據事件變數個人化傳送，您必須先將您要使用的變數宣告至傳送活動中：

1. 選取活動，然後按一下![](assets/dlv_activity_params-24px.png)按鈕以存取設定。
1. 選取&#x200B;**[!UICONTROL General]**&#x200B;標籤，然後新增將在傳送中作為個人化欄位可用的事件變數。

   ![](assets/extsignal_activities_delivery.png)

1. 按一下 **[!UICONTROL Confirm]** 按鈕。

現在可從個人化欄位清單中使用宣告事件變數。 您可以在傳送中使用這些欄位來執行下列動作：

* 定義用於傳送的範本名稱。

   >[!NOTE]
   >
   >此動作僅適用於&#x200B;**recurring**&#x200B;傳送。

   ![](assets/extsignal_activities_template.png)

* 個人化傳送：選取要設定傳送的個人化欄位時，事件變數可在&#x200B;**[!UICONTROL Workflow parameters]**&#x200B;元素中使用。 您可以將它們用作任何個人化欄位，例如定義傳送主旨、寄件者等。

   在[此區段](../../designing/using/personalization.md)中會詳細說明傳送個人化。

   ![](assets/extsignal_activities_perso.png)

**區段代碼**:根據事件變數定義區段代碼。

>[!NOTE]
>
>此動作可從可讓您定義區段代碼的任何活動執行，例如&#x200B;**[!UICONTROL Query]**&#x200B;或&#x200B;**[!UICONTROL Segmentation]**&#x200B;活動。

![](assets/extsignal_activities_segment.png)

**傳遞標籤**:根據事件變數定義傳送標籤。

![](assets/extsignal_activities_label.png)
