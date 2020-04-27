---
title: 管理類型
description: 瞭解如何使用類型。
page-status-flag: never-activated
uuid: a98ebc36-172d-4f46-b6ee-b2636a1007c9
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: working-with-typology-rules
discoiquuid: 2590d94c-51ef-4c0f-b1ec-c2837e94da40
context-tags: typology,overview;typologyRule,main;typologyRule,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: ba1fcca02ce9582d85e57bde815ccf3f551ac7a3

---


# 管理類型 {#managing-typologies}

## 關於類型 {#about-typologies}

類型是一組規則，允許您在發送郵件之前檢查郵件的有效性。 例如：消息內容不是空的，存在取消訂閱、排除重複內容等。

您可透過> **[!UICONTROL Administration]** > **[!UICONTROL Channels]** >選單存取 **[!UICONTROL Typologies]** 類型。 依預設，應用程式中會提供預設的排版。 您可以根據自己的需求建立自己的類型或修改現有的類型。

![](assets/typologies-list.png)

對於每種類型學，本 **[!UICONTROL Typology rules]** 節列出在使用含訊息的類型學時所執行的規則集。

![](assets/typology_typo-rule-list.png)

>[!NOTE]
>
>若要取得其中一種類型學規則的詳細資訊，請按兩下。 規則將以唯讀模式顯示。

## 建立類型 {#creating-a-typology}

若要建立新的類型學，請依照下列步驟進行：

1. 存取 **[!UICONTROL Administration]** > **[!UICONTROL Channels]** >功 **[!UICONTROL Typologies]** 能表。

1. 此時將顯示類型清單。 Click the **[!UICONTROL Create]** button.

   ![](assets/typologies-create.png)

1. 定義類 **[!UICONTROL Label]**&#x200B;型，然後按一 **[!UICONTROL Add an element]** 下按鈕以選取您要加入的類型學規則。 For more on typology rules, refer to [this section](../../sending/using/managing-typology-rules.md).

   ![](assets/typology_addrules.png)

   >[!NOTE]
   >
   >欄位 **[!UICONTROL IP affinity]** 可讓您根據您的設定來管理相關性。 它們在實例的配置檔案中定義。 如果您想使用相關性，請連絡您的管理員。

1. 按一 **[!UICONTROL Create]** 下以確認您的選擇。 您的類型學現在已可用於訊息。

## 對消息應用類型 {#applying-typologies-to-messages}

將分類與消息或消息模板關聯時，將執行包含在分類中的分類規則以檢查消息的有效性。

>[!NOTE]
>
>每個訊息或訊息範本只能指派單一類型。

若要將類型學連結至訊息，請遵循下列步驟：

1. 訪問消息屬性。 請注意，訊息範本可從「 >導 **[!UICONTROL Resources]** 覽功能表 **[!UICONTROL Templates]** 存取。

1. 在>區 **[!UICONTROL Advanced parameters]** 段 **[!UICONTROL Prearation]** 中，選取要連結至訊息的類型學。

   ![](assets/typology_message.png)

1. 按一下 **[!UICONTROL Confirm]**.

   選取的排版現在會連結至訊息。 系統將執行其所有相關的類型學規則，以檢查訊息有效性。
