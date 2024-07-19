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
source-git-commit: ee3ab5304e80ea098f7e172f6b3f4af4324e8eb4
workflow-type: tm+mt
source-wordcount: '458'
ht-degree: 2%

---

# 使用陷阱 {#using-traps}

使用補漏白時，訊息會傳送至[測試設定檔](../../audiences/using/managing-test-profiles.md)，就像傳送至主要目標一樣，以識別您的使用者端檔案是否遭到詐騙使用。

補漏白原本是為直接郵件傳遞而設計。 它們允許您：

* 確認您的直接郵件提供者確實在傳送通訊。
* 以與客戶相同的條件和時間接收郵件。
* 保留已傳送郵件的完整副本。
* 檢查您的使用者端清單是否未被直接郵件提供者不當使用。 事實上，如果將任何其他通訊傳送至測試設定檔的位址，則您的使用者端檔案可能在您不知道的情況下被使用。 這就是為什麼測試設定檔的位址只能用於此目的的原因。

如需將補漏白新增至直接郵件對象的詳細資訊，請參閱[新增測試與補漏白設定檔](../../channels/using/defining-the-direct-mail-audience.md#adding-test-and-trap-profiles)。

對於其他通訊通道，您可以將補漏白測試設定檔新增至主要目標，以便：

* 檢查您的訊息是否已成功傳送。
* 取得並保留訊息的精確副本。
* 追蹤其傳送及接收時間。

若要將測試設定檔作為補漏白使用，必須將其包含在訊息的對象中。

>[!NOTE]
>
>與用於[校樣](../../sending/using/sending-proofs.md)或[電子郵件轉譯](../../sending/using/email-rendering.md)的測試設定檔不同，訊息會同時傳送給主要目標及用作陷阱的測試設定檔。

定義訊息的對象時：

1. 從&#x200B;**[!UICONTROL Test profiles]**&#x200B;索引標籤中，選取測試設定檔。 確定它有&#x200B;**[!UICONTROL Trap]**&#x200B;作為預期用途。

   ![](assets/trap_select.png)

1. 訊息內容準備就緒後，請按一下&#x200B;**[!UICONTROL Prepare]**&#x200B;按鈕。 請參閱[準備傳送](../../sending/using/preparing-the-send.md)。
   >[!NOTE]
   >
   >請確定您已選取主要目標。 否則，無法傳送您的訊息。

1. 按一下 **[!UICONTROL Confirm]** 按鈕。請參閱[確認傳送](../../sending/using/confirming-the-send.md)。

   ![](assets/trap_confirm.png)

該訊息會傳送到主要目標和測試設定檔。

傳送交易式訊息時，您可以使用陷阱。 在此情況下，測試設定檔會在每個事件設定中收到一則訊息。 如需異動訊息的詳細資訊，請參閱此[區段](../../channels/using/getting-started-with-transactional-msg.md)。

>[!NOTE]
>
>將測試設定檔用作補漏白時，訊息中任何擴充的欄位將會從真正的目標設定檔中隨機選取其對應的額外資料，並將其指派給補漏白測試設定檔。 但是，請注意，如果由於在第一個訊息準備期間套用的型別規則而排除真正的目標設定檔，則傳送準備將會失敗。 發生此失敗是因為擴充欄位值無法取代補漏白設定檔。 因此，排除型別規則可能無法正確套用至真正的收件者。
>
>若要防止此情況，請避免在交易式型別中，將補漏白測試設定檔與篩選或疲勞規則同時使用。 進一步瞭解擴充。 如需擴充的詳細資訊，請參閱[此範例](../../automating/using/enriching-profile-data-file.md)。
