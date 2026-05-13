---
title: 定義電子郵件的主旨行和寄件者
description: 瞭解如何在電子郵件Designer中定義電子郵件的主旨行和寄件者。
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: User
level: Beginner
exl-id: 22112517-40f7-4966-84bf-40794e5d0f79
TQID: https://experienceleague.adobe.com/yT1UWD2C-BxfMymuwxE0vL3dYIOnnAjTf3O8Owx2S4g
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 338
ht-degree: 2%

---

# 定義電子郵件的主旨行和寄件者{#defining-the-subject-line-of-an-email}

## 定義電子郵件的主旨行 {#subject-line}

訊息主旨是準備和傳送訊息的必要專案。

>[!NOTE]
>
>如果主旨列為空，訊息控制面板和電子郵件Designer中會顯示警告。

1. 建立電子郵件。
1. 前往電子郵件Designer首頁的&#x200B;**[!UICONTROL Properties]**&#x200B;標籤（可透過首頁圖示存取）。
1. 填寫&#x200B;**[!UICONTROL Subject]**&#x200B;區段。

   ![](assets/email_designer_subject.png)

1. 您也可以按一下對應的圖示，將個人化欄位、內容區塊及動態內容新增至主旨列。 如需詳細資訊，請參閱[Personalization](../../designing/using/personalization.md)。

## 定義電子郵件的電子郵件寄件者 {#email-sender}

若要定義將顯示在已傳送訊息標題中的寄件者名稱，請移至電子郵件Designer首頁的&#x200B;**[!UICONTROL Properties]**&#x200B;標籤（可透過首頁圖示存取）。

![](assets/delivery_content_edition16.png)

* **[!UICONTROL From: name]**&#x200B;欄位可讓您輸入寄件者名稱。 依預設，預設的&#x200B;**寄件者名稱**&#x200B;區塊會自動輸入欄位中。 預設寄件者電子郵件地址和寄件者名稱定義於&#x200B;**[!UICONTROL Brands]**&#x200B;中，可透過進階功能表&#x200B;**[!UICONTROL Administration > Instance settings > Brand configuration]**&#x200B;下的Adobe Campaign標誌存取。

  您可以按一下&#x200B;**寄件者名稱**&#x200B;區塊來變更寄件者名稱。 欄位隨後會變成可編輯，您可以輸入要使用的名稱。

  此欄位可個人化。 若要這麼做，您可以按一下寄件者名稱下方的圖示，新增個人化欄位、內容區塊和動態內容。 如需詳細資訊，請參閱[Personalization](../../designing/using/personalization.md)。

* 無法從此節編輯&#x200B;**[!UICONTROL From: email address]**&#x200B;欄位。 您可以從電子郵件的控制面板編輯電子郵件的屬性，以變更它。 如需詳細資訊，請參閱[電子郵件進階引數清單](../../administration/using/configuring-email-channel.md#advanced-parameters)。

>[!NOTE]
>
>標頭引數不得為空白。 必須提供寄件者的地址，才能傳送電子郵件（RFC標準）。 Adobe Campaign會檢查所輸入電子郵件地址的語法。

**相關主題：**

* [插入個人化欄位](../../designing/using/personalization.md#inserting-a-personalization-field)
* [新增內容區塊](../../designing/using/personalization.md#adding-a-content-block)
* [定義電子郵件中的動態內容](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)
