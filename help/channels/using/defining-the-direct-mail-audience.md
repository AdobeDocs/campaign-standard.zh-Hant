---
title: 定義直接郵件對象
description: 瞭解如何定義直接郵件傳遞的目標。
page-status-flag: never-activated
uuid: f843e368-5c07-4b53-8943-46f7bf45b62b
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: direct-mail
discoiquuid: f993d1b6-4b9a-4f95-81fc-60c126211bd2
context-tags: delivery,directMailContent,back
internal: n
snippet: y
translation-type: ht
source-git-commit: 07d68b5bf8d800ebd95919f491e98f1b7a015705
workflow-type: ht
source-wordcount: '278'
ht-degree: 100%

---


# 定義直接郵件對象{#defining-the-direct-mail-audience}

您可以在建立精靈中定義對象，或按一下傳遞控制面板的「**對象**」章節來定義對象。

![](assets/direct_mail_15.png)

## 定義主要目標 {#defining-the-main-target}

對於直接郵件，目標設定檔是將包含在摘取檔案中的設定檔，您將將會發送給直接郵件提供者。

對於每個目標設定檔，在擷取檔案中將新增一行。每個收件者所包括的設定檔資訊量，會在「[定義擷取](../../channels/using/defining-the-direct-mail-content.md#defining-the-extraction)」畫面中定義。

>[!CAUTION]
>
>請確定您的設定檔包含郵寄地址，因為此資訊對於直接郵件提供者至關重要。另請確保您已核取設定檔資訊中的 **[!UICONTROL Address specified]**&#x200B;方塊。請參閱[建議](../../channels/using/about-direct-mail.md#recommendations)。

## 新增測試與補漏白設定檔 {#adding-test-and-trap-profiles}

新增測試設定檔，以便使用少量的設定檔來測試您的檔案。它可讓您在準備實際檔案之前，快速建立檔案範例以測試與驗證結構。請參閱[管理測試設定檔](../../audiences/using/managing-test-profiles.md)。

使用補漏白對於直接郵件至關重要。允許您驗證直接郵件提供者是否確實傳送通訊，並且未將您的客戶端清單傳送給其他提供者。請參閱「[使用補漏白](../../sending/using/using-traps.md)」。

對於直接郵件傳遞，補漏白會在摘取期間新增，並在輸出文件中進行混合。依預設，它們會按輸出檔案的排序順序插入，但您可以選取在檔案的結尾或開頭插入它們。定義對象時，請從 **[!UICONTROL Trap insertion mode]** 標籤中選取所需的選項。

![](assets/direct_mail_trap_insertion_mode.png)
