---
solution: Campaign Standard
product: campaign
title: 定義電子郵件的主旨行和發件人
description: 瞭解如何在電子郵件設計工具中定義主旨行和電子郵件寄件者。
audience: designing
content-type: reference
topic-tags: editing-email-content
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 2%

---


# 定義電子郵件的主旨行和發件人{#defining-the-subject-line-of-an-email}

## Defining the subject line of an email {#subject-line}

留言主體是準備和發送留言的必備主題。

>[!NOTE]
>
>如果主旨行為空白，則訊息控制面板和電子郵件設計工具中會顯示警告。

1. 建立電子郵件.
1. 轉到「電 **[!UICONTROL Properties]** 子郵件設計器」首頁的頁籤（可通過首頁表徵圖訪問）。
1. Fill in the **[!UICONTROL Subject]** section.

   ![](assets/email_designer_subject.png)

1. 您也可以按一下對應的圖示，將個人化欄位、內容區塊和動態內容新增至主題行。 For more on this, see [Personalization](../../designing/using/personalization.md).
1. 您可以嘗試不同的主題行，以便在傳送電子郵件之前，先估計您的電子郵件開放率。 如需詳細資訊，請參 [閱測試電子郵件的主旨行](../../sending/using/testing-subject-line-email.md)。

## 定義電子郵件的電子郵件發件人 {#email-sender}

要定義將出現在所發送郵件標題中的發件人名稱，請轉至「電子郵件設計器」首頁的頁籤（可通過首頁表徵圖訪問）。 **[!UICONTROL Properties]**

![](assets/delivery_content_edition16.png)

* 該 **[!UICONTROL From: name]** 欄位允許您輸入發件人名稱。 預設情況下，預設的 **「發件人名稱** 」塊會自動輸入到欄位中。 預設寄件者電子郵件地址和寄件者名稱是透過進階功 **[!UICONTROL Brands]** 能表下的Adobe Campaign標誌加以定義 **[!UICONTROL Administration > Instance settings > Brand configuration]** 。

   您可以按一下「傳送者名稱」區塊，以變更 **傳送者名稱** 。 然後，欄位會變成可編輯，您可以輸入要使用的名稱。

   此欄位可以個人化。 若要這麼做，您可以按一下傳送者名稱下方的圖示，新增個人化欄位、內容區塊和動態內容。 For more on this, see [Personalization](../../designing/using/personalization.md).

* 無 **[!UICONTROL From: email address]** 法從此部分編輯欄位。 您可以透過從其控制面板編輯電子郵件的屬性來變更。 如需詳細資訊，請參 [閱電子郵件進階參數清單](../../administration/using/configuring-email-channel.md#advanced-parameters)。

>[!NOTE]
>
>標題參數不得為空。 發件人地址是允許發送電子郵件的強制性地址（RFC標準）。 Adobe Campaign會檢查輸入的電子郵件地址語法。

**相關主題：**

* [插入個人化欄位](../../designing/using/personalization.md#inserting-a-personalization-field)
* [新增內容區塊](../../designing/using/personalization.md#adding-a-content-block)
* [定義電子郵件中的動態內容](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)
