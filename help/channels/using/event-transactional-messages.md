---
title: 事件交易式訊息
description: 瞭解如何建立和發佈事件交易訊息。
page-status-flag: never-activated
uuid: d747feb5-58fb-4e12-a176-404f0eca5391
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: transactional-messaging
discoiquuid: 4f6317a1-9dfe-4714-bc1c-393629d855cd
context-tags: deliveryTransactionalTemplate,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1b70e18be29fd48d102313f6d741e9ffe053cc34

---


# 事件交易式訊息{#event-transactional-messages}

您可以傳送事件交易訊息，以事件為目標。 此類事務性消息不包含配置檔案資訊：傳送目標是由事件本身所包含的資料所定義。

建立並發佈事件(如本節所述的購物車放棄 [率](../../channels/using/about-transactional-messaging.md#transactional-messaging-operating-principle))後，就會自動建立對應的交易訊息。

配置步驟顯示在「配置事 [件以發送事務性消息」部分](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message) 。

為了讓事件觸發傳送交易訊息，您必須個人化訊息，然後測試並發佈訊息。

>[!NOTE]
>
>要訪問事務性消息，您必須是安全組的一 **[!UICONTROL Administrators (all units)]** 部分。
>
>事件事務性消息不包含配置檔案資訊，因此它們與疲勞規則不相容（即使在富集了配置檔案的情況下）。 請參 [閱疲勞規則](../../administration/using/fatigue-rules.md#choosing-the-channel)。

## 在事務性消息中定義測試配置檔案 {#defining-a-test-profile-in-a-transactional-message}

定義已調整的測試設定檔，讓您預覽訊息並傳送校對。

### 在事務性消息中建立測試配置檔案 {#creating-a-test-profile-within-the-transactional-----------message}

1. 若要存取您建立的訊息，請按一 **[!UICONTROL Adobe Campaign]** 下左上角的標誌，然後選取 **[!UICONTROL Marketing plans]** &gt; **[!UICONTROL Transactional messages]** &gt; **[!UICONTROL Transactional messages]**。

   ![](assets/message-center_4.png)

1. 建立將連結至您事件的測試設定檔。

   ![](assets/message-center_test-profile.png)

1. 在區段中指定要以JSON格式傳送的 **[!UICONTROL Event data used for personalization]** 資訊。 這是預覽訊息和測試設定檔收到校對時要使用的內容。

   ![](assets/message-center_event-data.png)

   >[!NOTE]
   >
   >您也可以輸入與配置檔案表相關的資訊。 請參 [閱豐富交易式訊息內容](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content)。

1. 在建立後，測試設定檔會預先指定在交易訊息中。 按一 **[!UICONTROL Test profiles]** 下訊息區塊以檢查您的證明目標。

   ![](assets/message-center_5.png)

### 在事務性消息外建立測試配置檔案 {#creating-a-test-profile-outside-the-transactional-----------message}

您也可以建立新的測試設定檔，或使用功能表中已存在的測試設 **[!UICONTROL Test profiles]** 定檔。

1. 按一下 **[!UICONTROL Adobe Campaign]** 左上角的標誌，然後選取 **[!UICONTROL Profiles & audiences]** &gt; **[!UICONTROL Test profiles]**。
1. 在您選 **[!UICONTROL Event]** 擇之測試設定檔頁面的區段中，選取您剛建立的事件。 在此範例中，選取「購物車放棄(EVTcartAppliation)」。
1. 在文字方塊中指定要以JSON格式傳送 **[!UICONTROL Event data]** 的資訊。

   ![](assets/message-center_3.png)

1. 儲存您的變更。

您現在可以存取您建立的訊息，並選取更新的測試設定檔。

**相關主題：**

* [管理測試設定檔](../../sending/using/managing-test-profiles-and-sending-proofs.md)
* [定義觀眾](../../audiences/using/creating-audiences.md)

## 個人化交易式訊息 {#personalizing-a-transactional-message}

要在事務性消息中設定個人化，請執行以下步驟：

1. 按一下 **[!UICONTROL Content]** 區塊以修改訊息的主旨和內容。 在此範例中，選取任何包含影像和文字的範本。 如需電子郵件內容範本的詳細資訊，請參閱「使 [用範本設計」](../../designing/using/using-reusable-content.md#designing-templates)。

   ![](assets/message-center_6.png)

1. 新增主旨並編輯訊息內容以符合您的需求。

   >[注意]
   >
   >放棄購物車的連結是外部URL的連結，會將訪客重新導向至其購物車。 Adobe Campaign不會管理此參數。

1. 在此範例中，您要新增建立事件時所定義的三 [個欄位](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message):名字、最後咨詢的產品、購物車總量。 若要這麼做，請 [在訊息內容中插入個人化欄位](../../designing/using/personalization.md#inserting-a-personalization-field) 。

1. 瀏覽至&gt; **[!UICONTROL Context]****[!UICONTROL Real-time event]** &gt;的欄位 **[!UICONTROL Event context]**。

   ![](assets/message-center_7.png)

1. 若要豐富訊息的內容，請從您連結事件的表格中選取欄位，以新增欄位。 在我們的範例中，選取 **[!UICONTROL Title (salutation)]** 表格中的欄 **[!UICONTROL Profile]** 位， **[!UICONTROL Context]** 透過&gt; **[!UICONTROL Real-time event]** &gt; **[!UICONTROL Event context]**。

   ![](assets/message-center_7-enrichment.png)

1. 插入所需的所有欄位。

   ![](assets/message-center_8.png)

1. 選取您為此事件定義的描述檔，以預覽訊息。

   預覽訊息的步驟在「預覽訊息」區 [段中詳述](../../sending/using/previewing-messages.md) 。

   ![](assets/message-center_9.png)

   您可以檢查個人化欄位是否符合測試描述檔中輸入的資訊。 如需詳細資訊，請參 [閱在交易訊息中定義測試描述檔](#defining-a-test-profile-in-a-transactional-message)。

## 在事務性消息中使用產品清單 {#using-product-listings-in-a-transactional-message}

您可以建立產品清單，參考交易電子郵件內容中的一或多個資料集合。 例如，在購物車放棄電子郵件中，您可以包含使用者離開網站時購物車中的所有產品清單，以及影像、價格和每個產品的連結。

>[!CAUTION]
>
>只有在通過「電子郵件設計器」介面編輯事務性電子郵件消息時，產品 [清單才可用](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-interface) 。

要在事務性消息中添加放棄的產品清單，請遵循以下步驟。

您也可以觀看一組影片，說明在交易式電子郵件中設定產品清單所需的步驟。 For more on this, see [this page](https://helpx.adobe.com/campaign/kt/acs/using/acs-product-listings-in-transactional-emails-feature-video-setup.html).

>[!NOTE]
>
>Adobe Campaign不支援巢狀產品清單，這表示您無法將產品清單加入另一個產品清單中。

### 定義產品清單 {#defining-a-product-listing}

在交易訊息中使用產品清單之前，您必須在事件層級定義產品清單以及您要顯示清單中各產品的欄位。 如需詳細資訊，請參閱定 [義資料集合](../../administration/using/configuring-transactional-messaging.md#defining-data-collections)。

1. 在交易訊息中，按一下 **[!UICONTROL Content]** 區塊以修改電子郵件內容。
1. 將結構元件拖放到工作區。 如需詳細資訊，請參閱「 [編輯電子郵件結構」](../../designing/using/designing-from-scratch.md#defining-the-email-structure)。

   例如，選擇一列結構元件並添加文本元件、影像元件和按鈕元件。 如需詳細資訊，請參 [閱新增片段和元件](../../designing/using/designing-from-scratch.md#defining-the-email-structure)。

1. 選擇剛建立的結構元件，然後按一下上下文 **[!UICONTROL Enable product listing]** 工具欄中的表徵圖。

   ![](assets/message-center_loop_create.png)

   結構元件會以橘色的影格反白顯示，而 **[!UICONTROL Product listing]** 設定會顯示在左側浮動視窗中。

   ![](assets/message-center_loop_palette.png)

1. 選擇系列元素的顯示方式：

   * **[!UICONTROL Row]**:水準，表示一列上另一列下方的每個元素。
   * **[!UICONTROL Column]**:垂直，表示同一行上的每個元素相鄰。
   >[!NOTE]
   >
   >只 **[!UICONTROL Column]** 有當使用多欄結構元件（、和）時， **[!UICONTROL 2:2 column]****[!UICONTROL 3:3 column]** 才可使用此選 **[!UICONTROL 4:4 column]** 項。 編輯產品清單時，僅填入第一欄：其他欄則不會納入考量。 有關選擇結構元件的詳細資訊，請參 [閱編輯電子郵件結構](../../designing/using/designing-from-scratch.md#defining-the-email-structure)。

1. 選擇在配置與事務性消息相關的事件時建立的資料收集。 您可以在&gt; **[!UICONTROL Context]** &gt; **[!UICONTROL Real-time event]** &gt;節點下 **[!UICONTROL Event context]** 找到。

   ![](assets/message-center_loop_selection.png)

   如需設定事件的詳細資訊，請參閱定 [義資料集合](../../administration/using/configuring-transactional-messaging.md#defining-data-collections)。

1. 使用下 **[!UICONTROL First item]** 拉式清單來選取要啟動電子郵件中顯示清單的元素。

   例如，如果您選取2，系列的第一個項目將不會顯示在電子郵件中。 產品清單將從第二個項目開始。

1. 選取清單中要顯示的項目數上限。

   >[!NOTE]
   >
   >如果希望清單的元素垂直顯示( **[!UICONTROL Column]** )，則根據選定的結構元件（2、3或4列）限制項的最大數量。 有關選擇結構元件的詳細資訊，請參 [閱編輯電子郵件結構](../../designing/using/designing-from-scratch.md#defining-the-email-structure)。

### 填入產品清單 {#populating-the-product-listing}

若要顯示連結至交易式電子郵件之事件的產品清單，請遵循下列步驟。

如需設定事件時建立系列和相關欄位的詳細資訊，請參閱定 [義資料系列](../../administration/using/configuring-transactional-messaging.md#defining-data-collections)。

1. 選取您插入的影像元件，選取 **[!UICONTROL Enable personalization]** 並按一下「設定」窗格中的鉛筆。

   ![](assets/message-center_loop_image.png)

1. 在打 **[!UICONTROL Add personalization field]** 開的 **[!UICONTROL Image source URL]** 窗口中選擇。

   從&gt; **[!UICONTROL Context]** &gt;節 **[!UICONTROL Real-time event]** 點中，開啟與您建立的系列(此處 **[!UICONTROL Event context]** )對應的節點，然後選擇您定義的映像欄位(此處 **[!UICONTROL Product list]****[!UICONTROL Product image]** )。 Click **[!UICONTROL Save]**.

   ![](assets/message-center_loop_product-image.png)

   您選取的個人化欄位現在會顯示在「設定」窗格中。

1. 在所要的位置，從內容相關工 **[!UICONTROL Insert personalization field]** 具列中選取。

   ![](assets/message-center_loop_product.png)

1. 從&gt; **[!UICONTROL Context]** &gt;節 **[!UICONTROL Real-time event]** 點中，開啟與您建立的系列(此處 **[!UICONTROL Event context]** )對應的節點，然後選擇您建立的欄位(此處 **[!UICONTROL Product list]****[!UICONTROL Product name]** )。 Click **[!UICONTROL Confirm]**.

   ![](assets/message-center_loop_product_node.png)

   您選取的個人化欄位現在會顯示在電子郵件內容的所需位置。

1. 以類似方式繼續插入價格。
1. 選擇一些文本，然後從上 **[!UICONTROL Insert link]** 下文工具欄中選擇。

   ![](assets/message-center_loop_link_insert.png)

1. 在打 **[!UICONTROL Add personalization field]** 開的 **[!UICONTROL Insert link]** 窗口中選擇。

   從&gt; **[!UICONTROL Context]** &gt;節 **[!UICONTROL Real-time event]** 點中，開啟與您所建立之系列對應的節點(此處 **[!UICONTROL Event context]** )，然後選取您所建立的URL欄位(此處 **[!UICONTROL Product list]****[!UICONTROL Product URL]** )。 Click **[!UICONTROL Save]**.

   >[!CAUTION]
   >
   >出於安全原因，請務必將個人化欄位插入以適當靜態網域名稱開始的連結中。

   ![](assets/message-center_loop_link_select.png)

   您選取的個人化欄位現在會顯示在「設定」窗格中。

1. 選擇應用產品清單的結構元件，並選 **[!UICONTROL Show fallback]** 擇定義預設內容。

   ![](assets/message-center_loop_fallback_show.png)

1. 拖曳一或多個內容元件，並視需要加以編輯。

   ![](assets/message-center_loop_fallback.png)

   如果系列在觸發事件時為空，例如客戶購物車中沒有任何項目，則會顯示備援內容。

1. 在「設定」窗格中，編輯產品清單的樣式。 如需詳細資訊，請參閱「編輯 [電子郵件樣式](../../designing/using/styles.md)」。
1. 使用連結至相關交易事件且您已定義收集資料的測試設定檔來預覽電子郵件。 例如，在您要使用的測試設定 **[!UICONTROL Event data]** 檔區段中新增下列資訊：

   ![](assets/message-center_loop_test-profile_payload.png)

   如需在交易訊息中定義測試描述檔的詳細資訊，請參 [閱本節](#defining-a-test-profile-in-a-transactional-message)。

## 測試事務性消息 {#testing-a-transactional-message}

儲存交易訊息後，您現在可以傳送證明來測試。

![](assets/message-center_10.png)

傳送證明的步驟在傳送證明一節 [中詳述](../../sending/using/managing-test-profiles-and-sending-proofs.md#sending-proofs) 。

## 發佈交易訊息 {#publishing-a-transactional-message}

勾選交易訊息後，即可發佈。

![](assets/message-center_12.png)

現在，一旦觸發「購物車放棄」事件，就會自動提示訊息，內含收件者的標題和姓氏、購物車URL、上次諮詢的產品或產品清單（如果您定義產品清單），以及要傳送的購物車總金額。

要訪問有關事務性消息的報告，請使用 **[!UICONTROL Reports]** 按鈕。 請參閱 [報表](../../reporting/using/about-dynamic-reports.md)。

![](assets/message-center_13.png)

## 暫停事務性消息發佈 {#suspending-a-transactional-message-publication}

您可以暫停發佈事務性消息， **[!UICONTROL Pause]** 例如使用按鈕修改消息中包含的資料。 因此，這些事件不會再處理，而會保留在Adobe Campaign資料庫的佇列中。

佇列的事件會在REST API中定義的時段內保留(請參閱 [REST API檔案](../../api/using/about-campaign-standard-apis.md))，或在觸發器事件中(如果您使用「觸發器」核心服務，請參閱 [Working with Campaign and Experience cloud觸發器](../../integrating/using/about-adobe-experience-cloud-triggers.md))。

![](assets/message-center_pause.png)

按一 **[!UICONTROL Resume]**&#x200B;下時，會處理所有佇列的事件（前提是未過期）。 現在，範本發佈暫停時，它們會包含所有進行的修改。

## 取消發佈交易式訊息 {#unpublishing-a-transactional-message}

按一下 **[!UICONTROL Unpublish]** 可以取消事務性消息發佈，也可以取消相應事件的發佈，該發佈會從REST API中刪除與先前建立的事件對應的資源。 現在，即使事件是透過您的網站觸發，對應的訊息也不會再傳送，也不會儲存在資料庫中。

![](assets/message-center_unpublish-template.png)

>[!NOTE]
>
>若要再次發佈訊息，您必須返回對應的事件設定、發佈訊息，然後發佈訊息。 如需詳細資訊，請參閱「發 [布交易式訊息」](#publishing-a-transactional-message)。

如果您解除發佈已暫停的交易訊息，您可能必須等候最多24小時，才能再次發佈。 這可讓工作流 **[!UICONTROL Database cleanup]** 程清除傳送至佇列的所有事件。 暫停消息的步驟在暫停事務性消息發 [布部分中有詳細說明](#suspending-a-transactional-message-publication) 。

每 **[!UICONTROL Database cleanup]** 天凌晨4點執行的工作流程可透過 **[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt;存取 **[!UICONTROL Workflows]**。

## 刪除事務性消息 {#deleting-a-transactional-message}

![](assets/message-center_delete-template.png)

選擇事務性消息後，即使已發佈該消息，您也 **[!UICONTROL Delete element]** 可以使用按鈕將其刪除。 但是，刪除事務性消息只能在特定條件下完成：

* **事務性消息**:要刪除事務性消息，應取消發佈消息，而不應暫停。

   如果未發佈事務性消息，則事件配置也需要取消發佈才能成功刪除事務性消息，除非另一個事務性消息連結到相應的事件。 有關如何取消發佈事務性消息的詳細資訊，請參閱本 [節](#unpublishing-a-transactional-message)。

   >[!CAUTION]
   >
   >刪除已發送通知的事務性消息也會刪除其發送和跟蹤日誌。

* **來自現成可用事件範本的交易訊息（內部交易訊息）**:要刪除內部事務性消息，應取消發佈消息，而不應暫停。

   它也不應是事件中唯一的事務性消息，其他消息必須連結到相應的事件。

## 事務性消息重試過程 {#transactional-message-retry-process}

暫時未傳送的事務性消息可能會執行自動重試，直到傳送過期為止。 有關交貨期間的詳細資訊，請參 [閱有效期間參數](../../administration/using/configuring-email-channel.md#validity-period-parameters)。

發送事務性消息失敗時，有兩個重試系統：

* 在事務性消息傳遞級別，事務性消息在事件被分配給執行傳送之前可能失敗，這意味著事件接收和傳送準備之間。 請參閱 [事件處理重試程式](#event-processing-retry-process)。
* 在發送進程級別，一旦將事件分配給執行傳送，事務性消息就會因臨時錯誤而失敗。 請參 [閱消息發送重試進程](#message-sending-retry-process)。

### 事件處理重試程式 {#event-processing-retry-process}

如果事件無法指派給執行傳送，則事件處理會延遲。 然後會執行重試，直到將其指派給新的執行傳送。

>[!NOTE]
>
>事務性消息發送日誌中不會顯示延遲的事件，因為它尚未分配給執行傳送。

例如，由於事件內容不正確、存取權或品牌有問題、套用排版規則等，因此無法將事件指派給執行傳送。 在這種情況下，您可以暫停訊息、編輯訊息以修正問題，然後再次發佈。 然後，重試系統會將其分配給新的執行傳送。

### 消息發送重試進程 {#message-sending-retry-process}

一旦將事件指派給執行傳送，事務性消息就會因為臨時錯誤而失敗，例如，如果收件人的郵箱已滿。 如需詳細資訊，請參 [閱傳送暫時失敗後重試](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure)。

>[!NOTE]
>
>將事件指派給執行傳送時，它會出現在此執行傳送的傳送記錄中，而且此時才會顯示。 失敗的傳送會顯示在交易 **[!UICONTROL Execution list]** 訊息的標籤中。

### 限制 {#limitations}

**傳送記錄檔更新**

在重試過程中，不會立即更新新執行傳送的傳送記錄（更新是透過排程的工作流程執行）。 這表示即使事務事件已經由 **[!UICONTROL Pending]** 新的執行傳送處理，該消息仍可能處於狀態。

**執行傳送失敗**

您無法停止執行傳送。 但是，如果當前執行傳送失敗，當收到新事件時，就會建立新事件，而所有新事件都會由此新的執行傳送處理。 失敗的執行傳送不會處理任何新事件。

如果已分配給執行傳送的某些事件已經延遲，並且如果該執行傳送失敗，則重試系統不會將延遲的事件指派給新的執行傳送，這意味著這些事件將丟失。
