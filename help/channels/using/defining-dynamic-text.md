---
solution: Campaign Standard
product: campaign
title: 定義動態文字
description: 瞭解如何根據Adobe Campaign中定義的條件，動態地向使用者顯示不同的文字。
audience: designing
content-type: reference
topic-tags: defining-conditional-content
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '213'
ht-degree: 3%

---


# 定義動態文字{#defining-dynamic-text}

動態文字的定義方式與動態內容相同。 請參閱「定 [義動態內容](../../designing/using/personalization.md#defining-dynamic-content-in-an-email) 」一節。

>[!NOTE]
>
>對於SMS和推播，您只能定義動態文字。 您可以在登陸頁面中定義動態內容和文字。 如果您想要使用「電子郵件設計器」定義 [動態文本](../../designing/using/designing-content-in-adobe-campaign.md)，請 [參閱定義電子郵件中的動態內容](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)。

請注意，替代對（未包含在Unicode字元集的「基本多語言平面」中的字元）無法儲存為2個位元組（16位元），而且需要編碼為2個UTF-16字元。 這些字元包括一些CJK表意文字、大多數表情符號和一些語言。
<br>這些字元可能會在動態文字中造成一些不相容的問題。 傳送訊息前，您必須先執行強式測試。


以下範例說明如何定義SMS訊息中的動態文字。

1. 在訊息或著陸頁面的正文中選取文字。
1. 按一下 **[!UICONTROL Enable dynamic text]**。

   ![](assets/dynamic_text_sms_1.png)

   選項 **[!UICONTROL Dynamic text]** 會顯示在浮動視窗中。 其設定方式與動態內容相同。

1. 選擇變型。

   ![](assets/dynamic_text_sms_2.png)

1. 定義此變體的條件。

   ![](assets/dynamic_text_sms_4.png)

一旦為至少一個變體定義了條件，動態文字周圍就會顯示紫色框架。

![](assets/dynamic_text_sms_3.png)
