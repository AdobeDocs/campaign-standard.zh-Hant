---
title: 閱讀讀者群
seo-title: 閱讀讀者群
description: 閱讀讀者群
seo-description: 「讀取對象」活動可讓您擷取現有對象，並套用其他篩選條件加以修飾。
page-status-flag: 從未啓動
uuid: 58c54e71-f4 a7-4ae9-80a3-33c379 ab1 db9
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: reference
topic-tags: 定位活動
discoiquuid: 674684e5-8830-4d2f-ba97-59ed4 ba7422 f
context-tags: ReadAudience，主要
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Read audience{#read-audience}

## Description {#description}

![](assets/prefill.png)

**[!UICONTROL Read audience]** 此活動可讓您擷取現有對象，並套用其他篩選條件加以修飾。

## Context of use {#context-of-use}

**[!UICONTROL Read audience]** 活動是較簡單的 **[!UICONTROL Query]** 活動版本，專為您僅需要選取現有對象所設計。

## Configuration {#configuration}

1. Drop a **[!UICONTROL Read audience]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. Select the audience you want to retrieve from the **[!UICONTROL Properties]** tab.

   You can retrieve audiences of the following types: **[!UICONTROL List]**, **[!UICONTROL Query]**, **[!UICONTROL File]** and **[!UICONTROL Experience Cloud]**. For more information on audience types, refer to the [Audiences](../../audiences/using/about-audiences.md) documentation.

   **[!UICONTROL Use a dynamic audience]** 此選項可讓您根據工作流程的事件變數來定義對象的名稱。For more on this, refer to the [Customizing activities with events variables](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables) section.

   ![](assets/readaudience_activity1.png)

1. If you want to apply additional filtering to the selected audience, add conditions via the **[!UICONTROL Source filtering]** tab of the activity.

   For more information about creating filtering conditions, refer to the [Creating queries](../../automating/using/editing-queries.md#creating-queries) documentation.

1. 確認活動的設定並儲存工作流程。

## Example: Reconcile a File audience with the database {#example--reconcile-a-file-audience-with-the-database}

This example shows how to use the **[!UICONTROL Read audience]** activity to reconcile an audience directly created from a file import.

執行檔案匯入時，您可以直接將其內容儲存在對象中。此對象為檔案對象，其資料不會連結至任何資料庫資源。

匯入工作流程的設計如下：

![](assets/readaudience_activity_example3.png)

* [載入檔案](../../automating/using/load-file.md) 活動會上傳包含從外部工具擷取之設定檔資料的檔案。

   例如：

   ```
   lastname;firstname;birthdate;email;crmID
   Smith;Hayden;23/05/1989;hayden.smith@example.com;124365
   Mars;Daniel;17/11/1987;dannymars@example.com;123545
   Smith;Clara;08/02/1989;hayden.smith@example.com;124567
   Durance;Allison;15/12/1978;allison.durance@example.com;120987
   Lucassen;Jody;28/03/1988;jody.lucassen@example.com;127634
   Binder;Tom;19/01/1982;tombinder@example.com;128653
   Binder;Tommy;19/01/1915;tombinder@example.com;134576
   Connor;Jade;10/10/1979;connor.jade@example.com;132452
   Mack;Clarke;02/03/1985;clarke.mack@example.com;149876
   Ross;Timothy;04/07/1986;timross@example.com;157643
   ```

* [「儲存對象](../../automating/using/save-audience.md) 」活動會將傳入的資料儲存為觀眾。由於資料尚未協調，觀眾是檔案對象，而資料也無法辨識為個人資料資料。

協調工作流程的設計如下：

![](assets/readaudience_activity_example2.png)

* **[!UICONTROL Read audience]** 活動會上傳在匯入工作流程中建立的檔案對象。對象資料尚未與Adobe Campaign資料庫和解。
* [「協調](../../automating/using/reconciliation.md) 」活動會透過 **[!UICONTROL Identification]** 標籤將傳入的資料識別為描述檔。For example by using the **email** field as reconciliation criteria.
* [更新資料](../../automating/using/update-data.md) 活動會插入並更新資料庫的描述檔資源與傳入資料。As the data is already identified as profiles, you can select the **[!UICONTROL Directly using the targeting dimension]** option and select **[!UICONTROL Profiles]** in the **[!UICONTROL Identification]** tab of the activity. 然後，您只需新增需要在「根據」索引標籤中更新的欄位清單。

## Example: Union on two refined audiences {#example--union-on-two-refined-audiences}

The workflow defined in this example shows the union of two **[!UICONTROL Read audience]** activities. 此工作流程的目標是傳送電子郵件給介於18到30歲的金級或銀級會員。

系統已建立特定對象，以追蹤金級和銀級會員。

工作流程的設計如下：

![](assets/readaudience_activity_example1.png)

* A first **[!UICONTROL Read audience]** activity that retrieves the Gold members audience and refines it by selecting only profiles that are between 18 and 30 years old.
* A second **[!UICONTROL Read audience]** activity that retrieves the Silver members audience and refines it by selecting only profiles that are between 18 and 30 years old.
* **[!UICONTROL Union]** 將兩 **[!UICONTROL Read audiences]** 個活動中的人口族群結合為一個最終人口族群的活動。
* **[!UICONTROL Email delivery]** 將電子郵件傳送給來自 **[!UICONTROL Union]** 活動中的人口的活動。

