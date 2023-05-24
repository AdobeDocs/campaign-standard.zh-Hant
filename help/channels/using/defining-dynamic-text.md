---
title: 定義動態文字
description: 瞭解如何根據Adobe Campaign定義的條件動態地向用戶顯示不同的文本。
audience: designing
content-type: reference
topic-tags: defining-conditional-content
feature: SMS
role: User
level: Beginner
exl-id: 649e3428-a3bf-470f-923c-04d9a57a208f
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '213'
ht-degree: 3%

---

# 定義動態文字{#defining-dynamic-text}

動態文本的定義方式與動態內容的定義方式相同。 請參閱 [定義動態內容](../../designing/using/personalization.md#defining-dynamic-content-in-an-email) 的子菜單。

>[!NOTE]
>
>對於SMS和推送，您只能定義動態文本。 您可以在登錄頁中定義動態內容和文本。 如果要使用 [電子郵件設計器](../../designing/using/designing-content-in-adobe-campaign.md)，請參閱 [在電子郵件中定義動態內容](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)。

請注意，代理對（未包含在Unicode字元集的基本多語言平面中的字元）不能以2個位元組（16位）儲存，需要編碼為2個UTF-16字元。 這些字元包括一些中日韓表意文字、大多數表情符號和一些語言。
<br>這些字元可能會在動態文本中引起一些不相容問題。 在發送消息之前，需要執行強test。


以下示例說明如何在SMS消息中定義動態文本。

1. 在消息或登錄頁的正文中選擇文本。
1. 按一下&#x200B;**[!UICONTROL Enable dynamic text]**。

   ![](assets/dynamic_text_sms_1.png)

   的 **[!UICONTROL Dynamic text]** 選項。 它的配置方式與動態內容的配置方式相同。

1. 選擇變型。

   ![](assets/dynamic_text_sms_2.png)

1. 定義此變型的條件。

   ![](assets/dynamic_text_sms_4.png)

一旦為至少一個變型定義了條件，就會在動態文本週圍顯示紫色框架。

![](assets/dynamic_text_sms_3.png)
