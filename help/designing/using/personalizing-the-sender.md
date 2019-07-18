---
title: 個人化傳送者
seo-title: 個人化傳送者
description: 個人化傳送者
seo-description: 瞭解如何個人化您的訊息傳送者姓名或地址。
page-status-flag: 從未啓動
uuid: 7aa08d5d-5e6c6c-4dac-bff88-6fde85368 c2 d
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: design
content-type: reference
topic-tags: 個人化內容
discoiquuid: 49532f6b-3cd0-4d03-932e-bcp7 d05 c74 d
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Personalizing the sender{#personalizing-the-sender}

## Email sender {#email-sender}

To define the name of the sender which will appear in the header of messages sent, go the **[!UICONTROL Properties]** tab of the Email Designer home page (accessible through the home icon).

![](assets/delivery_content_edition16.png)

* **[!UICONTROL From: name]** 欄位可讓您輸入傳送者名稱。By default, the default **Sender name** block is automatically entered in the field. Adobe Campaign refers to the email channel configuration (from the advanced menu **[!UICONTROL Administration > Channels > Email > Email accounts]** via the Adobe Campaign logo) to designate this sender.

   You can change the sender name by clicking the **Sender name** block. 欄位便會變成可編輯，您可以輸入想要使用的名稱。

   此欄位可個人化。若要這麼做，您可以按一下傳送者名稱下方的圖示，新增個人化欄位、內容區塊和動態內容。

* **[!UICONTROL From: email address]** 無法從此區域編輯欄位。您可以從控制面板編輯電子郵件的屬性來變更它。For more on this, see [List of email advanced parameters](../../administration/using/configuring-email-channel.md#advanced-parameters).

>[!NOTE]
>
>標題參數不能是空白的。傳送者的地址是強制傳送電子郵件(RFC標準)的必要地址。Adobe Campaign會檢查輸入的電子郵件地址語法。

**相關主題：**

* [插入個人化欄位](../../designing/using/inserting-a-personalization-field.md)
* [新增內容區塊](../../designing/using/adding-a-content-block.md)
* [在電子郵件中定義動態內容](../../designing/using/defining-dynamic-content-in-an-email.md)

## SMS sender {#sms-sender}

您可以個人化SMS傳送者的姓名。For more on this, refer to the [SMS configuration](../../administration/using/configuring-sms-channel.md#configuring-sms-properties) section.
