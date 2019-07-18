---
title: 推播通知傳送
seo-title: 推播通知傳送
description: 推播通知傳送
seo-description: 推播通知傳送活動可讓您設定在工作流程中傳送單一傳送推播通知或循環推播通知。
page-status-flag: 從未啓動
uuid: 994d8Fe3-29f0-4b5c-89ee-c6 be7 c60 a31 b
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: reference
topic-tags: channel-activity
discoiquuid: e61bdaee-4b48-4845-a2 a5-574b577 ea796
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 36727e82d3aa73add6116fa2916752ff0e407d9d

---


# Push notification delivery{#push-notification-delivery}

## Description {#description}

![](assets/push.png)

![](assets/recurrentpush.png)

**[!UICONTROL Push notification]** 此活動可讓您設定在工作流程中傳送推播通知。This can be a **single send** notification and sent just once, or it can be a **recurring** notification.

單一傳送通知是標準行動應用程式推播通知傳送，只傳送一次。

循環通知可讓您在定義的時段內，將相同的行動應用程式推播通知傳送至多次傳送至不同的目標。您可以匯總每個時段的傳送，取得符合您需求的報表。

## Context of use {#context-of-use}

**[!UICONTROL Push notification]** 此活動通常用於將通知傳送至相同工作流程中計算的目標。

當連結至排程器時，您可以定義循環推播通知。

收件者可透過定位活動(例如查詢、交叉點等)，在相同工作流程中定義為上游。

根據工作流程執行參數觸發訊息準備。在訊息控制面板中，您可以選擇要請求還是不要手動確認傳送訊息(預設為必要)。您可以手動開始工作流程，或在工作流程中放置排程器活動，以自動化執行。

## Configuration {#configuration}

1. Drag and drop a **[!UICONTROL Push notification]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.

   >[!NOTE]
   >
   >You can access the general properties and advanced options of the activity (and not of the delivery itself) via the ![](assets/dlv_activity_params-24px.png) button from the activity's quick actions. This button is specific to the **[!UICONTROL Push notification]** activity. 推播通知的屬性可透過推播控制面板中的動作列存取。

1. 選取推播通知傳送模式：

   * **[!UICONTROL Single notification]**：推播通知會一次傳送。您可以在此處指定是否要為活動新增對外轉場。此程序步驟中會詳述不同的轉場類型。
   * **[!UICONTROL Recurring notification]**：推播通知會根據 **[!UICONTROL Scheduler]** 活動中定義的頻率數次傳送。選取傳送的匯總期間。This allows you to regroup all the sends that occur during the defined period in one single push notification that is also called **recurring execution** and can be accessed from the application's marketing activity list.

      例如，若是每日傳送的生日通知，您可以選擇匯總每個月傳送的傳送次數。這可讓您每月收到報告，但每日傳送通知。

