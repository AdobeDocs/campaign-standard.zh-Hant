---
title: 後續追蹤訊息
description: 瞭解如何建立、管理和傳送後續追蹤訊息。
audience: channels
content-type: reference
topic-tags: transactional-messaging
feature: Transactional Messaging
role: User
level: Intermediate
exl-id: 0a05cf20-7c8f-406b-acfd-7aece2c5dd26
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '773'
ht-degree: 2%

---

# 後續追蹤訊息 {#follow-up-messages}

後續訊息是預先定義的行銷傳遞範本，可用於工作流程，以傳送其他通訊給特定交易式訊息的收件者。

讓我們重複使用[異動訊息操作原則](../../channels/using/getting-started-with-transactional-msg.md#transactional-messaging-operating-principle)一節中所述的範例：會傳送購物車放棄電子郵件給您的網站使用者，這些使用者將產品加入購物車，但離開網站卻未完成購買。

想要傳送好記的提醒給收到購物車放棄通知但三天後未開啟購物車的所有客戶。 他們將會收到後續追蹤訊息，此訊息會根據所傳送第一封電子郵件中所使用的相同資料。

## 設定事件以傳送後續訊息 {#configuring-an-event-to-send-a-follow-up-message}

若要傳送後續訊息，您首先需要相應地設定與已收到之交易式訊息對應的事件。

1. 使用您建立的相同事件設定來傳送事件交易式訊息。 請參閱[設定交易式事件](../../channels/using/configuring-transactional-event.md)。
1. 設定事件時，請先核取&#x200B;**[!UICONTROL Create follow-up delivery template for this event]**&#x200B;方塊再發佈事件。

   ![](assets/message-center_follow-up-checkbox.png)

1. [預覽並發佈事件](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event)。

發佈事件後，系統會自動建立交易式訊息及連結至新事件的後續傳送範本。 傳送後續訊息的步驟在[本節](#sending-a-follow-up-message)中詳細說明。

## 存取後續追蹤訊息 {#accessing-the-follow-up-messages}

若要處理工作流程中的事件，需要傳遞範本。 但是，發佈事件時，所建立的[交易式訊息](../../channels/using/editing-transactional-message.md)無法當做範本使用。 因此，您需要建立特定的後續傳送範本，以支援此事件型別，並作為工作流程中的範本使用。

若要存取此範本：

1. 按一下左上角的&#x200B;**Adobe**&#x200B;標誌。
1. 選取&#x200B;**[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**。
1. 勾選左窗格中的&#x200B;**[!UICONTROL Follow-up messages]**&#x200B;方塊。

   ![](assets/message-center_follow-up-search.png)

只顯示後續訊息。

>[!IMPORTANT]
>
>只有具有[管理](../../administration/using/users-management.md#functional-administrators)角色的使用者才能存取及編輯異動訊息。

## 傳送後續追蹤訊息 {#sending-a-follow-up-message}

建立後續傳送範本後，您便可在工作流程中使用它來傳送後續訊息。

<!--You need to set up a workflow targeting the event corresponding to the transactional message that was already received.-->

1. 存取行銷活動清單並建立新的工作流程。

   請參閱[建立工作流程](../../automating/using/building-a-workflow.md#creating-a-workflow)。

1. 將&#x200B;**[!UICONTROL Scheduler]**&#x200B;活動拖放到工作流程中並加以開啟。 將執行頻率設定為每天一次。

   排程器活動顯示在[排程器](../../automating/using/scheduler.md)區段中。

1. 將&#x200B;**[!UICONTROL Query]**&#x200B;活動拖放到工作流程中並加以開啟。

   查詢活動顯示在[查詢](../../automating/using/query.md)區段中。

1. 若要在設定檔資源以外的資源上執行查詢，請移至活動的&#x200B;**[!UICONTROL Properties]**&#x200B;索引標籤，然後按一下&#x200B;**[!UICONTROL Resource]**&#x200B;下拉式清單。

   ![](assets/message-center_follow-up-query-properties.png)

   >[!NOTE]
   >
   >依預設，活動會預先設定為搜尋設定檔。

1. 選取您要鎖定的事件，以便僅存取此事件的資料。

   ![](assets/message-center_follow-up-query-resource.png)

1. 移至活動的&#x200B;**[!UICONTROL Target]**&#x200B;標籤，並將&#x200B;**[!UICONTROL Delivery logs (logs)]**&#x200B;元素從浮動視窗拖放至工作區。

   ![](assets/message-center_follow-up-delivery-logs.png)

   選取&#x200B;**[!UICONTROL Exists]**&#x200B;以定位所有收到電子郵件的客戶。

   ![](assets/message-center_follow-up-delivery-logs-exists.png)

1. 將&#x200B;**[!UICONTROL Tracking logs (tracking)]**&#x200B;元素從浮動視窗移至工作區，並選取「**[!UICONTROL Does not exist]**」以鎖定所有未開啟電子郵件的客戶。

   ![](assets/message-center_follow-up-delivery-and-tracking-logs.png)

1. 從浮動視窗拖放您要鎖定的事件（在此範例中為&#x200B;**購物車放棄**）到工作區。 然後定義規則以定位三天前傳送的所有訊息。

   ![](assets/message-center_follow-up-created.png)

   這表示會在執行工作流程三天前收到交易式訊息，且仍未開啟該訊息的所有收件者都會成為目標。

   按一下&#x200B;**[!UICONTROL Confirm]**&#x200B;以儲存查詢。

1. 將&#x200B;**電子郵件傳遞**&#x200B;活動拖放至您的工作流程中。

   電子郵件傳遞活動會顯示在[電子郵件傳遞](../../automating/using/email-delivery.md)區段中。

   ![](assets/message-center_follow-up-workflow.png)

   您也可以使用[SMS傳遞](../../automating/using/sms-delivery.md)或[推播通知傳遞](../../automating/using/push-notification-delivery.md)活動。 在此情況下，在建立事件設定時，請務必選取&#x200B;**[!UICONTROL Mobile (SMS)]**&#x200B;或&#x200B;**[!UICONTROL Mobile application]**&#x200B;通道。 請參閱[建立事件](../../channels/using/configuring-transactional-event.md#creating-an-event)。

1. 開啟&#x200B;**電子郵件傳遞**&#x200B;活動。 在建立精靈中，核取&#x200B;**[!UICONTROL Follow-up messages]**&#x200B;方塊並選取發佈事件後建立的後續傳遞範本。

   ![](assets/message-center_follow-up-template.png)

1. 在後續追蹤訊息內容中，您可以新增個人化欄位，善用您的事件內容。

   ![](assets/message-center_follow-up-content.png)

1. 選取&#x200B;**[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]**，以尋找您在建立事件時定義的欄位。 請參閱[個人化交易式訊息](../../channels/using/editing-transactional-message.md#personalizing-a-transactional-message)。

   ![](assets/message-center_follow-up-personalization.png)

   這表示您可以利用第一次傳送事件時使用的相同內容（包括擴充資料）來建立個人化的友善提醒。

1. 儲存活動並啟動工作流程。

工作流程開始後，三天前收到購物車放棄通知但未開啟的每位客戶都會收到以相同資料為基礎的後續追蹤訊息。

>[!NOTE]
>
>如果您在建立事件設定時選取&#x200B;**[!UICONTROL Profile]**&#x200B;目標維度，後續訊息也會運用Adobe Campaign行銷資料庫。 請參閱[設定檔交易式訊息](../../channels/using/editing-transactional-message.md#profile-transactional-message-specificities)。
