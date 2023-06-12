---
title: 發佈異動事件
description: 瞭解如何預覽、發佈、取消發佈和刪除交易式事件設定。
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
feature: Transactional Messaging
role: User
level: Intermediate
exl-id: 6bcd8dcd-d710-4ca3-937d-bf4339f36069
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '607'
ht-degree: 6%

---

# 發佈異動事件 {#publishing-transactional-event}

一次 [設定](../../channels/using/configuring-transactional-event.md) 完成，事件已準備好發佈。 預覽、發佈、取消發佈和刪除事件的步驟如下所述。

>[!IMPORTANT]
>
>僅限 [功能管理員](../../administration/using/users-management.md#functional-administrators) <!--being part of the **[!UICONTROL All]** [organizational unit](../../administration/using/organizational-units.md) -->具有發佈事件設定的適當許可權。

說明整個交易式訊息發佈程式（包括發佈和取消發佈事件設定）的圖表可在以下網址取得： [本節](../../channels/using/publishing-transactional-message.md).

發佈完成後：
* 系統會自動建立對應的交易式訊息。 另請參閱 [編輯異動訊息](../../channels/using/editing-transactional-message.md).
* 將部署您的網站開發人員使用的API，現在可以傳送交易式事件。 另請參閱 [整合事件觸發](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger).

## 預覽和發佈事件 {#previewing-and-publishing-the-event}

您必須先預覽並發佈事件，才能加以使用。

1. 按一下 **[!UICONTROL API preview]** 按鈕來檢視您的網站開發人員在發佈之前使用的REST API模擬。

   發佈事件後，此按鈕也可讓您在生產環境中檢視API的預覽。 另請參閱 [整合事件觸發](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger).

   ![](assets/message-center_api_preview.png)

   >[!NOTE]
   >
   >REST API會根據選取的管道和選取的目標維度而有所不同。 如需各種設定的詳細資訊，請參閱 [本節](../../channels/using/configuring-transactional-event.md#transactional-event-specific-configurations).

1. 按一下 **[!UICONTROL Publish]** 以開始發佈。

   ![](assets/message-center_pub.png)

   將部署您的網站開發人員使用的API，現在可以傳送交易式事件。

1. 您可以在對應的索引標籤中檢視出版物記錄。

   ![](assets/message-center_logs.png)

   >[!IMPORTANT]
   >
   >每次修改事件時，都必須按一下 **[!UICONTROL Publish]** 再次更新，以產生您的網站開發人員使用的更新REST API。

   發佈事件後， [異動訊息](../../channels/using/editing-transactional-message.md) 系統會自動建立連結至新事件的資訊。

1. 您可以透過左側區域中的連結直接存取此交易式訊息。

   ![](assets/message-center_messagegeneration.png)

   >[!NOTE]
   >
   >為了讓事件觸發傳送交易式訊息，您必須修改並發佈剛建立的訊息。 另請參閱 [編輯](../../channels/using/editing-transactional-message.md) 和 [發佈交易式訊息](../../channels/using/publishing-transactional-message.md) 區段。 您也必須 [整合此觸發程式事件](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger) 至您的網站。

1. 在Adobe Campaign開始接收與此事件設定相關的事件後，您可以按一下 **[!UICONTROL Latest transactional events]** 連結在 **[!UICONTROL History]** 區段，以存取您的協力廠商服務傳送並由Adobe Campaign處理的最新事件。

![](assets/message-center_latest-events.png)

事件（JSON格式）會從最近到最舊列出。 此清單可讓您檢查內容或事件狀態等資料，以用於控制和偵錯。

## 取消發佈事件 {#unpublishing-an-event}

此 **[!UICONTROL Unpublish]** 按鈕可讓您取消事件的發佈，這會從REST API中刪除與您先前建立之事件對應的資源。

現在，即使事件是透過網站觸發，也不會再傳送相對應的訊息，也不會將之儲存在資料庫中。

![](assets/message-center_unpublish.png)

>[!NOTE]
>
>如果您已發佈對應的交易式訊息，交易式訊息發佈也會被取消。 另請參閱 [取消發佈交易式訊息](../../channels/using/publishing-transactional-message.md#unpublishing-a-transactional-message).

按一下 **[!UICONTROL Publish]** 按鈕來產生新的REST API。

<!--## Transactional messaging publication process {#transactional-messaging-pub-process}

The chart below illustrates the transactional messaging publication process.

![](assets/message-center_pub-process.png)

For more on publishing, pausing and unpublishing a transactional message, see [this section](../../channels/using/publishing-transactional-message.md).-->

## 刪除事件 {#deleting-an-event}

取消發佈事件後，或尚未發佈事件時，您可以從事件設定清單中刪除該事件。 操作步驟：

1. 按一下 **Adobe** 標誌，在左上角，然後選取 **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Event configuration]**.
1. 將滑鼠停留在您選擇的事件設定上，並選取 **[!UICONTROL Delete element]** 按鈕。

   ![](assets/message-center_delete-button.png)

   >[!NOTE]
   >
   >確定事件設定具有 **[!UICONTROL Draft]** 狀態，否則您將無法刪除它。 此 **[!UICONTROL Draft]** 狀態適用於尚未發佈或已經發佈的事件 [已取消發佈](#unpublishing-an-event).

1. 按一下 **[!UICONTROL Confirm]** 按鈕。

   ![](assets/message-center_delete-confirm.png)

>[!IMPORTANT]
>
>刪除已發佈且已使用的事件設定也會刪除對應的交易式訊息及其傳送和追蹤記錄。