1. 選取通知類型。These types come from push notifications templates defined in the **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** &gt; **[!UICONTROL Delivery templates]** menu.
1. 輸入推播通知的一般屬性。您也可以將其附加至現有促銷活動。工作流程的傳送活動標籤會以推播通知標籤更新。
1. 定義推播通知內容。See [Creating a push notification](../../channels/using/preparing-and-sending-a-push-notification.md)
1. By default, the **[!UICONTROL Push notification]** activity does not include any outbound transitions. If you would like to add an outbound transition to your **[!UICONTROL Push Notification]** activity, go to the **[!UICONTROL General]** tab of the advanced activity options ( ![](assets/dlv_activity_params-24px.png) button in the activity's quick actions) then check one of the following options:

   * **[!UICONTROL Add outbound transition without the population]**：這可讓您產生對外轉場，其中包含與傳入轉換完全相同的人口族群。
   * **[!UICONTROL Add outbound transition with the population]**：這可讓您產生對外轉場，包含傳送通知的人口族群。傳送準備期間排除之目標的成員會從此轉變中排除。

1. 確認活動的設定並儲存工作流程。

當您重新開啓活動時，會直接進入推播通知控制面板。只能編輯其內容。

根據預設，啓動傳送工作流程只會觸發訊息準備。在工作流程啓動後，仍需要確認從工作流程建立的訊息。But from the message dashboard, and only if the message was created from a workflow, you can disable the **[!UICONTROL Request confirmation before sending messages]** option. 取消勾選此選項後，就會在準備完成後，不會進一步通知訊息。

## Remarks {#remarks}

在工作流程中建立的傳送可在應用程式的行銷活動清單中存取。您可以使用控制面板來檢視工作流程的執行狀態。推播通知摘要窗格中的連結可讓您直接存取連結的元素(工作流程、促銷活動等)。

In the parent deliveries, which can be accessed from the marketing activity list, you can view the total number of sends that have been processed (according to the aggregation period specified when the **[!UICONTROL Push notification]** activity was configured). To do this, open the detail view of the parent delivery's **[!UICONTROL Deployment]** block by selecting ![](assets/wkf_dlv_detail_button.png).

## Sending a recurring push notification with a workflow {#sending-a-recurring-push-notification-with-a-workflow}

![](assets/wkf_push_example_1.png)

在此範例中，個人化推播通知會在每月的每一天傳送至行動應用程式的訂閱者，視其時區而定。若要這麼做：

1. **[!UICONTROL Scheduler]** 活動可讓您開始傳送開始前的工作流程天數，以便在任何指定時區傳送通知給每個訂閱者8pm：

   * In the **[!UICONTROL Execution frequency]** field, select Monthly.
   * Select 8 pm in the **[!UICONTROL Time]** field.
   * 選擇每個月傳送的日期。
   * 選取工作流程的開始日期，在傳送開始前至少一天。否則，有些收件者可能會在所選時間已在其時區傳入時收到訊息。
   * **[!UICONTROL Execution options]** 在標籤中，選取工作流程在 **[!UICONTROL Time zone]** 欄位中開始的時間。例如，在這裡，工作流程將於太平洋時間下午點開始，在這個月的第一天前一周，為所有適用時區建立傳送。
   ![](assets/wkf_push_example_5.png)

1. **「查詢** 」活動可讓您鎖定已訂閱您行動應用程式且未開啓您傳送電子郵件的使用者之間的舊版VIP客戶：

   * 選擇受眾(您的VIP客戶)並篩選他們的年齡。
   * Drag and drop the **Subscriptions to an application** element into the workspace. Select **Exists** and select the mobile application that you want to use.
   * 選擇傳送給客戶的電子郵件。
   * Drag and drop the **Delivery logs (logs)** element into the workspace and select **Exists** to target all of the customers who received the email.
   * Drag and drop the **Tracking logs (tracking)** element into the workspace and select **Does not exist** to target all of the customers who did not open the email.

      ![](assets/wkf_push_example_2.png)

1. **「推播通知** 」活動可讓您輸入訊息的內容，並選取您要使用的個人化欄位：

   * Select the **[!UICONTROL Recurring notification]** option.
   * 定義推播通知內容。For more information on push notification content, refer to this [section](../../channels/using/preparing-and-sending-a-push-notification.md).
   * In the **[!UICONTROL Schedule]** block, select **[!UICONTROL Messages to be sent automatically on the time zone specified below]**. Here, we chose the **[!UICONTROL Time zone of the contact date]** Pacific as in the workflow **[!UICONTROL Scheduler]**.
   * In the **[!UICONTROL Optimize the sending time per recipient]** field, select **[!UICONTROL Send at the recipient's time zone]**.

      ![](assets/wkf_push_example_4.png)

1. Click the **[!UICONTROL Start]** button to start your recurring workflow.

   ![](assets/wkf_push_example_3.png)

您的工作流程正在執行中。It will start at the chosen start date of the **[!UICONTROL Scheduler]** at 8 pm Pacific time, the recurring push will then be sent every first day of the month at 8 pm depending on the customers time zone.
