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
source-git-commit: b0cf437ec97153b53bd4502171b24286abb25731

---


# Defining the direct mail audience{#defining-the-direct-mail-audience}

You can either define the audience in the creation wizard or by clicking on the **Audience** section of the delivery dashboard.

![](assets/direct_mail_15.png)

## Defining the main target {#defining-the-main-target}

對於直接郵件，目標設定檔會包含在要傳送給直接郵件提供者的擷取檔案中。

對於每個目標設定檔，擷取檔案中會新增新行。The amount of profile information that will be included for each recipient is defined in the [Defining the extraction](../../channels/using/defining-the-direct-mail-content.md#defining-the-extraction) screen.

>[!CAUTION]
>
>請確定您的個人檔案包含郵寄地址，因為此資訊對直接郵件提供者而言是不可或缺的資訊。Also make sure you have checked the **[!UICONTROL Address specified]** box in your profiles' information. See [Recommendations](../../channels/using/about-direct-mail.md#recommendations).

## Adding test and trap profiles {#adding-test-and-trap-profiles}

新增測試設定檔，讓您可以使用少量描述檔來測試檔案。它可讓您快速建立檔案範例，在準備實際檔案之前測試並驗證結構。Refer to [Managing test profiles and sending proofs](../../sending/using/managing-test-profiles-and-sending-proofs.md).

使用補漏白是直效郵件傳送的必備工具。例如，它們允許您驗證直接郵件提供者是否確實傳送了通訊資料，而且他們並未傳送您的客戶清單給其他供應商。

對於直接郵件傳送，會在擷取期間新增補漏白，並在輸出文件中混合。By default, they are inserted in the sorting order of the output file, but you can choose to insert them at the end or the beginning of the file ( **[!UICONTROL Trap insertion mode]** tab).
