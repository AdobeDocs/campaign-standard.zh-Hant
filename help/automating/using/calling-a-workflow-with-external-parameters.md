---
title: 使用外部參數來呼叫工作流程
seo-title: 使用外部參數來呼叫工作流程
description: 使用外部參數來呼叫工作流程
seo-description: 本節詳細資訊會鼓勵您使用外部參數來呼叫工作流程。
page-status-flag: 從未啓動
uuid: beccd1b6-8e6d-4504-9152-9ff537459c4a
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: reference
topic-tags: 工作流程一般運作
discoiquuid: 1676da91-55e3-414f-bcd3-be0804 b682 bd
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 267e30c603baf67020aadefad578f91b40dc042d

---


# Calling a workflow with external parameters{#calling-a-workflow-with-external-parameters}

促銷活動標準可讓您呼叫包含參數的工作流程(目標對象的目標、匯入的檔案名稱、訊息的一部分等等)。如此，您就可以輕鬆地將促銷活動自動化與外部系統整合。

讓我們舉下面的範例，我們希望直接從CMS傳送電子郵件。在這種情況下，您可以設定您的系統來選取觀眾和電子郵件內容至CMS。按一下「傳送」會將「促銷活動」工作流程與這些參數呼叫，讓您可將這些參數用於工作流程中，定義要用於傳送的對象和URL內容。

呼叫包含參數的工作流程的程序如下：

