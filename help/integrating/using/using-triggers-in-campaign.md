---
title: 在促銷活動中使用觸發器
seo-title: 在促銷活動中使用觸發器
description: 在促銷活動中使用觸發器
seo-description: null
page-status-flag: 從未啓動
uuid: d844d013-b38 a-4e69-9df5-0edc01 fa6 e6 e
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 整合
content-type: reference
topic-tags: 使用促銷活動與觸發器
discoiquuid: a524c700-bug6-4fcf-857a-c31 bfae4 d30 c
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 698466596fdacd005dc4d72b8071208c8c39f77d

---


# Using Triggers in Campaign{#using-triggers-in-campaign}

## Creating a mapped trigger in Campaign {#creating-a-mapped-trigger-in-campaign}

You should make sure to define the behaviors that you want to monitor beforehand in Adobe Experience Cloud ( **[!UICONTROL Triggers]** core service). For more on this, refer to the [Adobe Experience Cloud documentation](https://marketing.adobe.com/resources/help/en_US/mcloud/triggers.html). 請注意，當您定義觸發器時，必須啓用別名。對於每個行為(瀏覽/表單放棄、新增/刪除產品、作業過期等)，Adobe Experience Cloud中必須新增新觸發器。

您現在必須根據現有Adobe Experience Cloud觸發器，在Adobe Campaign中建立觸發事件。

You can watch this [video](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html#step-two) to help you understand how triggers are set up in Adobe Campaign.

將此項目放入位置的步驟包括：

1. Click the **[!UICONTROL Adobe Campaign]** logo, in the top left corner, then select **[!UICONTROL Marketing plans]** &gt; **[!UICONTROL Transactional messages]** &gt; **[!UICONTROL Experience Cloud Triggers]**.

   ![](assets/remarketing_1.png)

1. Click the **[!UICONTROL Create]** button. 開啓的建立精靈會顯示Adobe Experience Cloud中定義的所有觸發器清單。**[!UICONTROL Fired by Analytics]** 欄會顯示Adobe Experience Cloud觸發器傳送給Campaign的事件數。這是在Experience Cloud介面中建立的觸發器映射。

   ![](assets/remarketing_2.png)

1. Select the Adobe Experience Cloud trigger that you want to use and click **[!UICONTROL Next]**.
1. 設定觸發器的一般屬性。At this step of the wizard, also specify the channel and the targeting dimension to use for the trigger (see [targeting dimensions and resources](../../automating/using/query.md#targeting-dimensions-and-resources)). 然後確認觸發器建立。
1. Click the button to the right of the **[!UICONTROL Event content and enrichment]** field to view the content of the payload. 此畫面也可讓您使用儲存在Adobe Campaign資料庫中的描述檔資料豐富事件資料。此增強功能的執行方式與標準交易訊息相同。

   ![](assets/remarketing_3.png)

1. **[!UICONTROL Transactional message validity duration]** 在欄位中，定義Analytics傳送事件後，訊息有效的持續時間。如果定義的持續時間為天，則該訊息將不會再於持續時間後傳送。如果您放置了幾個訊息，如此當您在一段時間後繼續進行這些訊息時，就無法傳送這些訊息。

   ![](assets/remarketing_4.png)

1. If a propensity scoring is defined in Analytics (see the [Experience Cloud documentation](https://marketing.adobe.com/resources/help/en_US/insight/client/c_visitor_propensity.html)), you can choose not to send the message if the customer has a high probability of coming back to the website in the near future. 分數的內容和臨界值可用於裝載內容中，讓您可以使用這些值個人化訊息。若要使用此選項，請勾選畫面底部的方塊。客戶極有可能在近期內返回網站，將不會收到訊息。
1. Click the **[!UICONTROL Publish]** button to start publishing the trigger event.
1. If you need to make a change in your trigger schema even after publishing your trigger event, click the **[!UICONTROL Update schema]** button to retrieve the latest changes.

   請注意，此動作會解除發佈您的觸發器和交易訊息，之後您必須重新發佈。

   ![](assets/remarketing_11.png)

**[!UICONTROL Show Trigger in Experience Cloud]** 此按鈕可讓您檢視Adobe Experience Cloud中的觸發器定義。

在發佈事件後，會自動建立連結至新事件的交易範本。然後您必須修改並發佈剛才建立的範本。For more on this, refer to the [Editing the template](../../start/using/about-templates.md) section.

## Editing the transactional message template {#editing-the-transactional-message-template}

建立並發佈觸發事件後，會自動建立對應的交易範本。For more on this, refer to the [Creating a mapped trigger in Campaign](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) section.

為了讓事件觸發傳送交易訊息，您必須個人化範本，然後加以測試並加以發佈。這些步驟與標準交易訊息相同。For more on this, refer to the [Transactional template](../../channels/using/event-transactional-messages.md#personalizing-a-transactional-message) section.

>[!NOTE]
>
>如果您取消發佈範本，它會自動解除發佈觸發事件。

編輯內容時，您可以根據Analytics觸發器所傳送的資訊，新增個人化欄位。如果您使用Adobe Campaign描述檔資料豐富事件資料，您可以根據此資訊個人化訊息。To personalize your message, select **[!UICONTROL Transactional event]** &gt; **[!UICONTROL Event context]** and select a field.

![](assets/remarketing_8.png)

## Accessing the reports {#accessing-the-reports}

To view the dedicated trigger report in Adobe Campaign, open the trigger event that you previously created, and click **[!UICONTROL Show trigger report]**.

![](assets/remarketing_9.png)

報表會顯示與Analytics所傳送事件數目相比的處理事件數目。它也會顯示所有最近觸發的項目。

![](assets/trigger_uc_browse_14.png)

