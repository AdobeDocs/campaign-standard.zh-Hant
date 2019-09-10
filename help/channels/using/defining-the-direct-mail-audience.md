---
title: 定義直接郵件對象
seo-title: 定義直接郵件對象
description: 定義直接郵件對象
seo-description: 瞭解如何定義直接郵件傳遞目標。
page-status-flag: 從未啓動
uuid: f843e368-5c07-4b53-8943-46f7bf45b62b
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 頻道
content-type: reference
topic-tags: 直接郵件
discoiquuid: f993d1b6-4b9a-4f95-81fc-60c126211bd2
context-tags: delivery，DirectMailContent，back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 27447db9ee0dd387c39976c7bd4e157a4b7899b8

---


# 定義直接郵件對象{#defining-the-direct-mail-audience}

您可以在建立精靈中定義對象，或按一下傳送控制面板的 **「對象** 」區段。

![](assets/direct_mail_15.png)

## 定義主要目標 {#defining-the-main-target}

對於直接郵件，目標設定檔會包含在要傳送給直接郵件提供者的擷取檔案中。

對於每個目標設定檔，擷取檔案中會新增新行。每個收件者將會在 [「定義」擷取](../../channels/using/defining-the-direct-mail-content.md#defining-the-extraction) 畫面中定義要包含的描述檔資訊量。

>[!CAUTION]
>
>請確定您的個人檔案包含郵寄地址，因為此資訊對直接郵件提供者而言是不可或缺的資訊。此外，請確定您已勾選個人檔案資訊中的 **[!UICONTROL Address specified]** 方塊。請參閱 [Recommendations](../../channels/using/about-direct-mail.md#recommendations)。

## 新增測試和補漏白描述檔 {#adding-test-and-trap-profiles}

新增測試設定檔，讓您可以使用少量描述檔來測試檔案。它可讓您快速建立檔案範例，在準備實際檔案之前測試並驗證結構。請參閱 [管理測試設定檔和傳送校樣](../../sending/using/managing-test-profiles-and-sending-proofs.md)。

使用補漏白是直效郵件傳送的必備工具。它們可讓您驗證直接郵件提供者是否確實傳送了通訊資料，而且他們並未傳送您的客戶清單給其他供應商。請參閱 [使用補漏白](../../sending/using/managing-test-profiles-and-sending-proofs.md#using-traps)。

對於直接郵件傳送，會在擷取期間新增補漏白，並在輸出文件中混合。依預設，它們會插入輸出檔案的排序順序，但您可以選擇將它們插入檔案的結尾或開頭。定義對象時，從 **[!UICONTROL Trap insertion mode]** 標籤中選擇所要的選項。

![](assets/direct_mail_trap_insertion_mode.png)
