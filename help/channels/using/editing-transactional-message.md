---
solution: Campaign Standard
product: campaign
title: 編輯異動訊息
description: 瞭解如何存取、編輯和個人化交易訊息。
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
translation-type: tm+mt
source-git-commit: f19d4b5c1837f3f03789958abb1539d4edea0744
workflow-type: tm+mt
source-wordcount: '1489'
ht-degree: 59%

---


# 編輯異動訊息 {#editing-transactional-message}

建立並發佈事件<!--(the cart abandonment example as explained in [this section](../../channels/using/getting-started-with-transactional-msg.md#transactional-messaging-operating-principle))-->後，將自動建立相應的事務性消息。

配置和發佈事件的步驟顯示在[配置事務事件](../../channels/using/configuring-transactional-event.md)和[發佈事務事件](../../channels/using/publishing-transactional-event.md)部分。

存取、編輯和個人化此訊息的步驟如下所述。

>[!IMPORTANT]
>
>只有[Administration](../../administration/using/users-management.md#functional-administrators)角色的用戶才能訪問和編輯事務性消息。

訊息準備就緒後，即可進行測試並發佈。 請參閱[測試事務性消息](../../channels/using/testing-transactional-message.md)和[事務性消息生命週期](../../channels/using/publishing-transactional-message.md)。

## 訪問事務性消息{#accessing-transactional-messages}

要訪問您建立的事務性消息，請執行以下操作：

1. 按一下左上角的&#x200B;**[!UICONTROL Adobe Campaign]**&#x200B;徽標。
1. 選擇&#x200B;**[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Transactional messages]**。

   ![](assets/message-center_4.png)

1. 按一下您選擇的訊息以進行編輯。

   ![](assets/message-center_message-board.png)

您也可以透過位於對應事件設定畫面左側區域的連結直接存取交易式訊息。 請參閱[預覽和發佈事件](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event)

## 個人化交易式訊息 {#personalizing-a-transactional-message}

要編輯並個性化事務性消息，請遵循以下步驟。

>[!NOTE]
>
>本節介紹如何編輯&#x200B;**event-based**&#x200B;事務性消息。 **基於概要的**&#x200B;事務性消息的具體性詳細說明如下](#profile-transactional-message-specificities)。[
>
>建立基於事件的事務消息的配置步驟顯示在[本節](../../channels/using/configuring-transactional-event.md#event-based-transactional-messages)中。

例如，您想要傳送通知給已將產品新增至購物車並離開網站的網站使用者，而不需進行購買。 此示例顯示在[事務性消息傳遞操作原則](../../channels/using/getting-started-with-transactional-msg.md#transactional-messaging-operating-principle)部分。

1. 按一下 **[!UICONTROL Content]** 區塊以修改訊息的主旨與內容。在此範例中，選取包含影像與文字的任何範本。如需電子郵件內容範本的詳細資訊，請參閱[使用範本設計電子郵件](../../designing/using/using-reusable-content.md#designing-templates)。

   ![](assets/message-center_6.png)

1. 新增主旨並編輯訊息內容以符合您的需求。

   >[!NOTE]
   >
   >連至「放棄的購物車」連結是外部 URL 的連結，這會將使用者重新導向至其購物車。Adobe Campaign 並未管理此參數。

1. 在此範例中，您希望在新增[建立事件](../../channels/using/configuring-transactional-event.md)時定義三個欄位：名字、最後諮詢的產品、購物車數量總計。要執行此操作，請在訊息內容中[插入個人化欄位](../../designing/using/personalization.md#inserting-a-personalization-field)。

1. 透過 **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]** 瀏覽至那些欄位。

   ![](assets/message-center_7.png)

1. 您也可以豐富訊息的內容。 若要這麼做，請從您連結至事件設定的表格新增欄位（請參閱[豐富事件](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content)）。 在此示例中，從&#x200B;**[!UICONTROL Profile]**&#x200B;表中選擇&#x200B;**[!UICONTROL Title (salutation)]**&#x200B;欄位，直到&#x200B;**[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]**。

   ![](assets/message-center_7-enrichment.png)

1. 插入需要的所有欄位。

   ![](assets/message-center_8.png)

1. 選取您為此事件定義的設定檔，以預覽訊息。

   在「[預覽訊息](../../sending/using/previewing-messages.md)」區段中會詳細說明預覽訊息的步驟。

   ![](assets/message-center_9.png)

   您可以檢查個人化欄位是否符合在測試設定檔中輸入的資訊。如需詳細資訊，請參閱[定義特定測試描述檔](../../channels/using/testing-transactional-message.md#defining-specific-test-profile)。

## 在交易式訊息中使用產品清單 {#using-product-listings-in-a-transactional-message}

編輯交易式電子郵件的內容時，您可以建立參照一或多個資料集合的產品清單。 例如，在購物車放棄電子郵件中，您可以包含使用者離開網站時購物車中的所有產品清單，以及影像、價格和每個產品的連結。

>[!IMPORTANT]
>
>產品清單僅適用於電子郵件通道，當您透過[電子郵件設計人員](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-interface)介面編輯交易電子郵件內容時。

若要在交易式訊息中新增放棄的產品清單，請遵循以下步驟。

您也可以觀看[這組影片](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/designing-content/product-listings-in-transactional-email.html?lang=en#configure-product-listings-in-transactional-emails)，說明在交易電子郵件中設定產品清單所需的步驟。

>[!NOTE]
>
>Adobe Campaign 不支援巢狀產品清單，這表示您無法將產品清單加入另一個產品清單中。

### 定義產品清單 {#defining-a-product-listing}

您必須先在事件層級中定義產品清單以及您想要顯示清單中各產品的欄位，才能在交易式訊息中使用產品清單。如需詳細資訊，請參閱「[定義資料集合](../../channels/using/configuring-transactional-event.md#defining-data-collections)」。

1. 在交易式訊息中，按一下 **[!UICONTROL Content]** 區塊以修改電子郵件內容。
1. 將結構元件拖放至工作區。有關詳細資訊，請參閱[定義電子郵件結構](../../designing/using/designing-from-scratch.md#defining-the-email-structure)。

   例如，選取單欄結構元件並新增文字元件、影像元件及按鈕元件。如需詳細資訊，請參閱[使用內容元件](../../designing/using/designing-from-scratch.md#about-content-components)。

1. 選取您剛剛建立的結構元件，然後按一下內容工具列中的 **[!UICONTROL Enable product listing]** 圖示。

   ![](assets/message-center_loop_create.png)

   結構元件會以橘色外框突出顯示，而 **[!UICONTROL Product listing]** 設定會顯示在左側色盤中。

   ![](assets/message-center_loop_palette.png)

1. 選取集合元素的顯示方式：

   * **[!UICONTROL Row]**：水平顯示，表示每列上的每個元素會位在彼此下方。
   * **[!UICONTROL Column]**：垂直顯示，表示每個元素會位在相同列上彼此旁邊。

   >[!NOTE]
   >
   >只有使用多欄結構元件時，才可使用　**[!UICONTROL Column]**　選項（**[!UICONTROL 2:2 column]**、**[!UICONTROL 3:3 column]** 及 **[!UICONTROL 4:4 column]**）。編輯產品清單時，僅填入第一欄：不會將其他欄納入考量。有關選擇結構元件的詳細資訊，請參閱[定義電子郵件結構](../../designing/using/designing-from-scratch.md#defining-the-email-structure)。

1. 選取您在設定與交易式訊息相關之事件時建立的資料集合。您可以在 **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]** 節點下方找到該集合。

   ![](assets/message-center_loop_selection.png)

   如需設定事件的詳細資訊，請參閱「[定義資料集合](../../channels/using/configuring-transactional-event.md#defining-data-collections)」。

1. 使用 **[!UICONTROL First item]** 下拉式清單，以選取會啟動電子郵件中所顯示清單的元素。

   例如，如果您選取 2，集合的第一個項目將不會顯示在電子郵件中。產品清單將從第二個項目開始。

1. 選取清單中要顯示的項目數量上限。

   >[!NOTE]
   >
   >如果您希望清單的元素垂直顯示　(**[!UICONTROL Column]**)，則會根據已選取的結構元件（2、3 或 4 欄）來限制項目數目上限。如需選取結構元件的詳細資訊，請參閱「[編輯電子郵件結構](../../designing/using/designing-from-scratch.md#defining-the-email-structure)」。

### 填入產品清單 {#populating-the-product-listing}

若要顯示從連結至交易式電子郵件之事件的產品清單，請遵循下列步驟。

如需在設定事件時建立集合及相關欄位的詳細資訊，請參閱「[定義資料集合](../../channels/using/configuring-transactional-event.md#defining-data-collections)」。

1. 選取您已插入的影像元件、選取 **[!UICONTROL Enable personalization]** 並按一下「設定」窗格中的鉛筆。

   ![](assets/message-center_loop_image.png)

1. 在開啟的 **[!UICONTROL Image source URL]** 視窗中選取　**[!UICONTROL Add personalization field]**。

   從　**[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]**　節點中，開啟與您建立之集合（此處 **[!UICONTROL Product list]**）相對應的節點，然後選取您定義的影像欄位（此處 **[!UICONTROL Product image]**）。按一下 **[!UICONTROL Save]**。

   ![](assets/message-center_loop_product-image.png)

   您選取的個人化欄位現在會顯示在「設定」窗格中。

1. 在需要的位置中，從內容工具列選取 **[!UICONTROL Insert personalization field]**。

   ![](assets/message-center_loop_product.png)

1. 從　**[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]**　節點中，開啟與您建立之集合（此處 **[!UICONTROL Product list]**）相對應的節點，然後選取您建立的欄位（此處 **[!UICONTROL Product name]**）。按一下 **[!UICONTROL Confirm]**。

   ![](assets/message-center_loop_product_node.png)

   您選取的個人化欄位現在會顯示在電子郵件內容的需要位置。

1. 以類似方式繼續插入價格。
1. 選取一些文字，然後從內容工具列選取 **[!UICONTROL Insert link]**。

   ![](assets/message-center_loop_link_insert.png)

1. 在開啟的 **[!UICONTROL Insert link]** 視窗中選取　**[!UICONTROL Add personalization field]**。

   從　**[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]**　節點中，開啟與您建立之集合（此處 **[!UICONTROL Product list]**）相對應的節點，然後選取您建立的　URL　欄位（此處 **[!UICONTROL Product URL]**）。按一下 **[!UICONTROL Save]**。

   >[!IMPORTANT]
   >
   >基於安全考量，請確定您將個人化欄位插入在連結（以適當靜態網域名稱開頭）內部。

   ![](assets/message-center_loop_link_select.png)

   您選取的個人化欄位現在會顯示在「設定」窗格中。

1. 選取要對產品清單套用的結構元件，並選取 **[!UICONTROL Show fallback]** 以定義預設內容。

   ![](assets/message-center_loop_fallback_show.png)

1. 拖曳一或多個內容元件，並視需要加以編輯。

   ![](assets/message-center_loop_fallback.png)

   如果集合在觸發事件（例如客戶購物車中沒有任何項目）時為空白，則會顯示後備內容。

1. 在「設定」窗格中，編輯產品清單的樣式。有關詳細資訊，請參閱[管理電子郵件樣式](../../designing/using/styles.md)。
1. 使用連結至相關交易式事件且您為其定義集合資料的測試設定檔，以預覽電子郵件。例如，在您要使用之測試設定檔的 **[!UICONTROL Event data]** 區段中新增下列資訊：

   ![](assets/message-center_loop_test-profile_payload.png)

   如需在交易式訊息中定義測試設定檔的詳細資訊，請參閱[本區段](../../channels/using/testing-transactional-message.md#defining-specific-test-profile)。

## 基於概要的事務性消息特性{#profile-transactional-message-specificities}

您可以根據客戶行銷設定檔來傳送交易式訊息，這可讓您運用所有設定檔資訊來個人化訊息內容、使用取消訂閱連結，並套用行銷類型學規則，例如[疲勞規則](../../sending/using/fatigue-rules.md)。

* 有關基於事件和基於配置檔案的事務消息之間差異的詳細資訊，請參閱[本節](../../channels/using/getting-started-with-transactional-msg.md#transactional-message-types)。

* 建立基於配置檔案的事務性消息的配置步驟在[本節](../../channels/using/configuring-transactional-event.md#profile-based-transactional-messages)中有詳細說明。

<!--### Editing a profile transactional message {#editing-profile-transactional-message}-->

建立、編輯和個性化配置檔案事務性消息的步驟與事件事務性消息的步驟基本相同。

差異列示於下方。

1. [移至建立的交易式訊息，以編輯其內容。](#accessing-transactional-messages)
1. 在交易式訊息中，按一下 **[!UICONTROL Content]** 區段。除了交易電子郵件範本外，您也可以選擇任何以&#x200B;**[!UICONTROL Profile]**&#x200B;資源為目標的電子郵件範本。

   ![](assets/message-center_marketing_templates.png)

1. 選取預設的電子郵件範本。與所有行銷電子郵件類似，它包含&#x200B;**取消訂閱連結**。

   ![](assets/message-center_marketing_perso_unsubscription.png)

   如需範本的詳細資訊，請參閱[本節](../../designing/using/using-reusable-content.md#content-templates)。

1. 此外，與基於即時事件的配置不同，您可以&#x200B;**直接訪問所有配置檔案資訊**&#x200B;以個性化您的消息。 您可以新增[個人化欄位](../../designing/using/personalization.md#inserting-a-personalization-field)，就像您對任何其他標準行銷電子郵件所做的一樣。

1. 在發佈訊息之前儲存您的變更。 如需詳細資訊，請參閱「[發佈交易式訊息](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message)」。

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
