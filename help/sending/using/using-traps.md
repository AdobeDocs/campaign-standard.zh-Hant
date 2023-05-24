---
title: 使用陷阱
description: 瞭解如何在消息中使用陷阱。
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
context-tags: seedMember,overview
feature: Seed Address
role: User
level: Intermediate
exl-id: 0482a946-35b1-426f-8505-42adcd1c3bbb
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '382'
ht-degree: 2%

---

# 使用陷阱 {#using-traps}

使用陷阱時，消息將發送到 [test配置檔案](../../audiences/using/managing-test-profiles.md) 就像它被發送到主目標一樣，作為確定客戶端檔案是否被欺騙性使用的一種方法。

陷阱最初是為直接郵寄而設計的。 它們允許您：

* 驗證您的直郵提供商是否確實在發送通信。
* 在與客戶相同的條件下同時接收郵件。
* 保留已發送郵件的準確副本。
* 檢查您的直接郵件提供商是否未濫用您的客戶端清單。 實際上，如果將任何其他通信發送到您的test配置檔案的地址，則您可能在您不知情的情況下使用了客戶檔案。 因此，test配置檔案的地址應僅用於此目的。

有關向直郵受眾添加陷阱的詳細資訊，請參見 [添加test和陷印配置檔案](../../channels/using/defining-the-direct-mail-audience.md#adding-test-and-trap-profiles)。

對於其他通信通道，您可以將陷印test配置檔案添加到主目標中，以便：

* 檢查您的郵件是否已成功發送。
* 獲取並保留您的郵件的準確副本。
* 跟蹤發送和接收時間。

要將test配置檔案用作陷阱，必須將其包含在消息的受眾中。

>[!NOTE]
>
>與用於的test配置檔案相反 [證明](../../sending/using/sending-proofs.md) 或 [電子郵件呈現](../../sending/using/email-rendering.md)，消息將同時發送到主目標和用作陷阱的test配置檔案。

定義郵件受眾時：

1. 從 **[!UICONTROL Test profiles]** 頁籤。 確保它 **[!UICONTROL Trap]** 作為預期用途。

   ![](assets/trap_select.png)

1. 消息內容準備好後，按一下 **[!UICONTROL Prepare]** 按鈕 請參閱 [準備發送](../../sending/using/preparing-the-send.md)。
   >[!NOTE]
   >
   >確保選擇了主目標。 否則，無法發送您的消息。

1. 按一下 **[!UICONTROL Confirm]** 按鈕。請參閱[確認傳送](../../sending/using/confirming-the-send.md)。

   ![](assets/trap_confirm.png)

消息將發送到主目標和test配置檔案。

在發送事務性消息時可以使用陷阱。 在這種情況下，test配置檔案將接收每個事件配置的一條消息。 有關事務性消息傳遞的詳細資訊，請參閱 [節](../../channels/using/getting-started-with-transactional-msg.md)。

>[!NOTE]
>
>當將test簡檔用作陷印時，對於消息中的任何富集欄位，從實際目標簡檔中隨機選取相應的附加資料並分配給陷印test簡檔。 有關濃縮的詳細資訊，請參見 [此示例](../../automating/using/enriching-profile-data-file.md)。
