---
title: 在訊息中選取對象
seo-title: 在訊息中選取對象
description: 在訊息中選取對象
seo-description: 「逐步程序以選擇電子郵件的對象：主要目標人口與測試設定檔」。
page-status-flag: 從未啓動
uuid: 7d8f8446-f2 e0-49c1-83f6-9667b29 bc228
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 受眾
content-type: reference
topic-tags: 管理觀眾
discoiquuid: 158da6ff-8899-4e7b-b925-8a42 c3 de46 a
context-tags: Delivery Creation，wizard；傳送，觀眾，返回
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c9e33f51ab497b8bd111dfc307670f2fde5d804f

---


# Selecting an audience in a message{#selecting-an-audience-in-a-message}

Adobe Campaign可讓您在訊息對象中設定數個描述檔類型。

透過建立精靈或訊息控制面板(如果訊息已建立)建立訊息時，可以定義觀眾。

>[!NOTE]
>
>如果觀眾已內建在工作流程中並使用其他資料豐富，您將無法使用這些資料個人化獨立傳送。它們只能用於工作流程中執行的傳送。

1. 從控制面板前往觀眾區塊開始。

   ![](assets/delivery_audience_definition_1.png)

   畫面以定義觀眾接著開啓。它有兩個標籤可讓您個別定義將接收訊息的每一類型對象：

   * Target
   * 測試設定檔
   ![](assets/delivery_audience_definition_2.png)

1. Define the main **[!UICONTROL Target]** of the email. 這是電子郵件的一般目標對象。

   The target is defined in the **[!UICONTROL Target]** tab and is made up of identified profiles from your database.

   You can establish your main target using the [query editor](../../automating/using/editing-queries.md#creating-queries) functionalities.

   In this tab, the **[!UICONTROL Shortcuts]** palette only contains predefined filters and the audiences that have been defined in the identified profiles. **[!UICONTROL Explorer]** 此標籤可讓您存取其他設定。

   因此，您可以重新使用並結合現有對象、套用其他篩選器至他們等。

1. Define the **[!UICONTROL Test profiles]** you want to use for the email. 測試設定檔將會收到您在傳送電子郵件至主要目標之前先傳送的校樣。

   For more information on configuring test profiles, refer to the [Test profiles](../../sending/using/managing-test-profiles-and-sending-proofs.md) section.

接著會更新觀眾區塊，並顯示已針對該電子郵件選取目標和測試設定檔。

![](assets/delivery_audience_definition_3.png)