1. Declare the parameters in the **[!UICONTROL External signal]** activity. See [Declaring the parameters in the External signal activity](../../automating/using/calling-a-workflow-with-external-parameters.md#declaring-the-parameters-in-the-external-signal-activity).
1. Configure the **[!UICONTROL End]** activity or the API call to define the parameters and trigger the workflow **[!UICONTROL External signal]** activity.

觸發工作流程後，參數便會吸收到工作流程的事件變數中，並可用於工作流程中。See [Customizing a workflow with external parameters](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-a-workflow-with-external-parameters).

![](assets/extsignal_process.png)

## Declaring the parameters in the External signal activity {#declaring-the-parameters-in-the-external-signal-activity}

The first step to call a workflow with parameters is to declare them in an **[!UICONTROL External signal]** activity.

1. Open the **[!UICONTROL External signal]** activity, then select the **[!UICONTROL Parameters]** tab.
1. Click the **[!UICONTROL Create element]** button, then specify the name and type of each parameter.

   >[!CAUTION]
   >
   >Make sure that the name and number of parameters are identical to what is defined when calling the workflow (see [Defining the parameters when calling the workflow](../../automating/using/calling-a-workflow-with-external-parameters.md#defining-the-parameters-when-calling-the-workflow)). 此外，參數的類型必須與預期的值一致。

   ![](assets/extsignal_declaringparameters_1.png)

1. 在參數宣告後，完成工作流程設定，然後執行它。

## Defining the parameters when calling the workflow {#defining-the-parameters-when-calling-the-workflow}

本節詳細說明如何在呼叫工作流程時定義參數。For more on how to perform this operation from an API call, refer to the [REST APIs documentation](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html).

在定義參數之前，請先確定：

* The parameters have been declared in the **[!UICONTROL External Signal]** activity. See [Declaring the parameters in the External signal activity](../../automating/using/calling-a-workflow-with-external-parameters.md#declaring-the-parameters-in-the-external-signal-activity).
* 包含訊號活動的工作流程。

To configure the **[!UICONTROL End]** activity, follow the steps below:

1. Open the **[!UICONTROL End]** activity, then select the **[!UICONTROL External signal]** tab.
1. 選取您要呼叫的工作流程和外部訊號活動。
1. Click the **[!UICONTROL Create element]** button to add a parameter, then fill in its name and value.

   * **[!UICONTROL Name]**：已在 **[!UICONTROL External signal]** 活動中宣告的名稱(請參閱 [「宣告外部訊號活動](../../automating/using/calling-a-workflow-with-external-parameters.md#declaring-the-parameters-in-the-external-signal-activity)中的參數」)。
   * **[!UICONTROL Value]**：您要指派給參數的值。The value should follow the **Standard syntax**, described in [this section](../../automating/using/advanced-expression-editing.md#standard-syntax).
   ![](assets/extsignal_definingparameters_2.png)

   >[!CAUTION]
   >
   >Make sure that all the parameters have been declared in the **[!UICONTROL External signal]** activity. 否則，執行活動時會發生錯誤。

1. 在定義參數後，請確認活動，然後儲存工作流程。

## Monitoring the events variables {#monitoring-the-events-variables}

您可以監控工作流程中可用的事件變數，包括宣告的外部參數。若要執行此動作，請執行下列步驟：

1. Select the activity that follows the **[!UICONTROL External signal]** activity, then click the **[!UICONTROL Log and tasks]** button.
1. In the **[!UICONTROL Tasks]** tab, click ![](assets/edit_darkgrey-24px.png) button.

   ![](assets/extsignal_monitoring_2.png)

1. 任務的執行上下文會顯示(ID、狀態、持續時間等)，包括現在可用於工作流程的所有事件變數。

   ![](assets/extsignal_monitoring_3.png)

## Customizing a workflow with external parameters {#customizing-a-workflow-with-external-parameters}

觸發工作流程後，參數會吸收到事件變數中，並可用來自訂工作流程的活動。

They can, for example, be used to define which audience to read in the **[!UICONTROL Read audience]** activity, the name of the file to transfer in the **[!UICONTROL Transfer file]** activity, etc.

Activities that can be customized with events variables are detailed in [this section](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables).

### Using events variables {#using-events-variables}

Events variables are used within an expression that must respect the **[Standard syntax](../../automating/using/advanced-expression-editing.md#standard-syntax)**.

The syntax to use events variables must follow the format below, and use the parameter's name that has been defined in the **[!UICONTROL External signal]** activity (see [Declaring the parameters in the External signal activity](../../automating/using/calling-a-workflow-with-external-parameters.md#declaring-the-parameters-in-the-external-signal-activity)):

```
$(vars/@parameterName)
```

In this syntax, the **$** function returns **string** data type. 如果您想要指定其他類型的資料，請使用下列函數：

* **$ long**：整數。
* **$ float**：小數數。
* **$布林**&#x200B;值：true/false。
* **$ atetime**：時間戳記。

在活動中使用變數時，介面可提供呼叫。

![](assets/extsignal_callparameter.png)

* ![](assets/extsignal_picker.png)：在工作流程中可用的所有變數中選取事件變數(請參閱)。

   ![](assets/wkf_test_activity_variables.png)

* ![](assets/extsignal_expression_editor.png)：編輯結合變數和函數的運算式。For more on the Expression editor, refer to [this section](../../automating/using/advanced-expression-editing.md).

   ![](assets/wkf_test_activity_variables_expression.png)

**相關主題：**

* [編輯運算式](../../automating/using/advanced-expression-editing.md#edit-an-expression)
* [標準語法](../../automating/using/advanced-expression-editing.md#standard-syntax)
* [函數清單](../../automating/using/list-of-functions.md)

### Customizing activities with events variables {#customizing-activities-with-events-variables}

可使用事件變數來自訂下一節所列的多個活動。For more on how to call a variable from an activity, refer to [this section](../../automating/using/calling-a-workflow-with-external-parameters.md#using-events-variables).

**[!UICONTROL Read audience]** 活動：定義對象以根據事件變數進行定位。

For more on how to use the activity, refer to the [dedicated section](../../automating/using/read-audience.md).

![](assets/extsignal_activities_audience.png)

**[!UICONTROL Test]** 活動：根據事件變數建立條件。

For more on how to use the activity, refer to the [dedicated section](../../automating/using/test.md).

![](assets/extsignal_activities_test.png)

**[!UICONTROL Transfer file]** 活動：自訂檔案以根據事件變數進行傳輸。

For more on how to use the activity, refer to the [dedicated section](../../automating/using/transfer-file.md).

![](assets/extsignal_activities_transfer.png)

**[!UICONTROL Query]** 活動：參數可在查詢中參照，方法是使用結合事件變數和函數的運算式。To do this, add a rule then click the **[!UICONTROL Advanced mode]** link to access the expression editing window (see [Advanced expression editing](../../automating/using/advanced-expression-editing.md)).

For more on how to use the activity, refer to the [dedicated section](../../automating/using/query.md).

![](assets/extsignal_activities_query.png)

**[!UICONTROL Channels]** 活動：根據事件變數個人化。

>[!NOTE]
>
>傳送參數'值'會在每次準備完成時擷取。
>
>Recurring deliveries preparation is based on the delivery **aggregation period**. 例如，如果匯總期間是「依天」，則傳送將每天只重新準備一次。如果傳送參數的值在當天經過修改，則不會在傳送中更新，因為它已準備就緒一次。
>
>If you plan on calling the workflow multiple times a day, use the [!UICONTROL No aggregation] option, so that the delivery parameters are updated each time. For more on recurring deliveries configuration, refer to [this section](/help/automating/using/email-delivery.md#configuration).

若要根據事件變數個人化傳送，您必須先將變數中的變數宣告為要使用的變數：

1. Select the activity, then click the ![](assets/dlv_activity_params-24px.png) button to access the settings.
1. Select the **[!UICONTROL General]** tab, then add the events variables that will be available as personalization fields in the delivery.

   ![](assets/extsignal_activities_delivery.png)

1. Click the **[!UICONTROL Confirm]** button.

已宣告事件變數現在可從個人化欄位清單中取得。您可以在傳送中使用它們執行下列動作：

* 定義要用於傳送的範本名稱。

   >[!NOTE]
   >
   >This action is available for **recurring** deliveries only.

   ![](assets/extsignal_activities_template.png)

* Personalize the delivery: when selecting a personalization field to configure a delivery, events variables are available in the **[!UICONTROL Workflow parameters]** element. 您可以將其用作任何個人化欄位，例如定義傳送主體、寄件者等。

   Delivery personalization is detailed in [this section](../../designing/using/about-personalization.md).

   ![](assets/extsignal_activities_perso.png)

**區段代碼**：根據事件變數定義區段代碼。

>[!NOTE]
>
>This action can be performed from any activity that lets you define a segment code like, for example, **[!UICONTROL Query]** or **[!UICONTROL Segmentation]** activities.

![](assets/extsignal_activities_segment.png)

**傳送標籤**：根據事件變數定義傳送標籤。

![](assets/extsignal_activities_label.png)

## Use case {#use-case}

以下的使用案例顯示如何在工作流程中使用參數來呼叫工作流程。

其目標是從含有外部參數的API呼叫中觸發工作流程。此工作流程會從檔案載入資料並建立關聯的觀眾。建立觀眾後，會觸發第二個工作流程，以API呼叫中定義的外部參數個人化訊息。

若要執行此使用案例，您必須執行下列動作：

1. **進行API呼叫** ，以外部參數觸發Workflow1。See [Step 1: Configuring the API call](../../automating/using/calling-a-workflow-with-external-parameters.md#step-1--configuring-the-api-call).
1. **建立工作流程1**：工作流程將會傳輸檔案並將它載入資料庫中。然後，它會測試資料是否空白，並最後將描述檔儲存給觀眾。最後，它會觸發Workflow2。See [Step 2: Configuring Workflow 1](../../automating/using/calling-a-workflow-with-external-parameters.md#step-2--configuring-workflow-1).
1. **建立工作流程2**：工作流程會讀取已在Workflow中建立的觀眾，然後傳送個人化訊息至描述檔，並使用參數自訂區段代碼。See [Step 3: Configuring Workflow 2](../../automating/using/calling-a-workflow-with-external-parameters.md#step-3--configuring-workflow-2).

![](assets/extsignal_uc_process.png)

### Prerequisites {#prerequisites}

Before configuring the workflows, you need to create Workflow 1 and 2 with an **[!UICONTROL External signal]** activity in each of them. 如此一來，您就可以在呼叫工作流程時，鎖定這些訊號活動。

### Step 1: Configuring the API call {#step-1--configuring-the-api-call}

建立API呼叫，以參數觸發Workflow1。For more on the API call syntax, refer to the [Campaign Standard REST APIs documentation](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html).

在我們的案例中，我們想要將工作流程與下列參數進行呼叫：

* **FilterTarget**：我們要匯入資料庫的檔案名稱。
* **DiscountDesc**：我們想要在提供中顯示的說明。

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/<TRIGGER_URL>
-H 'Authorization: Bearer <ACCESS_TOKEN>' 
-H 'Cache-Control: no-cache' 
-H 'X-Api-Key: <API_KEY>' 
-H 'Content-Type: application/json;charset=utf-8' 
-H 'Content-Length:79' 
-i
-d {
-d "source:":"API",
-d "parameters":{
-d "fileToTarget":"profile.txt",
-d "discountDesc":"Running shoes"
-d } 
```

### Step 2: Configuring Workflow 1 {#step-2--configuring-workflow-1}

Workflow的建置方式如下：

* **[!UICONTROL External signal]** 活動：必須宣告外部參數，以便在工作流程中使用。
* **[!UICONTROL Transfer file]** 活動：以參數定義的名稱匯入檔案。
* **[!UICONTROL Load file]** 活動：將資料從匯入的檔案載入資料庫。
* **[!UICONTROL Update data]** 活動：使用匯入檔案中的資料插入或更新資料庫。
* **[!UICONTROL Test]** 活動：檢查是否已匯入資料。
* **[!UICONTROL Save audience]** 活動：如果檔案包含資料，請將描述檔儲存給對象。
* **[!UICONTROL End activity]** 活動：以您要在其中使用的參數來呼叫Workflow2。

![](assets/extsignal_uc_wkf1.png)

請依照下列步驟來設定工作流程：

1. 宣告API呼叫中已定義的參數。To do this, open the **[!UICONTROL External signal]** activity, then add the parameters' names and types.

   ![](assets/extsignal_uc1.png)

1. Add a **[!UICONTROL Transfer file]** activity to import data into the database.To do this, drag and drop the activity, open it, then select the **[!UICONTROL Protocol]** tab.
1. Select the **[!UICONTROL Use a dynamic file path]** option, then use the **fileToTarget** parameter as the file to transfer:

   ```
   $(vars/@fileToTarget)
   ```

   ![](assets/extsignal_uc2.png)

1. 將資料從檔案載入資料庫。

   To do this, drag and drop a **[!UICONTROL Load file]** activity into the workflow, then configure it according to your needs.

1. 使用匯入檔案中的資料插入並更新資料庫。

   To do this, drag and drop an **[!UICONTROL Update data]** activity, then select the **[!UICONTROL Identification]** tab to add a reconciliation criteria (in our case the **email** field).

   ![](assets/extsignal_uc3.png)

1. Select the **[!UICONTROL Fields to update]** tab, then specify the fields to update in the database (in our case the **firstname** and **email** fields).

   ![](assets/extsignal_uc4.png)

1. 檢查是否從檔案擷取資料。To do this, drag and drop a **[!UICONTROL Test]** activity into the workflow, then click the **[!UICONTROL Add an element]** button to add a condition.
1. 命名並定義條件。在我們的案例中，我們想要測試傳出轉換是否包含下列語法的資料：

   ```
   $long(vars/@recCount)>0
   ```

   ![](assets/extsignal_uc5.png)

1. 如果擷取資料，將其儲存至對象。To do this, add a **[!UICONTROL Save audience]** activity to the **Target not empty** transition, then open it.
1. Select the **[!UICONTROL Use a dynamic label]** option, then use the **fileToTarget** parameter as the label of the audience:

   ```
   $(vars/@fileToTarget)
   ```

   ![](assets/extsignal_uc6.png)

1. Drag and drop an **[!UICONTROL End]** activity that will call Workflow 2 with parameters, then open it.
1. Select the **[!UICONTROL External signal]** tab, then specify the workflow to trigger and its associated signal activity.
1. 定義您要在Workflow及其相關值中使用的參數。

   In our case, we want to pass the parameters originally defined in the API call (**fileToTarget** and **discountDesc**), and an additional **segmentCode** parameter with a constant value ("20% discount").

   ![](assets/extsignal_uc7.png)

工作流程1已設定，您現在可以建立工作流程2。For more on this, refer to [this section](../../automating/using/calling-a-workflow-with-external-parameters.md#step-3--configuring-workflow-2).

### Step 3: Configuring Workflow 2 {#step-3--configuring-workflow-2}

Workflow的建置方式如下：

* **[!UICONTROL External signal]** 活動：參數必須宣告，以便在工作流程中使用。
* **[!UICONTROL Read audience]** 活動：讀取儲存在Workflow中的觀眾。
* **[!UICONTROL Email delivery]** 活動：傳送週期性訊息給目標對象，並使用參數個人化。

![](assets/extsignal_uc_wkf2.png)

請依照下列步驟來設定工作流程：

1. 宣告已在Workflow中定義的參數。

   To do this, open the **[!UICONTROL External signal]** activity, then add the name and type of each parameter defined in the **[!UICONTROL End]** activity of Workflow 1.

   ![](assets/extsignal_uc8.png)

1. 使用已儲存在Workflow中的觀眾。To do this, drag and drop a **[!UICONTROL Read audience]** activity into the workflow, then open it.
1. Select the **[!UICONTROL Use a dynamic audience]** option, then use the **fileToTarget** parameter as the name of the audience to read:

   ```
   $(vars/@fileToTarget)
   ```

   ![](assets/extsignal_uc9.png)

1. Name the outbound transition according to the **segmentCode** parameter.

   To do this, select the **[!UICONTROL Transition]** tab, then the **[!UICONTROL Use a dynamic segment code]** option.

1. Use the **segmentCode** parameter as the name of the outbound transition:

   ```
   $(vars/@segmentCode)
   ```

   ![](assets/extsignal_uc10.png)

1. Drag and drop an **[!UICONTROL Email delivery]** activity to send a message to the audience.
1. Identify the parameters to use in the message to personalize it with the **discountDesc** parameter. 若要這麼做，請開啓活動的進階選項，然後新增參數名稱和值。

   ![](assets/extsignal_uc10b.png)

1. 您現在可以設定訊息。Open the activity, then select **[!UICONTROL Recurring email]**.

   ![](assets/extsignal_uc11.png)

1. 選取要使用的範本，然後根據您的需求定義電子郵件屬性。
1. Use the **discountDesc** parameter as a personalization field. 若要這麼做，請從個人化欄位清單中選取它。

   ![](assets/extsignal_uc13.png)

1. 您現在可以完成設定訊息，然後照常傳送。

   ![](assets/extsignal_uc14.png)

### Executing the workflows {#executing-the-workflows}

建立工作流程後，您就可以執行這些工作流程。請確定兩個工作流程已開始，然後再執行API呼叫。
