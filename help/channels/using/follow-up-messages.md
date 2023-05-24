---
title: 後續追蹤訊息
description: 瞭解如何建立、管理和發送後續消息。
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

後續消息是預定義的市場營銷傳遞模板，可在工作流中用於向特定事務性消息的收件人發送另一通信。

讓我們重複使用中介紹的示例 [事務性消息傳遞操作原則](../../channels/using/getting-started-with-transactional-msg.md#transactional-messaging-operating-principle) 部分：將向您的網站用戶發送購物車放棄電子郵件，這些用戶將產品添加到購物車中，但離開網站時不會進行購買。

您希望向收到購物車放棄通知但三天後未開啟該通知的所有客戶發送友好提醒。 他們將根據在發送的第一封電子郵件中使用的相同資料接收後續消息。

## 配置事件以發送後續消息 {#configuring-an-event-to-send-a-follow-up-message}

要發送後續消息，您首先需要相應配置與已接收的事務性消息對應的事件。

1. 使用您建立的事件配置來發送事件事務性消息。 請參閱 [配置事務事件](../../channels/using/configuring-transactional-event.md)。
1. 配置事件時，請檢查 **[!UICONTROL Create follow-up delivery template for this event]** 框。

   ![](assets/message-center_follow-up-checkbox.png)

1. [預覽和發佈事件](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event)。

一旦發佈了事件，將自動建立連結到新事件的事務性消息和後續傳遞模板。 有關發送後續消息的步驟，請參見 [此部分](#sending-a-follow-up-message)。

## 訪問後續消息 {#accessing-the-follow-up-messages}

要處理工作流中的事件，需要交貨模板。 但是，在發佈事件時， [事務性消息](../../channels/using/editing-transactional-message.md) 不能將建立的模板用作模板。 因此，您需要建立特定的後續交付模板，該模板旨在支援此事件類型並用作工作流中的模板。

要訪問此模板：

1. 按一下 **Adobe** 徽標，位於左上角。
1. 選擇 **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**。
1. 檢查 **[!UICONTROL Follow-up messages]** 的子菜單。

   ![](assets/message-center_follow-up-search.png)

只顯示後續消息。

>[!IMPORTANT]
>
>僅具有 [管理](../../administration/using/users-management.md#functional-administrators) 角色可以訪問和編輯事務性消息。

## 發送後續消息 {#sending-a-follow-up-message}

建立後續傳遞模板後，您可以在工作流中使用它來發送後續消息。

<!--You need to set up a workflow targeting the event corresponding to the transactional message that was already received.-->

1. 訪問市場營銷活動清單並建立新工作流。

   請參閱 [生成工作流](../../automating/using/building-a-workflow.md#creating-a-workflow)。

1. 拖放 **[!UICONTROL Scheduler]** 活動並將其開啟。 將執行頻率設定為每天一次。

   「Scheduler（計畫程式）」活動顯示在 [調度程式](../../automating/using/scheduler.md) 的子菜單。

1. 拖放 **[!UICONTROL Query]** 活動並將其開啟。

   「查詢」活動顯示在 [查詢](../../automating/using/query.md) 的子菜單。

1. 要在配置檔案資源以外的資源上運行查詢，請轉到活動的 **[!UICONTROL Properties]** ，然後按一下 **[!UICONTROL Resource]** 的子菜單。

   ![](assets/message-center_follow-up-query-properties.png)

   >[!NOTE]
   >
   >依預設，活動會預先設定為搜尋設定檔。

1. 選擇要目標的事件，以便僅訪問此事件中的資料。

   ![](assets/message-center_follow-up-query-resource.png)

1. 轉到活動 **[!UICONTROL Target]** ，然後拖放 **[!UICONTROL Delivery logs (logs)]** 元素。

   ![](assets/message-center_follow-up-delivery-logs.png)

   選擇 **[!UICONTROL Exists]** 以接收該電子郵件的所有客戶為目標。

   ![](assets/message-center_follow-up-delivery-logs-exists.png)

1. 移動 **[!UICONTROL Tracking logs (tracking)]** 從元件面板到工作區的元素並選擇 **[!UICONTROL Does not exist]** 瞄準所有未開啟電子郵件的客戶。

   ![](assets/message-center_follow-up-delivery-and-tracking-logs.png)

1. 拖放您所針對的事件(**購物車放棄** 在本示例中)將元件面板中的元件轉換為工作區。 然後定義一個規則，以針對三天前發送的所有消息。

   ![](assets/message-center_follow-up-created.png)

   這意味著在工作流執行三天前收到事務性消息且尚未開啟該消息的所有收件人都是目標收件人。

   按一下 **[!UICONTROL Confirm]** 的子菜單。

1. 拖放 **電子郵件傳遞** 活動。

   「E-mail delivery（電子郵件傳遞）」活動在 [電子郵件傳遞](../../automating/using/email-delivery.md) 的子菜單。

   ![](assets/message-center_follow-up-workflow.png)

   您還可以使用 [SMS傳遞](../../automating/using/sms-delivery.md) 或 [推送通知傳遞](../../automating/using/push-notification-delivery.md) 的子菜單。 在這種情況下，請確保選擇 **[!UICONTROL Mobile (SMS)]** 或 **[!UICONTROL Mobile application]** 建立事件配置時的通道。 請參閱[建立事件](../../channels/using/configuring-transactional-event.md#creating-an-event)。

1. 開啟 **電子郵件傳遞** 的子菜單。 在建立嚮導中，檢查 **[!UICONTROL Follow-up messages]** 框中，選擇發佈事件後建立的後續傳遞模板。

   ![](assets/message-center_follow-up-template.png)

1. 在後續消息內容中，可以通過添加個性化欄位來利用事件的內容。

   ![](assets/message-center_follow-up-content.png)

1. 通過選擇 **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]**。 請參閱 [個性化事務性消息](../../channels/using/editing-transactional-message.md#personalizing-a-transactional-message)。

   ![](assets/message-center_follow-up-personalization.png)

   這意味著您可以利用在首次發送活動時使用的相同內容（包括增強的資料）建立個性化友好提醒。

1. 保存活動並啟動工作流。

工作流啟動後，在三天前收到您的購物車放棄通知但沒有開啟的每個客戶都會收到基於相同資料的後續消息。

>[!NOTE]
>
>如果選擇了 **[!UICONTROL Profile]** 在建立事件配置時以維為目標，後續消息還將利用Adobe Campaign市場資料庫。 請參閱[設定檔交易式訊息](../../channels/using/editing-transactional-message.md#profile-transactional-message-specificities)。
