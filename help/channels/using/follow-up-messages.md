---
solution: Campaign Standard
product: campaign
title: 後續追蹤訊息
description: 了解如何建立、管理和傳送後續訊息。
audience: channels
content-type: reference
topic-tags: transactional-messaging
feature: 異動訊息傳送
role: User
level: Intermediate
exl-id: 0a05cf20-7c8f-406b-acfd-7aece2c5dd26
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '775'
ht-degree: 3%

---

# 後續追蹤訊息 {#follow-up-messages}

後續訊息是預先定義的行銷傳送範本，可用於工作流程，以傳送其他通訊給特定交易式訊息的收件者。

讓我們重複使用[交易式訊息操作原則](../../channels/using/getting-started-with-transactional-msg.md#transactional-messaging-operating-principle)區段中所述的範例：購物車放棄電子郵件會傳送給將產品新增至購物車，但未進行購買便離開網站的網站使用者。

您想要傳送好記提醒給收到購物車放棄通知，但三天後未開啟通知的所有客戶。 他們將會收到後續訊息，其依據是第一封電子郵件中所使用的相同資料。

## 設定事件以傳送後續訊息 {#configuring-an-event-to-send-a-follow-up-message}

若要傳送後續訊息，您必須先相應地設定與已接收的交易式訊息相對應的事件。

1. 使用您建立的事件設定，以傳送事件交易式訊息。 請參閱[設定交易式事件](../../channels/using/configuring-transactional-event.md)。
1. 設定事件時，請在發佈事件之前勾選&#x200B;**[!UICONTROL Create follow-up delivery template for this event]**&#x200B;方塊。

   ![](assets/message-center_follow-up-checkbox.png)

1. [預覽和發佈事件](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event)。

發佈事件後，系統會自動建立連結至新事件的交易式訊息和後續傳送範本。 在[本節](#sending-a-follow-up-message)中詳細說明了發送後續消息的步驟。

## 存取後續訊息 {#accessing-the-follow-up-messages}

若要處理工作流程中的事件，需要傳遞範本。 不過，發佈事件時，建立的[交易式訊息](../../channels/using/editing-transactional-message.md)無法作為範本使用。 因此，您需要建立特定的後續傳送範本，專門設計以支援此事件類型，並用作工作流程中的範本。

若要存取此範本：

1. 按一下左上角的&#x200B;**[!UICONTROL Adobe Campaign]**&#x200B;標誌。
1. 選擇&#x200B;**[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**。
1. 勾選左窗格中的&#x200B;**[!UICONTROL Follow-up messages]**&#x200B;方塊。

   ![](assets/message-center_follow-up-search.png)

只會顯示後續訊息。

>[!IMPORTANT]
>
>只有具有[Administration](../../administration/using/users-management.md#functional-administrators)角色的使用者才能存取和編輯交易式訊息。

## 傳送後續訊息 {#sending-a-follow-up-message}

建立後續傳送範本後，您就可以在工作流程中使用該範本，以傳送後續訊息。

<!--You need to set up a workflow targeting the event corresponding to the transactional message that was already received.-->

1. 存取行銷活動清單並建立新的工作流程。

   請參閱[建立工作流](../../automating/using/building-a-workflow.md#creating-a-workflow)。

1. 將&#x200B;**[!UICONTROL Scheduler]**&#x200B;活動拖放至工作流程並開啟。 將執行頻率設為一天一次。

   調度程式活動顯示在[調度程式](../../automating/using/scheduler.md)部分中。

1. 將&#x200B;**[!UICONTROL Query]**&#x200B;活動拖放至工作流程並開啟。

   「查詢」活動顯示在[Query](../../automating/using/query.md)區段中。

1. 若要對設定檔資源以外的資源執行查詢，請前往活動的&#x200B;**[!UICONTROL Properties]**&#x200B;標籤，然後按一下&#x200B;**[!UICONTROL Resource]**&#x200B;下拉式清單。

   ![](assets/message-center_follow-up-query-properties.png)

   >[!NOTE]
   >
   >依預設，活動會預先設定為搜尋設定檔。

1. 選取您要定位的事件，以便您只能存取此事件中的資料。

   ![](assets/message-center_follow-up-query-resource.png)

1. 前往活動的&#x200B;**[!UICONTROL Target]**&#x200B;標籤，並將&#x200B;**[!UICONTROL Delivery logs (logs)]**&#x200B;元素從浮動視窗拖放至工作區。

   ![](assets/message-center_follow-up-delivery-logs.png)

   選擇&#x200B;**[!UICONTROL Exists]**&#x200B;以定位所有收到電子郵件的客戶。

   ![](assets/message-center_follow-up-delivery-logs-exists.png)

1. 將&#x200B;**[!UICONTROL Tracking logs (tracking)]**&#x200B;元素從浮動視窗移至工作區，並選取&#x200B;**[!UICONTROL Does not exist]**&#x200B;來鎖定所有未開啟電子郵件的客戶。

   ![](assets/message-center_follow-up-delivery-and-tracking-logs.png)

1. 從浮動視窗將您要定位的事件（此範例中為&#x200B;**購物車放棄**）拖放至工作區。 然後定義規則，以定位三天前傳送的所有訊息。

   ![](assets/message-center_follow-up-created.png)

   這表示所有在執行工作流程三天前收到交易式訊息但尚未開啟的收件者，都會設為目標。

   按一下&#x200B;**[!UICONTROL Confirm]**&#x200B;以儲存查詢。

1. 將&#x200B;**電子郵件傳送**&#x200B;活動拖放至工作流程中。

   電子郵件傳送活動顯示在[電子郵件傳送](../../automating/using/email-delivery.md)區段中。

   ![](assets/message-center_follow-up-workflow.png)

   您也可以使用[SMS傳送](../../automating/using/sms-delivery.md)或[推播通知傳送](../../automating/using/push-notification-delivery.md)活動。 在此情況下，請務必在建立事件設定時選取&#x200B;**[!UICONTROL Mobile (SMS)]**&#x200B;或&#x200B;**[!UICONTROL Mobile application]**&#x200B;通道。 請參閱[建立事件](../../channels/using/configuring-transactional-event.md#creating-an-event)。

1. 開啟&#x200B;**電子郵件傳送**&#x200B;活動。 在建立精靈中，核取&#x200B;**[!UICONTROL Follow-up messages]**&#x200B;方塊，並選取發佈事件後建立的後續傳送範本。

   ![](assets/message-center_follow-up-template.png)

1. 在後續訊息內容中，您可以新增個人化欄位，以運用事件的內容。

   ![](assets/message-center_follow-up-content.png)

1. 通過選擇&#x200B;**[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]**，查找建立事件時定義的欄位。 請參閱[個人化交易式訊息](../../channels/using/editing-transactional-message.md#personalizing-a-transactional-message)。

   ![](assets/message-center_follow-up-personalization.png)

   這表示您可以運用第一次傳送事件時使用的相同內容，包括擴充資料，以建立個人化的好記提醒。

1. 儲存活動並啟動工作流程。

工作流程開始後，每個在三天前收到購物車放棄通知但未開啟的客戶，都會收到以相同資料為基礎的後續訊息。

>[!NOTE]
>
>如果您在建立事件設定時選取了&#x200B;**[!UICONTROL Profile]**&#x200B;目標維度，後續訊息也會運用Adobe Campaign行銷資料庫。 請參閱[設定檔交易式訊息](../../channels/using/editing-transactional-message.md#profile-transactional-message-specificities)。
