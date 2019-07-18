---
title: 外部訊號
seo-title: 外部訊號
description: 外部訊號
seo-description: 在其他工作流程中成功符合某些條件時，外部訊號活動會觸發工作流程。
page-status-flag: 從未啓動
uuid: 884b6df-bd9-440b-8336-004b80 c76 def
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: reference
topic-tags: 執行活動
discoiquuid: 911c71b5-da8 b-4916-b645-13bba6 d21715
context-tags: doment，main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# External signal{#external-signal}

## Description {#description}

![](assets/signal.png)

**[!UICONTROL External signal]** 當某些條件成功符合其他工作流程或REST API呼叫時，活動會觸發工作流程。

## Context of use {#context-of-use}

**[!UICONTROL External signal]** 此活動用於組織和協調不同客戶歷程中屬於不同工作流程的不同流程。它可讓您從另一個工作流程開始，支援更複雜的客戶歷程，並且能夠在發生問題時更好地監視和回應。

**[!UICONTROL External signal]** 此活動旨在作為工作流程的第一個活動。It can be triggered from the **[!UICONTROL End]** activity of another workflow or from a REST API call (for more on this, refer to the [API documentation](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#triggering-a-signal-activity) ).

觸發後，可以定義外部參數並在工作流程事件變數中使用。The process to call a workflow with external parameters is detailed in [this section](../../automating/using/calling-a-workflow-with-external-parameters.md).

>[!NOTE]
>
>活動的觸發頻率不會超過每10分鐘。

Note that an **[!UICONTROL External signal]** activity can be triggered from several different events. In that case, the **[!UICONTROL External signal]** is triggered as soon as one of the source workflows or API call is executed. 不需要所有來源工作流程都完成。

## Configuration {#configuration}

When configuring an external signal, it is important to first configure the **[!UICONTROL External signal]** activity in the destination workflow. Once this configuration is done, the **[!UICONTROL External signal]** activity of this workflow becomes available to configure the **[!UICONTROL End]** activity of the source workflow.

1. Drag and drop an **[!UICONTROL External signal]** activity into your destination workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. 編輯活動的標籤。This label is needed when configuring the source workflow that triggers the **[!UICONTROL External signal]**.

   If you want to call the workflow with parameters, use the **[!UICONTROL Parameters]** area to declare them. For more on this, refer to [this section](../../automating/using/calling-a-workflow-with-external-parameters.md#declaring-the-parameters-in-the-external-signal-activity).

   ![](assets/external_signal_configuration.png)

1. 確認活動的設定，新增您需要的其他活動並儲存工作流程。

   >[!NOTE]
   >
   >如果您想要從其他工作流程觸發目的地工作流程，請繼續下列步驟。If you want to trigger the destination workflow from a REST API call, consult the [API documentation](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#triggering-a-signal-activity) to get more details.

1. Open the source workflow and select an **[!UICONTROL End]** activity. If there is no **[!UICONTROL End]** activity available, add one after the last activity of a branch of the workflow.

   有些活動預設沒有對外轉場。From the **[!UICONTROL Properties]** tab of these activities, you can add an outbound transition.

   For example, in an **[!UICONTROL Update data]** activity, go to the **[!UICONTROL Transitions]** tab and check the **[!UICONTROL Add an outbound transition without the population]** option. 此選項可讓您新增不包含任何資料且不會消耗系統上任何不必要空間的轉場。It is just used to connect the extra **[!UICONTROL End]** activity that triggers the destination workflow.

   ![](assets/external_signal_empty_transition.png)

1. In the **[!UICONTROL External signal]** tab of the **[!UICONTROL End]** activity, select the destination workflow as well as the **[!UICONTROL External signal]** activity to trigger within that workflow.

   When you set an **[!UICONTROL End]** activity to trigger another workflow, its icon is updated with an additional signal symbol.

   If you want to call the workflow with parameters, use the **[!UICONTROL Parameters and values]** area. For more on this, refer to [this section](../../automating/using/calling-a-workflow-with-external-parameters.md#defining-the-parameters-when-calling-the-workflow).

   ![](assets/external_signal_end.png)

1. 儲存來源工作流程。

Once the **[!UICONTROL End]** activity of the source workflow or the REST API call is executed, the destination workflow is automatically triggered from the **[!UICONTROL External signal]** activity.

>[!NOTE]
>
>必須手動啓動目的地工作流程，才能觸發。When started, the **[!UICONTROL External activity]** is activated and waits for the signal from the source workflow.

## Example {#example}

The following example illustrates the **[!UICONTROL External signal]** activity in a typical use case. 資料匯入是在來源工作流程中執行。匯入完成並更新資料庫後，就會觸發第二個工作流程。此第二個工作流程可用來更新匯入資料的匯總。

來源工作流程如下所示：

* [載入檔案](../../automating/using/load-file.md) 活動會上傳包含新購買資料的檔案。Note that the [database has been extended](../../developing/using/data-model-concepts.md) accordingly as purchase data are not present by default in the datamart.

   例如：

   ```
   tcode;tdate;customer;product;tamount
   aze123;21/05/2015;dannymars@example.com;A2;799
   aze124;28/05/2015;dannymars@example.com;A7;8
   aze125;31/07/2015;john.smith@example.com;A7;8
   aze126;14/12/2015;john.smith@example.com;A10;4
   aze127;02/01/2016;dannymars@example.com;A3;79
   aze128;04/03/2016;clara.smith@example.com;A8;149
   ```

* [「協調](../../automating/using/reconciliation.md) 」活動會建立匯入資料與資料庫之間的連結，使交易資料能夠正確連接至描述檔和產品。
* [「更新資料](../../automating/using/update-data.md) 」活動會將資料庫的「交易」資源插入並更新至接收的資料。
* **[!UICONTROL End]** 活動會觸發目的地工作流程，用於更新匯總。

![](assets/signal_example_source1.png)

目的地工作流程顯示如下：

* **[!UICONTROL External signal]** 活動等待來源工作流程成功完成。
* [A Query](../../automating/using/query.md#enriching-data) activity target profiles and enrich them with a collection set to regture the last purchase date.
* [更新資料](../../automating/using/update-data.md) 活動會將額外資料儲存在專屬自訂欄位中。Note that the profile resource has been extended to add the **Last purchase date** field.

![](assets/signal_example_source2.png)

