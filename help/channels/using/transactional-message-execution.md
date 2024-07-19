---
title: 異動訊息執行與監控
description: 瞭解異動訊息執行，並探索如何監視異動訊息。
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
feature: Transactional Messaging
role: User
level: Intermediate
exl-id: 4cea7207-469c-46c5-9921-ae2f8f12d141
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '740'
ht-degree: 61%

---

# 異動訊息執行與監控 {#transactional-messaging-execution}

## 異動訊息執行傳送 {#transactional-message-execution-delivery}

訊息發佈並完成網站整合後，觸發事件時，就會將其指派給執行傳送。

<img src="assets/do-not-localize/icon_concepts.svg" width="60px">

**執行傳送**&#x200B;是每月針對每個交易式訊息建立一次且無法執行且無法運作的技術訊息，而且每次都會編輯並再次發佈交易式訊息。

**相關主題**：
* [發佈交易式訊息](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message)
* [整合事件觸發](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger)

## 異動訊息重試過程 {#transactional-message-retry-process}

暫時未傳送的交易式訊息可能會執行自動重試，直到傳送到期為止。如需傳遞期間的詳細資訊，請參閱「[有效期間參數](../../administration/using/configuring-email-channel.md#validity-period-parameters)」。

如果無法傳送交易式訊息，有兩種重試系統：

* 在交易式訊息傳遞層級，在將該事件指派給執行傳送之前（代表介於事件接收及傳送準備之間），交易式訊息可能會失敗。請參閱「[事件處理重試過程](#event-processing-retry-process)」。
* 在傳送過程層級，一旦將事件指派給執行傳送，交易式訊息就會因暫時錯誤而失敗。請參閱「[訊息傳送重試過程](#message-sending-retry-process)」。

### 事件處理重試過程 {#event-processing-retry-process}

觸發事件時，會將其指派給執行傳送。 如果無法將事件指派給執行傳送，則會延遲事件處理。然後會執行重試，直到將其指派給新的執行傳送為止。

>[!NOTE]
>
>交易式訊息傳送日誌中不會顯示延遲的事件，因為尚未將之指派給執行傳送。

例如，由於事件內容不正確、存取權限或品牌推廣有問題、套用類型規則時偵測到錯誤，因此無法將事件指派給執行傳送。在此情況下，您可以暫停訊息、編輯訊息以修正問題，然後再次發佈。之後，重試系統會將其指派給新的執行傳送。

### 訊息傳送重試過程 {#message-sending-retry-process}

一旦將事件指派給執行傳送，交易式訊息可能會因為暫時錯誤（例如，如果收件人的信箱已滿）而失敗。如需詳細資訊，請參閱[傳送暫時失敗後重試](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure)。

>[!NOTE]
>
>將事件指派給執行傳送時，其會顯示在此執行傳遞的傳送日誌中，而且只有在這個時候才會顯示。失敗的傳遞會顯示在交易式訊息傳送記錄檔的&#x200B;**[!UICONTROL Execution list]**&#x200B;標籤中。

### 重試程式限制 {#limitations}

**傳送日誌更新**

在重試過程中，不會對新執行傳送的傳送日誌進行立即更新（更新會透過排程的工作流程執行）。這表示即使交易式事件已經由新的執行傳送處理，該訊息仍可能處於 **[!UICONTROL Pending]** 狀態。

**執行傳送失敗**

您無法停止執行傳送。但是，如果目前的執行傳送失敗，只要在收到新事件時，就會建立新事件，而且所有新事件都會由這個新的執行傳遞進行處理。失敗的執行傳送不會處理任何新事件。

如果某些已指派給執行傳送的事件在重試流程中已延遲，並且該執行傳送失敗，則重試系統不會將延遲的事件指派給新的執行傳送，這意味著這些事件會遺失。 檢查[傳遞記錄](#monitoring-transactional-message-delivery)以檢視可能受影響的收件者。

## 監控異動訊息 {#monitoring-transactional-message-delivery}

若要監視異動訊息，您必須存取對應的[執行傳送](#transactional-message-execution-delivery)。

1. 若要檢視訊息傳送記錄檔，請按一下 **[!UICONTROL Deployment]** 區塊右下方的圖示。

   ![](assets/message-center_access_logs.png)

1. 按一下「**[!UICONTROL Execution list]**」標籤。

   ![](assets/message-center_execution_tab.png)

1. 選取您所選的執行傳送。

   ![](assets/message-center_execution_delivery.png)

1. 再按一下&#x200B;**[!UICONTROL Deployment]**&#x200B;區塊右下方的圖示。

   ![](assets/message-center_execution_access_logs.png)

   對於每個執行傳送，您可以像檢視標準傳送一樣檢視傳送記錄。 如需存取及使用記錄檔的詳細資訊，請參閱[監視傳遞](../../sending/using/monitoring-a-delivery.md)。

### 設定檔交易式訊息特性 {#profile-transactional-message-monitoring}

對於設定檔交易式訊息，您可以監控以下設定檔資訊。

選取 **[!UICONTROL Sending logs]** 索引標籤。在 **[!UICONTROL Status]** 欄中，**[!UICONTROL Sent]** 表示設定檔已選取加入。

![](assets/message-center_marketing_sending_logs.png)

選取&#x200B;**[!UICONTROL Exclusions logs]**&#x200B;索引標籤以檢視已從訊息目標（例如封鎖清單上的地址）中排除的收件者。

![](assets/message-center_marketing_exclusion_logs.png)

對於已選取退出的任何設定檔，**[!UICONTROL Address on denylist]**　類型規則會排除相對應的收件人。

此規則是特定類型的一部分，其適用於以 **[!UICONTROL Profile]** 表格為基礎的所有交易式訊息。

![](assets/message-center_marketing_typology.png)

**相關主題**：

* [關於類型與類型規則](../../sending/using/about-typology-rules.md)
* [監視傳遞](../../sending/using/monitoring-a-delivery.md)
