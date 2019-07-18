---
title: 定義可見度條件
seo-title: 定義可見度條件
description: 定義可見度條件
seo-description: 讓網頁元素只有在符合特定條件時才會顯示。
page-status-flag: 從未啓動
uuid: 22005ba-ef09-4790-b2 f0-30ed74 cfu32 d
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: design
content-type: reference
topic-tags: defining-conditional-content
discoiquuid: c12125a7-a1 cf-4bc1-a138-57ff74974024
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Defining a visibility condition{#defining-a-visibility-condition}

您可以在任何元素上指定可見度條件。只有在條件受到尊重時才會顯示。

To add a visibility condition, select a block and enter the condition to be respected in the **[!UICONTROL Visibility condition]** field of its settings.

![](assets/delivery_content_5.png)

此選項僅適用於下列元素：地址、BOCBOTION、CENTTER、DILR、DIV、DL、ELDECHET、FORM、H1、H2、H3、H4、H5、H6、NOSCRIPT、OL、P、PRE、UL、TR、TD.

The expression editor is presented in the [Advanced expression editing](../../automating/using/editing-queries.md#about-query-editor) section.

These conditions adopt the XTK expression syntax (e.g. **context.profile.email !=''** or **context.profile.status='0'**). 依預設會顯示所有欄位。

>[!NOTE]
>
>無法針對已包含動態內容的子元素或已組成動態內容的區塊，定義條件。無法編輯非可見動態區塊(例如下拉式清單)。

