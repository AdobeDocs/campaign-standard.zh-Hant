---
title: 編輯異動訊息
description: 瞭解如何訪問、編輯和個性化事務性消息。
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
feature: Transactional Messaging
role: User
level: Intermediate
exl-id: f5dcb715-7cbd-49f2-8713-7e16cfa04184
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '653'
ht-degree: 30%

---

# 編輯異動訊息 {#editing-transactional-message}

建立並發佈事件後<!--(the cart abandonment example as explained in [this section](../../channels/using/getting-started-with-transactional-msg.md#transactional-messaging-operating-principle))-->，自動建立相應的事務消息。

配置和發佈事件的步驟在 [配置事務事件](../../channels/using/configuring-transactional-event.md) 和 [發佈事務性事件](../../channels/using/publishing-transactional-event.md) 的子菜單。

下面介紹了訪問、編輯和個性化此消息的步驟。

>[!IMPORTANT]
>
>僅具有 [管理](../../administration/using/users-management.md#functional-administrators) 角色可以訪問和編輯事務性消息。

一旦您的郵件準備就緒，便可對其進行測試並發佈。 請參閱 [測試事務性消息](../../channels/using/testing-transactional-message.md) 和 [事務性消息生命週期](../../channels/using/publishing-transactional-message.md)。

## 訪問事務性消息 {#accessing-transactional-messages}

要訪問您建立的事務性消息，請執行以下操作：

1. 按一下 **Adobe** 徽標，位於左上角。
1. 選擇 **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Transactional messages]**。

   ![](assets/message-center_4.png)

1. 按一下您選擇的消息編輯它。

   ![](assets/message-center_message-board.png)

您還可以通過位於相應事件配置螢幕左側區域的連結直接訪問事務性消息。 請參閱 [預覽和發佈事件](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event)

## 個人化交易式訊息 {#personalizing-a-transactional-message}

要編輯並個性化事務性消息，請執行以下步驟。

>[!NOTE]
>
>本節介紹如何編輯 **基於事件** 事務性消息。 的 **基於輪廓** 事務性消息特性是詳細的 [下](#profile-transactional-message-specificities)。
>
>中介紹了建立基於事件的事務性消息的配置步驟 [此部分](../../channels/using/configuring-transactional-event.md#event-based-transactional-messages)。

例如，您希望向已將產品添加到購物車的網站用戶發送通知，然後離開網站，而不需要進行購買。 此示例在 [事務性消息傳遞操作原則](../../channels/using/getting-started-with-transactional-msg.md#transactional-messaging-operating-principle) 的子菜單。

1. 按一下 **[!UICONTROL Content]** 區塊以修改訊息的主旨與內容。在此範例中，選取包含影像與文字的任何範本。有關電子郵件內容模板的詳細資訊，請參見 [使用模板設計電子郵件](../../designing/using/using-reusable-content.md#designing-templates)。

   ![](assets/message-center_6.png)

1. 新增主旨並編輯訊息內容以符合您的需求。

   >[!NOTE]
   >
   >連至「放棄的購物車」連結是外部 URL 的連結，這會將使用者重新導向至其購物車。Adobe Campaign 並未管理此參數。

1. 在此範例中，您希望在新增[建立事件](../../channels/using/configuring-transactional-event.md)時定義三個欄位：名字、最後諮詢的產品、購物車數量總計。要執行此操作，請在訊息內容中[插入個人化欄位](../../designing/using/personalization.md#inserting-a-personalization-field)。

1. 透過 **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]** 瀏覽至那些欄位。

   ![](assets/message-center_7.png)

1. 您還可以豐富郵件的內容。 為此，請從連結到事件配置的表中添加欄位(請參閱 [豐富活動內容](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content))。 在此示例中，選擇 **[!UICONTROL Title (salutation)]** 的 **[!UICONTROL Profile]** 表 **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]**。

   ![](assets/message-center_7-enrichment.png)

1. 插入需要的所有欄位。

   ![](assets/message-center_8.png)

1. 選取您為此事件定義的設定檔，以預覽訊息。

   在「[預覽訊息](../../sending/using/previewing-messages.md)」區段中會詳細說明預覽訊息的步驟。

   ![](assets/message-center_9.png)

   您可以檢查個人化欄位是否符合在測試設定檔中輸入的資訊。有關此的詳細資訊，請參閱 [定義特定test配置檔案](../../channels/using/testing-transactional-message.md#defining-specific-test-profile)。

<!--## Using product listings in a transactional message {#using-product-listings-in-a-transactional-message}

When editing the content of a transactional email, you can create product listings referencing one or more data collections. For example, in a cart abandonment email, you can include a list of all products that were in the users' carts when they left your website, with an image, the price, and a link to each product.

>[!IMPORTANT]
>
>Product listings are only available for the email channel, when editing transactional email content through the [Email Designer](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-interface) interface.

To add a list of abandoned products in a transactional message, follow the steps below.

You can also watch [this set of videos](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/designing-content/product-listings-in-transactional-email.html#configure-product-listings-in-transactional-emails) explaining the steps that are required to configure product listings in a transactional email.

>[!NOTE]
>
>Adobe Campaign does not support nested product listings, meaning that you cannot include a product listing inside another one.

### Defining a product listing {#defining-a-product-listing}

Before being able to use a product listing in a transactional message, you need to define at the event level the list of products and the fields for each product of the list you want to display. For more on this, see [Defining data collections](../../channels/using/configuring-transactional-event.md#defining-data-collections).

1. In the transactional message, click the **[!UICONTROL Content]** block to modify the email content.
1. Drag and drop a structure component to the workspace. For more on this, see [Defining the email structure](../../designing/using/designing-from-scratch.md#defining-the-email-structure).

   For example, select a one-column structure component and add a text component, an image component and a button component. For more on this, see [Using content components](../../designing/using/designing-from-scratch.md#about-content-components).

1. Select the structure component you just created and click the **[!UICONTROL Enable product listing]** icon from the contextual toolbar.

   ![](assets/message-center_loop_create.png)

   The structure component is highlighted with an orange frame and the **[!UICONTROL Product listing]** settings are displayed in the left palette.

   ![](assets/message-center_loop_palette.png)

1. Select how the elements of the collection will be displayed:

    * **[!UICONTROL Row]**: horizontally, meaning each element on one row under the other.
    * **[!UICONTROL Column]**: vertically, meaning each element next to the other on the same row.

   >[!NOTE]
   >
   >The **[!UICONTROL Column]** option is only available when using a multicolumn structure component ( **[!UICONTROL 2:2 column]**, **[!UICONTROL 3:3 column]** and **[!UICONTROL 4:4 column]** ). When editing the product listing, only fill in the first column: the other columns will not be taken into account. For more on selecting structure components, see [Defining the email structure](../../designing/using/designing-from-scratch.md#defining-the-email-structure).

1. Select the data collection you created when configuring the event related to the transactional message. You can find it under the **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]** node.

   ![](assets/message-center_loop_selection.png)

   For more on configuring the event, see [Defining data collections](../../channels/using/configuring-transactional-event.md#defining-data-collections).

1. Use the **[!UICONTROL First item]** drop-down list to select which element will start the list displayed in the email.

   For example, if you select 2, the first item of the collection will not be displayed in the email. The product listing will start on the second item.

1. Select the maximum number of items to display in the list.

   >[!NOTE]
   >
   >If you want the elements of your list to be displayed vertically ( **[!UICONTROL Column]** ), the maximum number of items is limited according to the selected structure component (2, 3 or 4 columns). For more on selecting structure components, see [Editing the email structure](../../designing/using/designing-from-scratch.md#defining-the-email-structure).

### Populating the product listing {#populating-the-product-listing}

To display a list of products coming from the event linked to the transactional email, follow the steps below.

For more on creating a collection and related fields when configuring the event, see [Defining data collections](../../channels/using/configuring-transactional-event.md#defining-data-collections).

1. Select the image component you inserted, select **[!UICONTROL Enable personalization]** and click the pencil in the Settings pane.

   ![](assets/message-center_loop_image.png)

1. Select **[!UICONTROL Add personalization field]** in the **[!UICONTROL Image source URL]** window that opens.

   From the **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]** node, open the node corresponding to the collection that you created (here **[!UICONTROL Product list]** ) and select the image field that you defined (here **[!UICONTROL Product image]** ). Click **[!UICONTROL Save]**.

   ![](assets/message-center_loop_product-image.png)

   The personalization field that you selected is now displayed in the Settings pane.

1. At the desired position, select **[!UICONTROL Insert personalization field]** from the contextual toolbar.

   ![](assets/message-center_loop_product.png)

1. From the **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]** node, open the node corresponding to the collection that you created (here **[!UICONTROL Product list]** ) and select the field that you created (here **[!UICONTROL Product name]** ). Click **[!UICONTROL Confirm]**.

   ![](assets/message-center_loop_product_node.png)

   The personalization field that you selected is now displayed at the desired position in the email content.

1. Proceed similarly to insert the price.
1. Select some text and select **[!UICONTROL Insert link]** from the contextual toolbar.

   ![](assets/message-center_loop_link_insert.png)

1. Select **[!UICONTROL Add personalization field]** in the **[!UICONTROL Insert link]** window that opens.

   From the **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]** node, open the node corresponding to the collection that you created (here **[!UICONTROL Product list]** ) and select the URL field that you created (here **[!UICONTROL Product URL]** ). Click **[!UICONTROL Save]**.

   >[!IMPORTANT]
   >
   >For security reasons, make sure you insert the personalization field inside a link starting with a proper static domain name.

   ![](assets/message-center_loop_link_select.png)

   The personalization field that you selected is now displayed in the Settings pane.

1. Select the structure component on which the product listing is applied and select **[!UICONTROL Show fallback]** to define a default content.

   ![](assets/message-center_loop_fallback_show.png)

1. Drag one or more content components and edit them as needed.

   ![](assets/message-center_loop_fallback.png)

   The fallback content will be displayed if the collection is empty when the event is triggered, for example if a customer has nothing in his cart.

1. From the Settings pane, edit the styles for the product listing. For more on this, see [Managing email styles](../../designing/using/styles.md).
1. Preview the email using a test profile linked to the relevant transactional event and for which you defined collection data. For example, add the following information in the **[!UICONTROL Event data]** section for the test profile you want to use:

   ![](assets/message-center_loop_test-profile_payload.png)

   For more on defining a test profile in a transactional message, see [this section](../../channels/using/testing-transactional-message.md#defining-specific-test-profile).-->

## 基於配置檔案的事務性消息特性 {#profile-transactional-message-specificities}

您可以根據客戶市場營銷配置檔案發送事務性消息，這允許您利用所有配置檔案資訊來個性化消息內容、使用取消訂閱連結以及應用市場營銷類型規則，如 [疲勞規則](../../sending/using/fatigue-rules.md)。

* 有關基於事件和基於配置檔案的事務性消息之間的差異的更多資訊，請參見 [此部分](../../channels/using/getting-started-with-transactional-msg.md#transactional-message-types)。

* 有關建立基於配置檔案的事務性消息的配置步驟的詳細說明，請參見 [此部分](../../channels/using/configuring-transactional-event.md#profile-based-transactional-messages)。

建立、編輯和個性化配置檔案事務性消息的步驟與事件事務性消息的步驟大相同。

差異列示於下方。

1. [移至建立的交易式訊息，以編輯其內容。](#accessing-transactional-messages)
1. 在交易式訊息中，按一下 **[!UICONTROL Content]** 區段。除事務性電子郵件模板外，您還可以選擇任何針對 **[!UICONTROL Profile]** 資源。

   ![](assets/message-center_marketing_templates.png)

1. 選取預設的電子郵件範本。與所有營銷電子郵件類似，它包括 **取消訂閱連結**。

   ![](assets/message-center_marketing_perso_unsubscription.png)

   有關模板的詳細資訊，請參見 [此部分](../../designing/using/using-reusable-content.md#content-templates)。

1. 此外，與基於即時事件的配置相比，您 **直接訪問所有配置檔案資訊** 個性化您的郵件。 可以添加 [個性化欄位](../../designing/using/personalization.md#inserting-a-personalization-field) 正如您對任何其他標準營銷電子郵件所做的那樣。

1. 在發佈消息之前保存您所做的更改。 如需詳細資訊，請參閱「[發佈交易式訊息](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message)」。

<!--### Monitoring a profile transactional message delivery {#monitoring-a-profile-transactional-message-delivery}

Once the message is published and your site integration is done, you can monitor the delivery.

1. To view the message delivery log, click the icon at the bottom right of the **[!UICONTROL Deployment]** block.

1. Click the **[!UICONTROL Execution list]** tab.

   ![](assets/message-center_execution_tab.png)

1. Select the latest execution delivery.

   An **execution delivery** is a non-actionable and non-functional technical message created once a month for each transactional message, and each time a transactional message is edited and published again

1. Select the **[!UICONTROL Sending logs]** tab. In the **[!UICONTROL Status]** column, **[!UICONTROL Sent]** indicates that a profile has opted in.

   ![](assets/message-center_marketing_sending_logs.png)

1. Select the **[!UICONTROL Exclusions logs]** tab to view recipients who have been excluded from the message target, such as addresses on denylist.

   ![](assets/message-center_marketing_exclusion_logs.png)

>[!NOTE]
>
>For more information on accessing and using the logs, see [Monitoring a delivery](../../sending/using/monitoring-a-delivery.md).

For any profile that has opted out, the **[!UICONTROL Address on denylist]** typology rule excluded the corresponding recipient.

This rule is part of a specific typology that applies to all transactional messages based on the **[!UICONTROL Profile]** table.

![](assets/message-center_marketing_typology.png)

**Related topics**:

* [Integrate the event triggering](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger)
* [About typologies and typology rules](../../sending/using/about-typology-rules.md)-->
