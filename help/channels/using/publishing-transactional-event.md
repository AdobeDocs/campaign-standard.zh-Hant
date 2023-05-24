---
title: 發佈異動事件
description: 瞭解如何預覽、發佈、取消發佈和刪除事務性事件配置。
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

一次 [配置](../../channels/using/configuring-transactional-event.md) 已完成，該事件已準備好發佈。 下面介紹了預覽、發佈、取消發佈和刪除事件的步驟。

>[!IMPORTANT]
>
>僅 [功能管理員](../../administration/using/users-management.md#functional-administrators) <!--being part of the **[!UICONTROL All]** [organizational unit](../../administration/using/organizational-units.md) -->具有發佈事件配置的適當權限。

中提供了一個圖表，說明了整個事務性消息發佈過程，包括發佈和取消發佈事件配置 [此部分](../../channels/using/publishing-transactional-message.md)。

發佈完成後：
* 自動建立相應的事務消息。 請參閱 [編輯事務性消息](../../channels/using/editing-transactional-message.md)。
* 將部署網站開發人員使用的API，現在可以發送事務事件。 請參閱 [整合事件觸發](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger)。

## 預覽和發佈事件 {#previewing-and-publishing-the-event}

在能夠使用事件之前，必須預覽並發佈它。

1. 按一下 **[!UICONTROL API preview]** 按鈕，查看網站開發人員在發佈REST API之前將使用的模擬。

   發佈事件後，此按鈕還允許您查看生產中API的預覽。 請參閱 [整合事件觸發](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger)。

   ![](assets/message-center_api_preview.png)

   >[!NOTE]
   >
   >REST API根據所選通道和所選目標維度而改變。 有關各種配置的詳細資訊，請參閱 [此部分](../../channels/using/configuring-transactional-event.md#transactional-event-specific-configurations)。

1. 按一下 **[!UICONTROL Publish]** 的子菜單。

   ![](assets/message-center_pub.png)

   將部署網站開發人員使用的API，現在可以發送事務事件。

1. 您可以在相應頁籤中查看發佈日誌。

   ![](assets/message-center_logs.png)

   >[!IMPORTANT]
   >
   >每次修改事件時，必須按一下 **[!UICONTROL Publish]** 生成網站開發人員將使用的更新REST API。

   事件發佈後， [事務性消息](../../channels/using/editing-transactional-message.md) 將自動建立連結到新事件。

1. 您可以通過位於左側區域的連結直接訪問此事務性消息。

   ![](assets/message-center_messagegeneration.png)

   >[!NOTE]
   >
   >要使事件觸發發送事務性消息，必須修改並發佈剛建立的消息。 請參閱 [編輯](../../channels/using/editing-transactional-message.md) 和 [發佈事務性消息](../../channels/using/publishing-transactional-message.md) 的下界。 你也得 [整合此觸發事件](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger) 你的網站。

1. 一旦Adobe Campaign開始接收與此事件配置相關的事件，您可以按一下 **[!UICONTROL Latest transactional events]** 連結 **[!UICONTROL History]** 的子菜單。

![](assets/message-center_latest-events.png)

事件（JSON格式）從最新到最舊列出。 此清單允許您檢查資料（如內容或事件狀態），以便進行控制和調試。

## 取消發佈事件 {#unpublishing-an-event}

的 **[!UICONTROL Unpublish]** 按鈕可取消事件的發佈，該事件從REST API中刪除與先前建立的事件對應的資源。

現在，即使事件是透過網站觸發，也不會再傳送相對應的訊息，也不會將之儲存在資料庫中。

![](assets/message-center_unpublish.png)

>[!NOTE]
>
>如果已發佈相應的事務性消息，事務性消息發佈也將被取消。 請參閱 [取消發佈事務性消息](../../channels/using/publishing-transactional-message.md#unpublishing-a-transactional-message)。

按一下 **[!UICONTROL Publish]** 按鈕以生成新的REST API。

<!--## Transactional messaging publication process {#transactional-messaging-pub-process}

The chart below illustrates the transactional messaging publication process.

![](assets/message-center_pub-process.png)

For more on publishing, pausing and unpublishing a transactional message, see [this section](../../channels/using/publishing-transactional-message.md).-->

## 刪除事件 {#deleting-an-event}

一旦某個事件被取消發佈，或某個事件尚未發佈，您就可以將其從事件配置清單中刪除。 操作步驟：

1. 按一下 **Adobe** 徽標，在左上角，然後選擇 **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Event configuration]**。
1. 將滑鼠懸停在所選事件配置上，然後選擇 **[!UICONTROL Delete element]** 按鈕

   ![](assets/message-center_delete-button.png)

   >[!NOTE]
   >
   >確保事件配置具有 **[!UICONTROL Draft]** 狀態，否則將無法刪除它。 的 **[!UICONTROL Draft]** 狀態適用於尚未發佈或已發佈的事件 [未發佈](#unpublishing-an-event)。

1. 按一下 **[!UICONTROL Confirm]** 按鈕。

   ![](assets/message-center_delete-confirm.png)

>[!IMPORTANT]
>
>刪除已發佈且已使用的事件配置也會刪除相應的事務性消息及其發送和跟蹤日誌。
