---
title: 定義動態文字
description: 瞭解如何根據Adobe Campaign中定義的條件，以動態方式向使用者顯示不同的文字。
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

動態文字的定義方式與動態內容相同。 請參閱 [定義動態內容](../../designing/using/personalization.md#defining-dynamic-content-in-an-email) 區段。

>[!NOTE]
>
>對於SMS和推播，您只能定義動態文字。 您可以在登入頁面中定義動態內容和文字。 如果您想使用定義動態文字 [電子郵件設計工具](../../designing/using/designing-content-in-adobe-campaign.md)，請參閱 [定義電子郵件中的動態內容](../../designing/using/personalization.md#defining-dynamic-content-in-an-email).

請注意，替代字元組（未包含在Unicode字元集的基本多語言平面中的字元）無法以2位元組（16位元）儲存，且需要編碼為2個UTF-16字元。 這些字元包括一些CJK表意文字、大多數表情符號和一些語言。
<br>這些字元可能會在動態文字中造成某些不相容問題。 傳送訊息前，您必須執行強大的測試。


以下範例說明如何定義SMS訊息中的動態文字。

1. 在訊息或登入頁面內文中選取文字。
1. 按一下&#x200B;**[!UICONTROL Enable dynamic text]**。

   ![](assets/dynamic_text_sms_1.png)

   此 **[!UICONTROL Dynamic text]** 選項會顯示在浮動視窗中。 其設定方式與動態內容相同。

1. 選取變體。

   ![](assets/dynamic_text_sms_2.png)

1. 為此變體定義條件。

   ![](assets/dynamic_text_sms_4.png)

一旦為至少一個變體定義了條件，動態文字周圍就會顯示紫色框架。

![](assets/dynamic_text_sms_3.png)
