---
title: 定義直接郵件客群
description: 瞭解如何定義直接郵件傳遞的目標。
audience: channels
content-type: reference
topic-tags: direct-mail
context-tags: delivery,directMailContent,back
feature: Direct Mail
role: User
level: Intermediate
exl-id: ea167fec-d4df-4147-9dcd-33001d8a1c9b
TQID: https://experienceleague.adobe.com/iYqxhsfsz95pTh8V-sP-xwGSSQ39YyIov9OHHyfepDI
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 278
ht-degree: 96%

---

# 定義直接郵件客群{#defining-the-direct-mail-audience}

您可以在建立精靈中定義客群，或按一下傳遞控制面板的「**客群**」章節來定義客群。

![](assets/direct_mail_15.png)

## 定義主要目標 {#defining-the-main-target}

對於直接郵件，目標輪廓是將包含在摘取檔案中的輪廓，您將將會發送給直接郵件提供者。

對於每個目標輪廓，在擷取檔案中將新增一行。 每個收件者所包括的輪廓資訊量，會在「[定義擷取](../../channels/using/defining-the-direct-mail-content.md#defining-the-extraction)」畫面中定義。

>[!IMPORTANT]
>
>請確定您的輪廓包含郵寄地址，因為此資訊對於直接郵件提供者至關重要。 另請確保您已核取輪廓資訊中的 **[!UICONTROL Address specified]**&#x200B;方塊。 請參閱[建議](../../channels/using/about-direct-mail.md#recommendations)。

## 新增測試和補漏白設定檔 {#adding-test-and-trap-profiles}

新增測試輪廓，以便使用少量的輪廓來測試您的檔案。 它可讓您在準備實際檔案之前，快速建立檔案範例以測試與驗證結構。 請參閱[管理測試輪廓](../../audiences/using/managing-test-profiles.md)。

使用補漏白對於直接郵件至關重要。 允許您驗證直接郵件提供者是否確實傳送通訊，並且未將您的客戶端清單傳送給其他提供者。 請參閱「[使用補漏白](../../sending/using/using-traps.md)」。

對於直接郵件傳遞，補漏白會在摘取期間新增，並在輸出文件中進行混合。 依預設，它們會按輸出檔案的排序順序插入，但您可以選取在檔案的結尾或開頭插入它們。 定義客群時，請從 **[!UICONTROL Trap insertion mode]** 標籤中選取所需的選項。

![](assets/direct_mail_trap_insertion_mode.png)
