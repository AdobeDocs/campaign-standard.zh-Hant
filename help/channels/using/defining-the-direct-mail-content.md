---
title: 定義直接郵件內容
description: 瞭解如何定義直接郵件傳送的內容。
page-status-flag: 從未激活
uuid: c1234c06-4d22-46d7-ad1b-3c88660f9b06
contentOwner: 紹維亞
products: SG_CAMPAIGN/STANDARD
audience: 頻道
content-type: 參考
topic-tags: 直接郵件
discoiquuid: 9e73d6b5-41b4-474b-a880-a0cd5999c2d1
context-tags: delivery,directMailContent,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 定義直接郵件內容{#defining-the-direct-mail-content}

您可以在建立精靈的最後一個畫面中定義內容，或按一下傳送控制面板的「內 **容** 」區段來定義內容。

![](assets/direct_mail_6.png)

定義 **[!UICONTROL Content]** 畫面是直效郵件頻道專屬的。 它分為四個標籤： **[!UICONTROL Extraction]**、 **[!UICONTROL File structure]****[!UICONTROL Header]** 和 **[!UICONTROL Footer]**。

![](assets/direct_mail_11.png)

## 定義抽取 {#defining-the-extraction}

1. 首先，定義抽取檔案的名稱。 按一下欄位右側的按鈕， **[!UICONTROL Output file]** 然後輸入所要的標籤。 您可以使用個人化欄位、內容區塊和動態文字(請參閱 [定義內容](../../designing/using/personalization.md#example-email-personalization))。 例如，您可以使用傳送ID或擷取日期來完成標籤。

   ![](assets/direct_mail_12.png)

1. 按一下或 **[!UICONTROL +]** 按 **[!UICONTROL Add an element]** 鈕添加輸出列。 可 **[!UICONTROL Output columns]** 以定義要導出到輸出檔案的配置檔案資訊（列）。

   >[!CAUTION]
   >
   >請確定您的個人檔案包含郵寄地址，因為這項資訊對於直效郵件提供者至關重要。 另請確定您已勾選設定 **[!UICONTROL Address specified]** 檔資訊中的方塊。 請參 [閱Recommendations](../../channels/using/about-direct-mail.md#recommendations)。

   ![](assets/direct_mail_13.png)

1. 建立您所需的欄數。 您可以按一下欄的運算式和標籤來編輯欄。

>[!NOTE]
>
>有關輸出列定義的詳細資訊，請參閱「提取文 [件工作流](../../automating/using/extract-file.md) 」活動部分。

## 定義檔案結構 {#defining-the-file-structure}

「文 **件結構** 」(File structure)頁籤允許您配置要導出的檔案的輸出、日期和編號格式。

![](assets/direct_mail_14.png)

>[!NOTE]
>
>可用選項在「提取檔案」工作 [流活動部分中](../../automating/using/extract-file.md) 有詳細說明。

## 定義頁首和頁尾 {#defining-the-header-and-footer}

有時，您可能需要在抽取檔案的開頭或結尾添加資訊。 為此，請使用 **[!UICONTROL Header]** 配置 **[!UICONTROL Footer]** 螢幕的和 **[!UICONTROL Content]** 頁籤。

![](assets/direct_mail_7.png)

例如，對於直接郵件提供者，您可能希望在檔案的標題中包括發件人資訊。 您可以使用傳送內容中的可用資訊來個人化頁尾和頁首。 請參閱 [定義內容](../../designing/using/personalization.md#example-email-personalization)。

發件人地址在直接郵件屬 **[!UICONTROL Send]** 性的部分或模板級別中定義。

![](assets/direct_mail_24.png)

