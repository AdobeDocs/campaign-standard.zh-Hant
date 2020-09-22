---
title: 使用陷阱
description: 瞭解如何在訊息中使用陷阱。
page-status-flag: never-activated
uuid: eb4d893b-3724-4b15-9312-1ec74784368d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
discoiquuid: 37320ec5-196c-4260-8156-98932da3e4a5
context-tags: seedMember,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: df70a2165c5d3a4b553565d9a91ec3f8da1b44aa
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 使用陷阱 {#using-traps}

使用陷阱時，訊息會像傳送至主要目標 [一樣傳送至測試描述檔](../../audiences/using/managing-test-profiles.md) ，做為識別用戶端檔案是否被詐用的方法。

陷阱最初是為直接郵寄而設計的。 它們允許您：

* 確認您的直接郵件提供商確實在發送通信。
* 在與客戶相同的條件下同時接收郵件。
* 保存已發送的郵件的確切副本。
* 檢查您的客戶清單是否未被您的直接郵件提供者濫用。 事實上，如果有任何其他通訊內容已傳送至您的測試設定檔位址，您的用戶端檔案可能已在您不知情的情況下使用。 這就是為什麼測試描述檔的位址僅能用於此目的。

有關向直效郵件對象添加陷阱的詳細資訊，請參 [閱添加測試和陷阱配置檔案](../../channels/using/defining-the-direct-mail-audience.md#adding-test-and-trap-profiles)。

對於其他通信通道，您可以將陷阱測試配置檔案添加到主目標中，以便：

* 檢查您的訊息是否已成功傳送。
* 取得並保留您的訊息。
* 追蹤傳送和接收的時間。

若要將測試描述檔當做陷阱，必須將其包含在訊息的觀眾中。

>[!NOTE]
>
>與用於校樣或電子郵 [件轉譯的測試描述檔](../../sending/using/sending-proofs.md)[](../../sending/using/email-rendering.md)，訊息會同時傳送至主要目標和用作陷阱的測試描述檔。

定義訊息的對象時：

1. 從標籤 **[!UICONTROL Test profiles]** 中，選取測試描述檔。 請確定它已 **[!UICONTROL Trap]** 達到預期用途。

   ![](assets/trap_select.png)

1. 在訊息內容準備就緒後，按一下 **[!UICONTROL Prepare]** 按鈕。 See [Preparing the send](../../sending/using/preparing-the-send.md).
   >[!NOTE]
   >
   >請確定您已選取主要目標。 否則，無法傳送您的訊息。

1. 按一下 **[!UICONTROL Confirm]** 按鈕。請參閱[確認傳送](../../sending/using/confirming-the-send.md)。

   ![](assets/trap_confirm.png)

訊息會傳送至主要目標和測試設定檔。

在發送事務性消息時可使用陷阱。 在這種情況下，測試設定檔會針對每個事件設定收到一則訊息。 For more on transactional messaging, see this [section](../../channels/using/getting-started-with-transactional-msg.md).

>[!NOTE]
>
>當將測試配置檔案用作陷印時，對於消息中的任何富集欄位，從實際目標配置檔案中隨機選擇相應的附加資料並分配給陷印測試配置檔案。 有關擴充的詳細資訊，請參 [閱此範例](../../automating/using/enriching-profile-data-file.md)。
