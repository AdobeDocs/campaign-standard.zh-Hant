---
title: 定義電子郵件的主旨行和發件人
seo-title: 定義電子郵件的主旨行和發件人
description: 定義電子郵件的主旨行和發件人
seo-description: 瞭解如何在電子郵件設計工具中定義主旨行和電子郵件寄件者。
page-status-flag: 從未激活
uuid: 571ffc01-6e41-4501-9094-2f812b041a10
contentOwner: 紹維亞
products: SG_CAMPAIGN/STANDARD
audience: 設計
content-type: 參考
topic-tags: 編輯——電子郵件——內容
discoiquuid: 39b86fda-7766-4e5f-ab48-bcc536ab66b3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0cf4807fc3d617b0c5ca33705b6344d1f3994ab3

---


# 定義電子郵件的主旨行和發件人{#defining-the-subject-line-of-an-email}

留言主體是準備和發送留言的必備主題。

>[!NOTE]
>
>如果主旨行為空白，則訊息控制面板和電子郵件設計工具中會顯示警告。

To configure the email subject, go the  tab of the Email Designer home page (accessible through the home icon) and fill in the  section.**[!UICONTROL Properties]****[!UICONTROL Subject]**

**要定義電子郵件的主題行，請執行以下操作**:

1. Create an email.
1. Close homepage.
1. Go the  tab of the Email Designer home page (accessible through the home icon) and fill in the  section.**[!UICONTROL Properties]****[!UICONTROL Subject]**

![](assets/email_designer_subject.png)

You can also add personalization fields, content blocks and dynamic content to the subject line by clicking the corresponding icons.

**Related topics:**

* [Inserting a personalization field](../../designing/using/personalization.md#inserting-a-personalization-field)
* [Adding a content block](../../designing/using/personalization.md#adding-a-content-block)
* [Defining dynamic content in an email](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)

## Predictive subject line {#predictive-subject-line}

When editing an email, you can try out different subject lines and get an estimation of its open rate before you send it.

This feature is disabled by default. 當匯入第一個模型時，就會啟用它。 A model is the result of training data sets specific to a given industry. Models allow the system to predict the open rate of the email when a new subject line is submitted.

>[!NOTE]
>
>此功能適用於電子郵件訊息和僅包含英文內容的資料庫。 The trained model will be inconsistent and will lead to erroneous results if your instance contains emails in other languages. 只有在實例上已有模型可用時，才會顯示允許測試主題的選項。

**相關主題**

* [測試主題行](../../sending/using/testing-subject-line-email.md)

## 電子郵件傳送者 {#email-sender}

要定義將出現在所發送郵件標題中的發件人名稱，請轉至「電子郵件設計器」首頁的頁籤（可通過首頁表徵圖訪問）。 **[!UICONTROL Properties]**

![](assets/delivery_content_edition16.png)

* 該 **[!UICONTROL From: name]** 欄位允許您輸入發件人名稱。 預設情況下，預設的 **「發件人名稱** 」塊會自動輸入到欄位中。 Adobe Campaign是指電子郵件通道設定(從進階功能表， **[!UICONTROL Administration > Channels > Email > Email accounts]** 透過Adobe Campaign標誌)來指定此傳送者。

   您可以按一下「傳送者名稱」區塊，以變更 **傳送者名稱** 。 然後，欄位會變成可編輯，您可以輸入要使用的名稱。

   此欄位可以個人化。 若要這麼做，您可以按一下傳送者名稱下方的圖示，新增個人化欄位、內容區塊和動態內容。

* 無 **[!UICONTROL From: email address]** 法從此部分編輯欄位。 您可以透過從其控制面板編輯電子郵件的屬性來變更。 如需詳細資訊，請參 [閱電子郵件進階參數清單](../../administration/using/configuring-email-channel.md#advanced-parameters)。

>[!NOTE]
>
>標題參數不得為空。 發件人地址是允許發送電子郵件的強制性地址（RFC標準）。 Adobe Campaign會檢查輸入的電子郵件地址語法。

**相關主題：**

* [插入個人化欄位](../../designing/using/personalization.md#inserting-a-personalization-field)
* [新增內容區塊](../../designing/using/personalization.md#adding-a-content-block)
* [定義電子郵件中的動態內容](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)