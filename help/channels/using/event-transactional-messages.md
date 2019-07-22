---
title: 事件交易訊息
seo-title: 事件交易訊息
description: 事件交易訊息
seo-description: 瞭解如何建立和發佈事件交易訊息。
page-status-flag: 從未啓動
uuid: d747feb5-58fb-4e12-a176-404f0 a5391
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 頻道
content-type: reference
topic-tags: 交易訊息
discoiquuid: 4f6317a1-9dfe-4714-bc1 c-393629d855 cd
context-tags: Delivery TransactionalTemplate，overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e08b7e01956a9106937cb72ab790cb2e98999fcd

---


# Event transactional messages{#event-transactional-messages}

您可以傳送定位事件的事件交易訊息。這類交易訊息不包含描述檔資訊：傳送目標是由事件本身包含的資料所定義。

Once you have created and published an event (the cart abandonment as explained in [this section](../../channels/using/about-transactional-messaging.md#transactional-messaging-operating-principle)), the corresponding transactional message is created automatically.

The configuration steps are presented in the [Configuring an event to send an transactional message](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message) section.

為了讓事件觸發傳送交易訊息，您必須個人化訊息，然後加以測試並加以發佈。

>[!NOTE]
>
>To access the transactional messages, you must have administration rights or appear in the **[!UICONTROL Message Center agents]** (mcExec) security group. 事件交易訊息不包含描述檔資訊，因此它們與疲勞規則不相容(即使在使用描述檔進行擴充時)。See [Fatigue rules](../../administration/using/fatigue-rules.md#choosing-the-channel).

## Defining a test profile in a transactional message {#defining-a-test-profile-in-a-transactional-message}

定義已調整的測試設定檔，讓您預覽訊息並傳送校樣以檢查訊息。

### Creating a test profile within the transactional message {#creating-a-test-profile-within-the-transactional-----------message}

1. To access the message that you created, click the **[!UICONTROL Adobe Campaign]** logo, in the top left corner, then select **[!UICONTROL Marketing plans]** &gt; **[!UICONTROL Transactional messages]** &gt; **[!UICONTROL Transactional messages]**.

   ![](assets/message-center_4.png)

1. 建立要連結至事件的測試設定檔。

   ![](assets/message-center_test-profile.png)

1. Specify the information to send in JSON format in the **[!UICONTROL Event data used for personalization]** section. 此為預覽訊息時，以及測試設定檔接收校樣時所使用的內容。

   ![](assets/message-center_event-data.png)

   >[!NOTE]
   >
   >您也可以輸入與描述檔表格相關的資訊。See [Enriching the transactional message content](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content).

1. 在建立後，會在交易訊息中預先指定測試設定檔。Click the **[!UICONTROL Test profiles]** block of the message to check the target of your proof.

   ![](assets/message-center_5.png)

### Creating a test profile outside the transactional message {#creating-a-test-profile-outside-the-transactional-----------message}

You can also create a new test profile or use one that already exists in the **[!UICONTROL Test profiles]** menu.

1. Click the **[!UICONTROL Adobe Campaign]** logo, in the top left corner, then select **[!UICONTROL Profiles & audiences]** &gt; **[!UICONTROL Test profiles]**.
1. In the **[!UICONTROL Event]** section of the page of the test profile that you have chosen, select the event that you have just created. 在此範例中，選取「購物車放棄(evtCartabandonUnment)」。
1. Specify the information to send in JSON format in the **[!UICONTROL Event data]** text box.

   ![](assets/message-center_3.png)

1. 儲存變更。

您現在可以存取您建立的訊息，並選取更新的測試設定檔。

**相關主題：**

* [管理測試設定檔](../../sending/using/managing-test-profiles-and-sending-proofs.md)
* [定義受眾](../../audiences/using/creating-audiences.md)

## Personalizing a transactional message {#personalizing-a-transactional-message}

若要在交易訊息中設定個人化，請遵循下列步驟：

1. Click the **[!UICONTROL Content]** block to modify your message's subject and content. 在此範例中，匯入包含影像、樣式表和HTML檔案的HTML範本。Importing HTML templates is presented in the [Loading an existing content](../../designing/using/selecting-an-existing-content.md) section.

   ![](assets/message-center_6.png)

1. 輸入您的訊息內容。在此範例中，我們新增了個個人化欄位：姓氏，上次產品諮詢，總購物車金額。放棄購物車的連結是外部URL的連結，可將人員重新導向至其購物車。此參數不會在Adobe Campaign中管理。

   To add fields that you defined when you created your event (see [Configuring an event](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message)), insert a personalization field in the message content. You can find the fields by selecting **[!UICONTROL Transactional event]** &gt; **[!UICONTROL Event context]**.

   ![](assets/message-center_7.png)

1. 若要豐富訊息內容，請從您連結事件的表格中選擇欄位。In our example, select the **[!UICONTROL Title (salutation)]** field in the **[!UICONTROL Profile]** table.

   ![](assets/message-center_7-enrichment.png)

   The steps for inserting a personalization field are detailed in the [Inserting a personalization field](../../designing/using/inserting-a-personalization-field.md) section.

   ![](assets/message-center_8.png)

1. 選取您為此事件定義的設定檔，以預覽您的訊息。

   The steps for previewing a message are detailed in the [Previewing messages](../../sending/using/preparing-the-send.md) section.

   ![](assets/message-center_9.png)

   您可以檢查個人化欄位是否符合測試描述檔中輸入的資訊。For more on this, see [Defining a test profile in a transactional message](../../channels/using/event-transactional-messages.md#defining-a-test-profile-in-a-transactional-message).

## Using product listings in a transactional message {#using-product-listings-in-a-transactional-message}

您可以建立產品清單，參照交易式電子郵件內容中的一或多個資料集合。例如，在購物車放棄電子郵件中，您可以包含使用者離開您的網站時的所有產品清單，其中包含影像、價格和每項產品的連結。

>[!CAUTION]
>
>Product listings are only available when editing transactional email messages through the [Email Designer](../../designing/using/about-email-content-design.md#about-the-email-designer) interface.

若要在交易訊息中新增放棄產品清單，請遵循以下步驟。

您也可以觀看一組影片，說明在交易式電子郵件中設定產品清單所需的步驟。For more on this, see [this page](https://helpx.adobe.com/campaign/kt/acs/using/acs-product-listings-in-transactional-emails-feature-video-setup.html).

>[!NOTE]
>
>Adobe Campaign不支援巢狀產品清單，這表示您無法在另一個清單中包含產品清單。

### Defining a product listing {#defining-a-product-listing}

在交易訊息中使用產品清單之前，您必須在事件層級定義產品清單，以及您要顯示之清單的每個產品的欄位。For more on this, see [Defining data collections](../../administration/using/configuring-transactional-messaging.md#defining-data-collections).

1. In the transactional message, click the **[!UICONTROL Content]** block to modify the email content.
1. 拖放結構元件至工作區。For more on this, see [Editing the email structure](../../designing/using/defining-the-email-structure.md#editing-the-email-structure).

   例如，選取單欄結構元件並新增文字元件、影像元件和按鈕元件。For more on this, see [Adding fragments and components](../../designing/using/defining-the-email-structure.md#adding-fragments-and-content-components).

1. Select the structure component you just created and click the **[!UICONTROL Enable product listing]** icon from the contextual toolbar.

   ![](assets/message-center_loop_create.png)

   The structure component is highlighted with an orange frame and the **[!UICONTROL Product listing]** settings are displayed in the left palette.

   ![](assets/message-center_loop_palette.png)

1. 選取系列元素的顯示方式：

   * **[!UICONTROL Row]**：水平表示另一列的每個元素。
   * **[!UICONTROL Column]**：垂直代表同一列上另一個元素的旁邊。
   >[!NOTE]
   >
   >**[!UICONTROL Column]** 此選項僅適用於使用多欄結構元件( **[!UICONTROL 2:2 column]**&#x200B;和 **[!UICONTROL 3:3 column]****[!UICONTROL 4:4 column]** )。編輯產品清單時，只會填寫第一欄：其他欄將不會納入考量。For more on selecting structure components, see [Editing the email structure](../../designing/using/defining-the-email-structure.md#editing-the-email-structure).

1. 選取設定與交易訊息相關之事件時所建立的資料收集。You can find it under the **[!UICONTROL Context]** &gt; **[!UICONTROL Real-time event]** &gt; **[!UICONTROL Event context]** node.

   ![](assets/message-center_loop_selection.png)

   For more on configuring the event, see [Defining data collections](../../administration/using/configuring-transactional-messaging.md#defining-data-collections).

1. Use the **[!UICONTROL First item]** drop-down list to select which element will start the list displayed in the email.

   例如，如果您選取了2，系列的第一個項目將不會顯示在電子郵件中。產品清單將從第二個項目開始。

1. 選取清單中要顯示的項目數目上限。

   >[!NOTE]
   >
   >If you want the elements of your list to be displayed vertically ( **[!UICONTROL Column]** ), the maximum number of items is limited according to the selected structure component (2, 3 or 4 columns). For more on selecting structure components, see [Editing the email structure](../../designing/using/defining-the-email-structure.md#editing-the-email-structure).

### Populating the product listing {#populating-the-product-listing}

若要顯示連結至交易電子郵件之事件的產品清單，請遵循以下步驟。

For more on creating a collection and related fields when configuring the event, see [Defining data collections](../../administration/using/configuring-transactional-messaging.md#defining-data-collections).

1. Select the image component you inserted, select **[!UICONTROL Enable personalization]** and click the pencil in the Settings pane.

   ![](assets/message-center_loop_image.png)

1. Select **[!UICONTROL Add personalization field]** in the **[!UICONTROL Image source URL]** window that opens.

   From the **[!UICONTROL Context]** &gt; **[!UICONTROL Real-time event]** &gt; **[!UICONTROL Event context]** node, open the node corresponding to the collection that you created (here **[!UICONTROL Product list]** ) and select the image field that you defined (here **[!UICONTROL Product image]** ). Click **[!UICONTROL Save]**.

   ![](assets/message-center_loop_product-image.png)

   您選取的個人化欄位現在會顯示在「設定」窗格中。

1. At the desired position, select **[!UICONTROL Insert personalization field]** from the contextual toolbar.

   ![](assets/message-center_loop_product.png)

1. From the **[!UICONTROL Context]** &gt; **[!UICONTROL Real-time event]** &gt; **[!UICONTROL Event context]** node, open the node corresponding to the collection that you created (here **[!UICONTROL Product list]** ) and select the field that you created (here **[!UICONTROL Product name]** ). Click **[!UICONTROL Confirm]**.

   ![](assets/message-center_loop_product_node.png)

   您選取的個人化欄位現在會顯示在電子郵件內容中所要的位置。

1. 按類似方式繼續進行。
1. Select some text and select **[!UICONTROL Insert link]** from the contextual toolbar.

   ![](assets/message-center_loop_link_insert.png)

1. Select **[!UICONTROL Add personalization field]** in the **[!UICONTROL Insert link]** window that opens.

   From the **[!UICONTROL Context]** &gt; **[!UICONTROL Real-time event]** &gt; **[!UICONTROL Event context]** node, open the node corresponding to the collection that you created (here **[!UICONTROL Product list]** ) and select the URL field that you created (here **[!UICONTROL Product URL]** ). Click **[!UICONTROL Save]**.

   >[!CAUTION]
   >
   >基於安全理由，請確定您在開頭為適當靜態網域名稱的連結中插入個人化欄位。

   ![](assets/message-center_loop_link_select.png)

   您選取的個人化欄位現在會顯示在「設定」窗格中。

1. Select the structure component on which the product listing is applied and select **[!UICONTROL Show fallback]** to define a default content.

   ![](assets/message-center_loop_fallback_show.png)

1. 拖曳一或多個內容元件並視需要加以編輯。

   ![](assets/message-center_loop_fallback.png)

   如果事件觸發時會顯示空白，則會顯示備援內容，例如客戶在購物車中無任何項目時。

1. 從「設定」窗格中，編輯產品清單的樣式。For more on this, see [Editing email styles](../../designing/using/editing-email-styles.md).
1. 使用連結至相關交易事件以及您定義收集資料的測試設定檔預覽電子郵件。For example, add the following information in the **[!UICONTROL Event data]** section for the test profile you want to use:

   ![](assets/message-center_loop_test-profile_payload.png)

   For more on defining a test profile in a transactional message, see [this section](../../channels/using/event-transactional-messages.md#defining-a-test-profile-in-a-transactional-message).

## Testing a transactional message {#testing-a-transactional-message}

儲存交易訊息後，您現在可以傳送校樣來進行測試。

![](assets/message-center_10.png)

The steps for sending a proof are detailed in the [Sending a proof](../../sending/using/managing-test-profiles-and-sending-proofs.md#sending-proofs) section.

## Publishing a transactional message {#publishing-a-transactional-message}

勾選交易訊息後，您可以加以發佈。

![](assets/message-center_12.png)

現在，當觸發「購物車放棄」事件時，會自動提示包含收件者標題和姓氏、購物車URL、上次產品諮詢或產品清單(如果您定義產品清單)的訊息，以及要傳送的總購物車金額。

To access reports concerning your transactional message, use the **[!UICONTROL Reports]** button. See [Reports](../../reporting/using/about-dynamic-reports.md).

![](assets/message-center_13.png)

## Suspending a transactional message publication {#suspending-a-transactional-message-publication}

You can suspend publishing your transactional message by using the **[!UICONTROL Pause]** button, for example, to modify the data contained in the message. 因此，事件不會再處理，而會保留在Adobe Campaign資料庫中的佇列中。

The queued events are kept during a period of time that is defined in the REST API (see [REST API documentation](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html)) or in the trigger event if you are using the Triggers core service (see [Working with Campaign and Experience Cloud Triggers](../../integrating/using/about-adobe-experience-cloud-triggers.md)).

![](assets/message-center_pause.png)

When clicking **[!UICONTROL Resume]**, all of the queued events (provided that they are not expired) are processed. 現在，它們包含範本出版物暫停時進行的所有修改。

## Unpublishing a transactional message {#unpublishing-a-transactional-message}

Clicking **[!UICONTROL Unpublish]** allows you to cancel the transactional message publication, but also the publication of the corresponding event, which deletes from the REST API the resource corresponding to the event that you previously created. 現在，即使是透過您的網站觸發事件，對應的訊息也不會再傳送，也不會儲存在資料庫中。

![](assets/message-center_unpublish-template.png)

>[!NOTE]
>
>若要再次發佈訊息，您需要返回對應的事件設定、發佈並發佈訊息。For more on this, see [Publishing a transactional message](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message).

如果您取消發佈已暫停的交易訊息，可能需要等候24小時才能再次發佈。This is to let the **[!UICONTROL Database cleanup]** workflow clean all the events that were sent to the queue. The steps for pausing a message are detailed in the [Suspending a transactional message publication](../../channels/using/event-transactional-messages.md#suspending-a-transactional-message-publication) section.

**[!UICONTROL Database cleanup]** 工作流程每天早上執行，可透過 **[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt;存取 **[!UICONTROL Workflows]**。

## Deleting a transactional message {#deleting-a-transactional-message}

![](assets/message-center_delete-template.png)

By selecting a transactional message, you can delete it with the **[!UICONTROL Delete element]** button even if it has already been published. 不過，刪除交易訊息只能在某些情況下完成：

* **交易訊息**：若要刪除交易訊息，訊息應該解除發佈且不會暫停。

   如果交易訊息未發佈，則必須解除發佈事件設定，才能成功刪除您的交易訊息，除非其他交易訊息連結至對應的事件。For more information on how to unpublish a transactional message, refer to this [section](../../channels/using/event-transactional-messages.md#unpublishing-a-transactional-message).

   >[!CAUTION]
   >
   >刪除已傳送通知的交易訊息也會刪除其傳送和追蹤記錄檔。

* **來自現成可用事件範本的交易訊息(內部交易訊息)**：若要刪除內部交易訊息，訊息應該解除發佈且不會暫停。

   它也不是事件中唯一的交易訊息，而必須連結至對應的事件。

## Transactional message retry process {#transactional-message-retry-process}

暫時未傳送的交易訊息會受到自動重試，直到傳送過期為止。For more on the delivery duration, see [Validity period parameters](../../administration/using/configuring-email-channel.md#validity-period-parameters).

如果無法傳送交易訊息，則有兩個重試系統：

* 在交易傳訊層級，交易訊息可能會在指派事件給執行傳送、事件接收和傳送準備之間失敗。See [Event processing retry process](../../channels/using/event-transactional-messages.md#event-processing-retry-process).
* 在傳送程序層級，當事件指派給執行傳送時，交易訊息會因暫時錯誤而失敗。See [Message sending retry process](../../channels/using/event-transactional-messages.md#message-sending-retry-process).

### Event processing retry process {#event-processing-retry-process}

如果無法指派事件給執行傳送，則會延遲事件處理。然後執行重試，直到指派給新執行傳送為止。

>[!NOTE]
>
>延遲事件不會出現在交易訊息中，因為它尚未指派給執行傳送。

例如，由於其內容不正確，所以無法指派事件給執行傳送，因此會發生存取權限或品牌的問題，在套用字型規則時偵測到錯誤等。在這種情況下，您可以暫停訊息，加以編輯以修正問題並再次發佈。然後重試系統會將其指派給新執行的傳送。

### Message sending retry process {#message-sending-retry-process}

一旦將事件指派給執行傳送，則如果收件者的郵箱已滿，交易訊息可能會因暫時錯誤而失敗。For more on this, see [Retries after a delivery temporary failure](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure).

>[!NOTE]
>
>當事件指派給執行傳送時，它會出現在此執行傳送的傳送記錄中，而且只會出現在此時。The failed deliveries are displayed in the **[!UICONTROL Execution list]** tab of the transactional message.

### Limitations {#limitations}

**傳送記錄檔更新**

在重試程序中，不會立即更新新執行傳送的傳送記錄(更新會透過排程工作流程執行)。It means that the message could be in **[!UICONTROL Pending]** status even if the transactional event has been processed by the new execution delivery.

**執行失敗**

您無法停止執行傳送。不過，如果目前的執行傳送失敗，則會在收到新事件時立即建立新的事件，而且新的事件會由新的執行傳送處理。未通過失敗執行傳送，就不會處理新事件。

如果某些已指派給執行傳送的事件已經延遲，而且如果執行傳送失敗，則重試系統不會將延遲的事件指派給新的執行傳送，這表示這些事件已遺失。
