---
title: 定義直接郵件內容
seo-title: 定義直接郵件內容
description: 定義直接郵件內容
seo-description: 瞭解如何定義內容以供直接傳送郵件。
page-status-flag: 從未啓動
uuid: c1234c06-4d22-46d7-ad1 b-3c88660 f9 b06
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 頻道
content-type: reference
topic-tags: 直接郵件
discoiquuid: 9e73d6b5-41b4-474b-a880-a0 cd5999 c2 d1
context-tags: delivery，DirectMailContent，back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b0cf437ec97153b53bd4502171b24286abb25731

---


# Defining the direct mail content{#defining-the-direct-mail-content}

You can either define the content in the last screen of the creation wizard or by clicking on the **Content** section of the delivery dashboard.

![](assets/direct_mail_6.png)

**[!UICONTROL Content]** 定義畫面是直接郵件頻道專屬的。It is divided into four tabs: **[!UICONTROL Extraction]**, **[!UICONTROL File structure]**, **[!UICONTROL Header]** and **[!UICONTROL Footer]**.

![](assets/direct_mail_11.png)

## Defining the extraction {#defining-the-extraction}

1. 首先，請定義擷取檔案的名稱。Click on the button to the right of the **[!UICONTROL Output file]** field and enter the desired label. You can use personalization fields, content blocks and dynamic text (see [Defining content](../../designing/using/example--email-personalization.md)). 例如，您可以使用傳送ID或擷取日期來完成標籤。

   ![](assets/direct_mail_12.png)

1. Click the **[!UICONTROL +]** or **[!UICONTROL Add an element]** button to add an output column. The **[!UICONTROL Output columns]** let you define the profile information (columns) to be exported into the output file.

   >[!CAUTION]
   >
   >請確定您的個人檔案包含郵寄地址，因為此資訊對直接郵件提供者而言是不可或缺的資訊。Also make sure you have checked the **[!UICONTROL Address specified]** box in your profiles' information. See [Recommendations](../../channels/using/about-direct-mail.md#recommendations).

   ![](assets/direct_mail_13.png)

1. 建立任意數量的欄。您可以按一下其運算式和標籤來編輯欄。

>[!NOTE]
>
>For more information on output column definition, refer to the [Extract file](../../automating/using/extract-file.md) workflow activity section.

## Defining the file structure {#defining-the-file-structure}

**「檔案結構** 」標籤可讓您設定將匯出檔案的輸出、日期和數字格式。

![](assets/direct_mail_14.png)

>[!NOTE]
>
>[「摘取檔案](../../automating/using/extract-file.md) 工作流程」活動區段中會詳細說明可用選項。

## Defining the header and footer {#defining-the-header-and-footer}

有時您可能需要在擷取檔案的開頭或結尾新增資訊。For this, use the **[!UICONTROL Header]** and **[!UICONTROL Footer]** tabs of the **[!UICONTROL Content]** configuration screen.

![](assets/direct_mail_7.png)

例如，您可能想要在直接郵件提供者中包含檔案標題中的傳送者資訊。您可以將頁尾和頁首個人化，並提供傳送內容中可用的資訊。See [Defining content](../../designing/using/example--email-personalization.md).

The sender address is defined in the **[!UICONTROL Send]** section of the direct mail properties or at the template level.

![](assets/direct_mail_24.png)

