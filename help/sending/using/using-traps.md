---
title: 使用陷阱
description: 了解如何在訊息中使用陷阱。
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

使用陷阱時，會像將消息發送到主目標一樣將消息發送到[測試配置檔案](../../audiences/using/managing-test-profiles.md)，作為標識客戶端檔案是否被欺騙使用的手段。

陷阱最初設計用於直接郵件傳遞。 它們可讓您：

* 確認直接郵件提供者確實傳送通訊。
* 在與客戶相同的條件下，同時接收郵件。
* 保留已發送郵件的確切副本。
* 檢查您的直接郵件提供者是否未濫用您的用戶端清單。 事實上，如果將任何其他通訊傳送至您的測試設定檔的位址，您的用戶端檔案可能已在您不知情的情況下使用。 這就是為什麼測試設定檔的位址僅應用於此目的。

有關將補漏白添加到直接郵件對象的詳細資訊，請參閱[添加測試和補漏白配置檔案](../../channels/using/defining-the-direct-mail-audience.md#adding-test-and-trap-profiles)。

對於其他通信通道，您可以將陷阱測試配置檔案添加到主目標，以便：

* 檢查您的郵件是否已成功發送。
* 取得並保留您的訊息的完整副本。
* 追蹤傳送和接收的時間。

若要使用測試設定檔作為補漏白，必須將其納入訊息的對象中。

>[!NOTE]
>
>與用於[校樣](../../sending/using/sending-proofs.md)或[電子郵件呈現](../../sending/using/email-rendering.md)的測試設定檔相反，訊息會同時傳送至主要目標以及用作陷阱的測試設定檔。

定義訊息的對象時：

1. 從&#x200B;**[!UICONTROL Test profiles]**&#x200B;索引標籤中，選取測試設定檔。 請確定其預期用途為&#x200B;**[!UICONTROL Trap]**。

   ![](assets/trap_select.png)

1. 訊息內容準備就緒後，按一下&#x200B;**[!UICONTROL Prepare]**&#x200B;按鈕。 請參閱[準備傳送](../../sending/using/preparing-the-send.md)。
   >[!NOTE]
   >
   >請確定您選取了主要目標。 否則，無法傳送您的訊息。

1. 按一下 **[!UICONTROL Confirm]** 按鈕。請參閱[確認傳送](../../sending/using/confirming-the-send.md)。

   ![](assets/trap_confirm.png)

訊息會傳送至主要目標和測試設定檔。

您可以在傳送交易式訊息時使用陷阱。 在此情況下，測試設定檔會收到每個事件設定一則訊息。 如需交易式訊息的詳細資訊，請參閱此[區段](../../channels/using/getting-started-with-transactional-msg.md)。

>[!NOTE]
>
>將測試設定檔當作補漏白時，對於訊息中的任何擴充欄位，會從實際目標設定檔隨機挑選對應的額外資料，並指派給補漏白測試設定檔。 如需擴充的詳細資訊，請參閱[此範例](../../automating/using/enriching-profile-data-file.md)。
