---
title: 使用陷阱
description: 瞭解如何在訊息中使用陷阱。
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

使用補漏白時，訊息會傳送至 [測試設定檔](../../audiences/using/managing-test-profiles.md) 就像傳送至主要目標一樣，用來識別使用者端檔案是否遭到詐騙使用。

補漏白原本是為直接郵件傳遞而設計。 它們允許您：

* 確認您的直接郵件提供者確實在傳送通訊。
* 以與客戶相同的條件和時間接收郵件。
* 保留已傳送郵件的完整副本。
* 檢查您的使用者端清單是否未被直接郵件提供者不當使用。 事實上，如果將任何其他通訊傳送至測試設定檔的位址，則您的使用者端檔案可能在您不知道的情況下被使用。 這就是為什麼測試設定檔的位址只能用於此目的的原因。

如需將補漏白新增至直接郵件對象的詳細資訊，請參閱 [新增測試和補漏白設定檔](../../channels/using/defining-the-direct-mail-audience.md#adding-test-and-trap-profiles).

對於其他通訊通道，您可以將補漏白測試設定檔新增至主要目標，以便：

* 檢查您的訊息是否已成功傳送。
* 取得並保留訊息的精確副本。
* 追蹤其傳送及接收時間。

若要將測試設定檔作為補漏白使用，必須將其包含在訊息的對象中。

>[!NOTE]
>
>與用來測試設定檔不同 [校樣](../../sending/using/sending-proofs.md) 或 [電子郵件呈現](../../sending/using/email-rendering.md)，訊息會同時傳送至主要目標及用來作為補漏白的測試設定檔。

定義訊息的對象時：

1. 從 **[!UICONTROL Test profiles]** 標籤，選取測試設定檔。 確定它具有 **[!UICONTROL Trap]** 作為預期用途。

   ![](assets/trap_select.png)

1. 訊息內容準備就緒後，請按一下 **[!UICONTROL Prepare]** 按鈕。 另請參閱 [準備傳送](../../sending/using/preparing-the-send.md).
   >[!NOTE]
   >
   >請確定您已選取主要目標。 否則，無法傳送您的訊息。

1. 按一下 **[!UICONTROL Confirm]** 按鈕。請參閱[確認傳送](../../sending/using/confirming-the-send.md)。

   ![](assets/trap_confirm.png)

該訊息會傳送到主要目標和測試設定檔。

傳送交易式訊息時，您可以使用陷阱。 在此情況下，測試設定檔會在每個事件設定中收到一則訊息。 有關交易式訊息的詳細資訊，請參閱此 [區段](../../channels/using/getting-started-with-transactional-msg.md).

>[!NOTE]
>
>使用測試設定檔作為補漏白時，對於訊息中任何擴充的欄位，會從真正的目標設定檔中隨機擷取對應的額外資料，並將其指派給補漏白測試設定檔。 如需擴充的詳細資訊，請參閱 [此範例](../../automating/using/enriching-profile-data-file.md).
