---
solution: Campaign Standard
product: campaign
title: 事件交易式訊息
description: 瞭解如何建立與發佈事件交易式訊息。
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
translation-type: tm+mt
source-git-commit: 4e157a582de836fa325d95593491c756209b205e
workflow-type: tm+mt
source-wordcount: '1352'
ht-degree: 77%

---


# 事務性消息生命週期{#publishing-transactional-message}

當[事務性消息](../../channels/using/editing-transactional-message.md)準備好發送時，可以發佈該消息。

測試、發佈、暫停、取消發佈和刪除事件的步驟如下。 本節還介紹事務性消息傳遞重試過程。

## 交易式訊息發佈程序 {#transactional-messaging-pub-process}

下圖說明了整個事務性消息傳遞發佈流程。

![](assets/message-center_pub-process.png)

有關發佈事務性消息的詳細資訊，請參閱[本節](#publishing-a-transactional-message)。
有關暫停事務性消息的詳細資訊，請參閱[本節](#suspending-a-transactional-message-publication)。
有關取消發佈事務性消息的詳細資訊，請參閱[本節](#unpublishing-a-transactional-message)。

如需發佈和取消發佈事件的詳細資訊，請參閱[本節](../../channels/using/publishing-transactional-event.md)。

## 測試交易式訊息 {#testing-a-transactional-message}

您首先需要建立特定的測試設定檔，以便正確檢查交易訊息。

### 定義特定測試配置檔案{#defining-specific-test-profile}

定義將連結至您事件的測試設定檔，讓您預覽訊息並傳送相關證明。

1. 在事務性消息儀表板中，按一下&#x200B;**[!UICONTROL Create test profile]**&#x200B;按鈕。

   ![](assets/message-center_test-profile.png)

1. 在 **[!UICONTROL Event data used for personalization]** 區段中指定要以 JSON 格式傳送的資訊。這是預覽訊息與測試設定檔收到校樣時，將會使用的內容。

   ![](assets/message-center_event-data.png)

   >[!NOTE]
   >
   >您也可以輸入與設定檔表格相關的資訊。請參閱[豐富事件](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content)<!--and [Personalizing a transactional message](../../channels/using/editing-transactional-message.md#personalizing-a-transactional-message)-->。

1. 建立後，測試描述檔將預先指定在交易訊息中。 按一下訊息的 **[!UICONTROL Test profiles]** 區塊以檢查您的校樣目標。

   ![](assets/message-center_5.png)

您也可以建立新的測試設定檔，或是使用 **[!UICONTROL Test profiles]** 功能表中已存在的測試設定檔。操作步驟：

1. 按一下左上方的標誌 **[!UICONTROL Adobe Campaign]**，然後選取 **[!UICONTROL Profiles & audiences]** > **[!UICONTROL Test profiles]**。
1. 在&#x200B;**[!UICONTROL Event]**&#x200B;區段中，選取您剛建立的事件。 在此範例中，選取「購物車放棄率 (EVTcartAbandonment)」。
1. 在 **[!UICONTROL Event data]** 文字方塊中指定要以 JSON 格式傳送的資訊。

   ![](assets/message-center_3.png)

1. 儲存您的變更。
1. 存取您建立的訊息，並選取更新的測試設定檔。

**相關主題：**

* [管理測試設定檔](../../audiences/using/managing-test-profiles.md)
* [建立閱聽眾](../../audiences/using/creating-audiences.md)

### 傳送證明{#sending-proof}

建立一或多個特定測試設定檔並儲存交易訊息後，您就可以傳送測試證明。

![](assets/message-center_10.png)

傳送校樣的步驟詳見[傳送校樣](../../sending/using/sending-proofs.md)一節。

## 發佈交易式訊息 {#publishing-a-transactional-message}

檢查交易式訊息之後，即可發佈。

![](assets/message-center_12.png)

現在，觸發「購物車放棄率」事件之後，則會自動提示訊息，其中包含收件者的職務及姓氏、購物車 URL、上次諮詢的產品或產品清單（如果您已定義產品清單），以及要傳送的購物車總金額。

若要存取關於交易式訊息的報告，請使用 **[!UICONTROL Reports]** 按鈕。請參閱[動態報表](../../reporting/using/about-dynamic-reports.md)。

![](assets/message-center_13.png)

### 暫停交易式訊息發佈 {#suspending-a-transactional-message-publication}

您可以使用　**[!UICONTROL Pause]**　按鈕以暫停發佈交易式訊息，例如，修改訊息中所包含的資料。因此，系統將不會再處理這些事件，而會將之保留在 Adobe Campaign 資料庫的佇列中。

佇列的事件會在REST API中定義的時段內保留(請參閱[REST API檔案](../../api/using/managing-transactional-messages.md)，或如果您使用「觸發器」核心服務，則會在觸發器事件中保留（請參閱[關於Adobe Experience Cloud觸發器](../../integrating/using/about-adobe-experience-cloud-triggers.md)）。

![](assets/message-center_pause.png)

按一下　**[!UICONTROL Resume]**　時，則會處理所有佇列的事件（前提是這些事件並未過期）。它們現在會包含暫停範本發佈時進行的所有修改。

### 取消發佈交易式訊息 {#unpublishing-a-transactional-message}

按一下 **[!UICONTROL Unpublish]** 可讓您取消交易式訊息發佈，同時也可取消相對應事件的發佈，這會從與　REST API（與您先前建立之事件相對應的資源）刪除。

![](assets/message-center_unpublish-template.png)

現在，即使事件是透過網站觸發，也不會再傳送相對應的訊息，也不會將之儲存在資料庫中。

>[!NOTE]
>
>若要再次發佈訊息，您必須返回對應的事件設定[發佈事件](../../channels/using/publishing-transactional-event.md)，然後[發佈訊息](#publishing-a-transactional-message)。

如果您解除發佈已暫停的交易式訊息，則可能必須等候長達 24 小時，才能再次發佈。這是為了讓 **[!UICONTROL Database cleanup]** 工作流程清除已傳送至佇列的所有事件。

在「[暫停交易式訊息發佈](#suspending-a-transactional-message-publication)」一節中會詳細說明暫停訊息的步驟。

可透過 **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Workflows]** 存取每天凌晨 4:00 執行的工作流程 **[!UICONTROL Database cleanup]**。

### 刪除交易式訊息 {#deleting-a-transactional-message}

在取消發佈交易式訊息之後，或尚未發佈交易式訊息時，您可以從交易式訊息清單中刪除該訊息。操作步驟：

1. 按一下左上方的標誌 **[!UICONTROL Adobe Campaign]**，然後選取 **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Transactional messages]**。
1. 將滑鼠游標移到您選取的訊息上。
1. 按一下 **[!UICONTROL Delete element]** 按鈕。

![](assets/message-center_delete-template.png)

但是，只能在特定條件下刪除交易式訊息：

* 請確定交易式訊息的狀態為 **[!UICONTROL Draft]** 狀態，否則您無法將之刪除。**[!UICONTROL Draft]** 狀態適用於尚未發佈或已[取消發佈](#unpublishing-a-transactional-message)（而且並未[暫停](#suspending-a-transactional-message-publication)）的訊息。

* **交易式訊息**：除非將另一個交易式訊息連結到相對應的事件，否則如果已取消發佈交易式訊息，也需要取消發佈事件設定，才能成功刪除交易式訊息。如需詳細資訊，請參閱「[取消發佈事件](../../channels/using/publishing-transactional-event.md#unpublishing-an-event)」。

   >[!IMPORTANT]
   >
   >刪除已傳送通知的交易式訊息也會刪除其發送與追蹤日誌。

* **來自現成事件範本的交易式訊息（內部交易式訊息）**：如果內部交易式訊息是唯一與相對應內部事件關聯的訊息，則無法刪除該訊息。您必須先建立另一個交易式訊息，方法是複製該訊息或透過 **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Transactional message templates]** 功能表進行。

## 交易式訊息重試過程 {#transactional-message-retry-process}

暫時未傳送的交易式訊息可能會執行自動重試，直到傳送到期為止。如需傳遞期間的詳細資訊，請參閱「[有效期間參數](../../administration/using/configuring-email-channel.md#validity-period-parameters)」。

如果無法傳送交易式訊息，有兩種重試系統：

* 在交易式訊息傳遞層級，在將該事件指派給執行傳送之前（代表介於事件接收及傳送準備之間），交易式訊息可能會失敗。請參閱「[事件處理重試過程](#event-processing-retry-process)」。
* 在傳送過程層級，一旦將事件指派給執行傳送，交易式訊息就會因暫時錯誤而失敗。請參閱「[訊息傳送重試過程](#message-sending-retry-process)」。

### 事件處理重試過程 {#event-processing-retry-process}

如果無法將事件指派給執行傳送，則會延遲事件處理。然後會執行重試，直到將其指派給新的執行傳送為止。

>[!NOTE]
>
>交易式訊息傳送日誌中不會顯示延遲的事件，因為尚未將之指派給執行傳送。

例如，由於事件內容不正確、存取權限或品牌推廣有問題、套用類型規則時偵測到錯誤，因此無法將事件指派給執行傳送。在此情況下，您可以暫停訊息、編輯訊息以修正問題，然後再次發佈。之後，重試系統會將其指派給新的執行傳送。

### 訊息傳送重試過程 {#message-sending-retry-process}

一旦將事件指派給執行傳送，交易式訊息可能會因為暫時錯誤（例如，如果收件人的信箱已滿）而失敗。如需詳細資訊，請參閱[傳送暫時失敗後重試](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure)。

>[!NOTE]
>
>將事件指派給執行傳送時，其會顯示在此執行傳遞的傳送日誌中，而且只有在這個時候才會顯示。失敗的傳送會顯示在事務性訊息傳送記錄的&#x200B;**[!UICONTROL Execution list]**&#x200B;標籤中。

### 重試進程限制{#limitations}

**傳送日誌更新**

在重試過程中，不會對新執行傳送的傳送日誌進行立即更新（更新會透過排程的工作流程執行）。這表示即使交易式事件已經由新的執行傳送處理，該訊息仍可能處於 **[!UICONTROL Pending]** 狀態。

**執行傳送失敗**

您無法停止執行傳送。但是，如果目前的執行傳送失敗，只要在收到新事件時，就會建立新事件，而且所有新事件都會由這個新的執行傳遞進行處理。失敗的執行傳送不會處理任何新事件。

如果已經將一些事件指派給已延遲的執行傳送且該執行傳送失敗，重試系統不會將延遲的事件指派給新的執行傳送，這代表這些事件都會遺失。
