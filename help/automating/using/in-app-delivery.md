---
title: 應用程式內散髮
seo-title: 應用程式內散髮
description: 應用程式內散髮
seo-description: 應用程式內傳送活動可讓您設定在工作流程中傳送應用程式內訊息。
page-status-flag: 從未啓動
uuid: 528d9472-e447-47af-a6 b2-3181aa5 fb廣告
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: reference
topic-tags: channel-activity
discoiquuid: 19796aca-6e9e9e-4d3a-8917-ba660 ec7993 c
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 36727e82d3aa73add6116fa2916752ff0e407d9d

---


# In-App delivery{#in-app-delivery}

## Description {#description}

![](assets/wkf_in_app_1.png)

**應用程式內傳送** 活動可讓您設定在工作流程中傳送應用程式內訊息。應用程式內傳訊可讓您在應用程式內啓用使用者時顯示訊息。For more information concerning the In-App delivery, refer to this [section](../../channels/using/about-in-app-messaging.md).

## Context of use {#context-of-use}

**[!UICONTROL In-App delivery]** 此活動通常用於將應用程式內訊息自動傳送給同一工作流程中計算的目標對象。

收件者可透過定位活動(例如查詢、交叉點等)，在相同工作流程中定義為上游。

根據工作流程執行參數觸發訊息準備。在訊息控制面板中，您可以選擇要請求還是不要手動確認傳送訊息(預設為必要)。您可以手動開始工作流程，或在工作流程中放置排程器活動，以自動化執行。

## Configuration {#configuration}

1. Drag and drop a **[!UICONTROL Query]** activity to your workflow. Please note that the **[!UICONTROL Query]** activity targeting dimension in the **[!UICONTROL Properties]** tab needs to be updated according to the template chosen in Step 4:

   * Targeting dimension should be set to **[!UICONTROL mobileApp (mobileAppV5)]** for the **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]** template.
   * Targeting dimension should be set to **[!UICONTROL profile (profile)]** for the **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]** template.
   * Targeting dimension should be set to **[!UICONTROL subscriptions to an application (nms:appSubscriptionRcp:appSubscriptionRcpDetail)]** for the **[!UICONTROL Target users based on their Mobile profile (inApp)]** template.

1. Drag and drop a **[!UICONTROL In-App delivery]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.

   >[!NOTE]
   >
   >You can access the general properties and advanced options of the activity (and not of the delivery itself) via the ![](assets/dlv_activity_params-24px.png) button from the activity's quick actions.

   ![](assets/wkf_in_app_3.png)

1. 選取應用程式內訊息類型。This will depend on the data targeted in your **[!UICONTROL Query]** activity.

   * **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]**：此訊息類型可讓您定位已訂閱您行動應用程式的Adobe Campaign設定檔，並個人化促銷活動中可用描述檔屬性的應用程式內訊息。
   * **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]**：此訊息類型可讓您傳送訊息給行動應用程式的所有使用者，即使他們沒有促銷活動中的現有設定檔。
   * **[!UICONTROL Target users based on their Mobile profile (inApp)]**：此訊息類型可讓您定位行動應用程式中具有行動設定檔的所有使用者(不論已知或未知)，以及使用行動裝置取得的任何描述檔屬性個人化應用程式內訊息。
   ![](assets/wkf_in_app_4.png)

1. Enter your In-App message properties and select your mobile app in the **[!UICONTROL Associate a Mobile App to a delivery]** field.
1. **[!UICONTROL Triggers]** 在標籤中拖放將觸發訊息的事件。可使用三種事件類別：
1. 定義您的應用程式內內容。Refer to the section concerning [In-App customization](../../channels/using/customizing-an-in-app-message.md).
1. By default, the **[!UICONTROL In-App delivery]** activity does not include any outbound transitions. If you would like to add an outbound transition to your **[!UICONTROL In-App delivery]** activity, go to the **[!UICONTROL General]** tab of the advanced activity options ( ![](assets/dlv_activity_params-24px.png) button in the activity's quick actions) then check one of the following options:

   * **[!UICONTROL Add outbound transition without the population]**：這可讓您產生對外轉場，其中包含與傳入轉換完全相同的人口族群。
   * **[!UICONTROL Add outbound transition with the population]**：這可讓您產生包含訊息傳送之人口族群的對外轉場。傳送準備期間排除之目標的成員會從此轉變中排除。
   ![](assets/wkf_in_app_5.png)

1. 確認活動的設定並儲存工作流程。

當您重新開啓活動時，會直接進入應用程式中控制面板。只能編輯其內容。

根據預設，啓動傳送工作流程只會觸發訊息準備。在工作流程啓動後，仍需要確認從工作流程建立的訊息。But from the message dashboard, and only if the message was created from a workflow, you can disable the **[!UICONTROL Request confirmation before sending messages]** option. 取消勾選此選項後，就會在準備完成後，不會進一步通知訊息。

## Remarks {#remarks}

在工作流程中建立的傳送可在應用程式的行銷活動清單中存取。您可以使用控制面板來檢視工作流程的執行狀態。推播通知摘要窗格中的連結可讓您直接存取連結的元素(工作流程、促銷活動等)。

In the parent deliveries, which can be accessed from the marketing activity list, you can view the total number of sends that have been processed (according to the aggregation period specified when the **[!UICONTROL In-App delivery]** activity was configured). To do this, open the detail view of the parent delivery's **[!UICONTROL Deployment]** block by selecting ![](assets/wkf_dlv_detail_button.png).
