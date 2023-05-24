---
title: 定義電子郵件的主題行和發件人
description: 瞭解如何在電子郵件設計器中定義電子郵件的主題行和發件人。
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: User
level: Beginner
exl-id: 22112517-40f7-4966-84bf-40794e5d0f79
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 2%

---

# 定義電子郵件的主題行和發件人{#defining-the-subject-line-of-an-email}

## 定義電子郵件的主題行 {#subject-line}

消息主題是準備和發送消息的必需內容。

>[!NOTE]
>
>如果主題行為空，則消息儀表板和電子郵件設計器中將顯示警告。

1. 建立電子郵件.
1. 開始 **[!UICONTROL Properties]** 的子菜單。
1. 填寫 **[!UICONTROL Subject]** 的子菜單。

   ![](assets/email_designer_subject.png)

1. 您還可以通過按一下相應表徵圖將個性化欄位、內容塊和動態內容添加到主題行。 有關此的詳細資訊，請參閱 [個性化](../../designing/using/personalization.md)。

## 定義電子郵件的電子郵件發件人 {#email-sender}

要定義將出現在已發送郵件標題中的發件人名稱，請轉到 **[!UICONTROL Properties]** 的子菜單。

![](assets/delivery_content_edition16.png)

* 的 **[!UICONTROL From: name]** 欄位中輸入發件人名稱。 預設情況下， **發件人名稱** 塊自動輸入到欄位中。 預設發件人電子郵件地址和發件人名稱在中定義 **[!UICONTROL Brands]** 可通過高級菜單下的Adobe Campaign徽標訪問 **[!UICONTROL Administration > Instance settings > Brand configuration]** 。

   您可以通過按一下 **發件人名稱** 框。 然後，該欄位將變為可編輯欄位，您可以輸入要使用的名稱。

   此欄位可以個性化。 為此，可以通過按一下發件人名稱下方的表徵圖來添加個性化欄位、內容塊和動態內容。 有關此的詳細資訊，請參閱 [個性化](../../designing/using/personalization.md)。

* 的 **[!UICONTROL From: email address]** 無法從此部分編輯欄位。 您可以通過從其儀表板編輯電子郵件的屬性來更改它。 有關詳細資訊，請參見 [電子郵件高級參數清單](../../administration/using/configuring-email-channel.md#advanced-parameters)。

>[!NOTE]
>
>標頭參數不能為空。 發送者地址是允許發送電子郵件（RFC標準）的必需地址。 Adobe Campaign檢查輸入的電子郵件地址的語法。

**相關主題：**

* [插入個人化欄位](../../designing/using/personalization.md#inserting-a-personalization-field)
* [添加內容塊](../../designing/using/personalization.md#adding-a-content-block)
* [在電子郵件中定義動態內容](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)
