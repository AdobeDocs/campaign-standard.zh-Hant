---
title: SMS傳送
seo-title: SMS傳送
description: SMS傳送
seo-description: SMS傳送活動可讓您設定在工作流程中傳送單一傳送SMS或循環SMS。
page-status-flag: 從未啓動
uuid: 736078c6-ac91-4440-825b-4a6 ae31894 ef
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: reference
topic-tags: channel-activity
discoiquuid: 978592b8-989a-446a-8a84-12b7fecfc130
context-tags: sms，main；傳送，SMSContent，back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# SMS delivery{#sms-delivery}

## Description {#description}

![](assets/sms.png)

![](assets/recurrentsms.png)

**[!UICONTROL SMS delivery]** 此活動可讓您設定工作流程中的SMS。This can be a **single send** SMS and sent just once, or it can be a **recurring** SMS.

單一傳送SMS訊息是標準SMS，只需傳送一次。

循環SMS訊息可讓您在定義的期間內，多次傳送相同的SMS至不同的目標。您可以匯總每個時段的傳送，取得符合您需求的報表。

## Context of use {#context-of-use}

**[!UICONTROL SMS delivery]** 此活動通常用於將SMS傳送至相同工作流程中計算的目標。

當連結至排程器時，您可以定義循環SMS訊息。

SMS收件者可透過定位活動(例如查詢、交叉點等)，在相同工作流程中定義為上游。

根據工作流程執行參數觸發訊息準備。在訊息控制面板中，您可以選擇要請求還是不要手動確認傳送訊息(預設為必要)。您可以手動開始工作流程，或在工作流程中放置排程器活動，以自動化執行。

## Configuration {#configuration}

1. Drag and drop an **[!UICONTROL SMS delivery]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.

   >[!NOTE]
   >
   >You can access the general properties and advanced options of the activity (and not of the delivery itself) via the ![](assets/dlv_activity_params-24px.png) button in the workflow's action bar. This button is specific to the **[!UICONTROL SMS delivery]** activity. SMS屬性可透過SMS儀表板中的動作列存取。

1. 選取SMS傳送模式：

   * **[!UICONTROL SMS]**：SMS會一次傳送。您可以在此處指定是否要為活動新增對外轉場。此程序步驟中會詳述不同的轉場類型。
   * **[!UICONTROL Recurring SMS]**：SMS會根據 **[!UICONTROL Scheduler]** 活動中定義的頻率數次傳送。選取傳送的匯總期間。This allows you to regroup all the sends that occur during the defined period into one single view that is also called **Recurring execution** and can be accessed from the application's marketing activity list.

      例如，若是每日傳送的生日SMS，您可以選擇匯總每個月傳送的傳送次數。這可讓您每月收到報告，但每日傳送SMS。

1. 選取SMS類型。The SMS types come from SMS templates defined in the **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** &gt; **[!UICONTROL Delivery templates]** menu.
1. 輸入SMS的一般屬性。您也可以將其附加至現有促銷活動。工作流程的傳送活動標籤會使用SMS標籤更新。
1. 定義SMS內容。Refer to the section concerning [Creating an SMS message](../../channels/using/creating-an-sms-message.md).
1. By default, the **[!UICONTROL SMS delivery]** activity does not include any outbound transitions. If you would like to add an outbound transition to your **[!UICONTROL SMS delivery]** activity, go to the **[!UICONTROL General]** tab of the advanced activity options ( ![](assets/dlv_activity_params-24px.png) button in the activity's quick actions) then check one of the following options:

   * **[!UICONTROL Add outbound transition without the population]**：這可讓您產生對外轉場，其中包含與傳入轉換完全相同的人口族群。
   * **[!UICONTROL Add outbound transition with the population]**：這可讓您產生內含SMS的對外轉場轉換。傳送準備期間排除的目標成員(隔離、無效數字等)被排除在外。

1. 確認活動的設定並儲存工作流程。

當您重新開啓活動時，會直接進入SMS儀表板。只能編輯其內容。

根據預設，啓動傳送工作流程只會觸發訊息準備。在工作流程啓動後，仍需要確認從工作流程建立的訊息。But from the message dashboard, and only if the message was created from a workflow, you can disable the **[!UICONTROL Request confirmation before sending messages]** option. 取消勾選此選項後，就會在準備完成後，不會進一步通知訊息。

## Remarks {#remarks}

在工作流程中建立的傳送可在應用程式的行銷活動清單中存取。您可以使用控制面板來檢視工作流程的執行狀態。SMS摘要窗格中的連結可讓您直接存取連結的元素(工作流程、促銷活動、父項傳送，以發生循環SMS)。

不過，預設會遮罩週期性傳送的執行。To view them, check the **[!UICONTROL Show recurring executions]** option in the marketing activities' search panel.

In the parent deliveries, which can be accessed from the marketing activity list or directly via the associated recurring executions, you can view the total number of sends that have been processed (according to the aggregation period specified when the **[!UICONTROL SMS delivery]** activity was configured). To do this, open the detail view of the parent delivery's **[!UICONTROL Deployment]** block by selecting ![](assets/wkf_dlv_detail_button.png).

## Example {#example}

![](assets/wkf_sms_example_1.png)

此範例為生日工作流程。每天將SMS傳送給當天生日的個人檔案。若要這麼做：

* The **[!UICONTROL Scheduler]** allows you to start the workflow every day at 8am.

   ![](assets/wkf_delivery_example_2.png)

* **[!UICONTROL Query]** 此活動可讓您計算提供行動電話號碼和生日當天(每次執行工作流程)的個人檔案。您可以使用查詢編輯工具中浮動視窗中可用的預先定義篩選來進行生日計算。

   ![](assets/wkf_delivery_example_3.png)

* **[!UICONTROL SMS]** 週期性。傳送會依月份匯總。因此，在一個月內傳送的所有SMS訊息都會匯總至單一檢視中。In one year, 365 deliveries are therefore executed but they are regrouped into 12 views (also called **recurring executions**) in the Adobe Campaign interface. 歷史和報告細節會每個月顯示，而不是每次傳送。

   ![](assets/wkf_sms_example_4.png)

