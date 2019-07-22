---
title: 新增內容區塊
seo-title: 新增內容區塊
description: 新增內容區塊
seo-description: 探索各種現成可用的動態內容區塊，以個人化您的訊息，並學習如何建立自訂內容區塊。
page-status-flag: 從未啓動
uuid: 08153ea0-42fb-4c0b-8d4b-9407640748d6
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: design
content-type: reference
topic-tags: 個人化內容
discoiquuid: fda143-f42 a-4cf9-b43 c-e53 d24549025
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 84bc011b079c9f620ea672bf081e54adc023aa07

---


# Adding a content block{#adding-a-content-block}

Adobe Campaign提供預先設定的內容區塊清單。這些內容區塊是動態、個人化且具有特定的演算。例如，您可以新增問候或連結至鏡像頁面。

>[!NOTE]
>
>The images below show how to insert a content block using the [Email Designer](../../designing/using/about-email-content-design.md#about-the-email-designer) for an email.

若要新增內容區塊：

1. Click inside a text block, click the **[!UICONTROL Personalize]** icon from the contextual toolbar and select **[!UICONTROL Insert content block]**. For more on the Email Designer interface, see [this section](../../designing/using/about-email-content-design.md#email-designer-interface).

   ![](assets/email_content_block_1.png)

1. 選取您要插入的內容區塊。可用的區塊視內容(電子郵件或登陸頁面)而異。

   ![](assets/email_content_block_2.png)

1. Click **[!UICONTROL Save]**.

內容區塊的名稱會出現在編輯器中，並以黃色反白顯示。當產生個人化時，它會自動適應描述檔。

![](assets/email_content_block_3.png)

現成可用的內容區塊包括：

* **[!UICONTROL Database URL in emails (EmailUrlBase)]**：此內容區塊只能用於 **傳送**。
* **[!UICONTROL Mirror page URL (MirrorPageUrl)]**：此內容區塊只能用於 **傳送**。
* **[!UICONTROL Link to mirror page (MirrorPage)]**：此內容區塊只能用於 **傳送**。
* **[!UICONTROL Greetings (Greetings)]**
* **[!UICONTROL Unsubscription link (UnsubscriptionLink)]**：此內容區塊只能用於 **傳送**。
* **[!UICONTROL Social network sharing links (LandingPageViralLinks)]**：此內容區塊只能用於 **登陸頁面**。
* **[!UICONTROL Default sender name (DefaultSenderName)]**：此內容區塊只能用於 **傳送**。
* **[!UICONTROL Name of default reply-to email address (DefaultReplyName)]**：此內容區塊只能用於 **傳送**。
* **[!UICONTROL Email address of default sender (DefaultSenderAddress)]**：此內容區塊只能用於 **傳送**。
* **[!UICONTROL Default error email address (DefaultErrorAddress)]**：此內容區塊只能用於 **傳送**。
* **[!UICONTROL Default reply-to email address (DefaultReplyAddress)]**：此內容區塊只能用於 **傳送**。
* **[!UICONTROL Brand name (BrandingUsualName)]**
* **[!UICONTROL Link to the brand website (BrandingWebSiteLink)]**
* **[!UICONTROL Brand logo (BrandingLogo)]**
* **[!UICONTROL Notification style (notificationStyle)]**

## Creating custom content blocks {#creating-custom-content-blocks}

您可以定義將插入訊息或登陸頁面的新內容區塊。

若要建立內容區塊，請遵循下列步驟：

1. Click **[!UICONTROL Resources > Content blocks]** from the advanced menu to access the list of content blocks.
1. Click the **[!UICONTROL Create]** button or duplicate a pre-existing content block.

   ![](assets/content_bloc_01.png)

1. 輸入標籤。
1. Select the block's **[!UICONTROL Content type]**. 有三個可用選項：

   * **[!UICONTROL Shared]**：內容區塊可用於傳送或登陸頁面。
   * **[!UICONTROL Delivery]**：內容區塊只能用於傳送。
   * **[!UICONTROL Landing page]**：內容區塊只能用於登陸頁面。
   ![](assets/content_bloc_02.png)

1. You can select a **[!UICONTROL Targeting dimension]**. For more on this, see [About targeting dimension](../../designing/using/adding-a-content-block.md#about-targeting-dimension).

   ![](assets/content_bloc_04.png)

1. You can select the **[!UICONTROL Depends on format]** option to define two different blocks: one for HTML emails, and one for emails in text format. 接著會在編輯器(HTML和文字)中顯示兩個標籤，以定義對應的內容。

   ![](assets/content_bloc_03.png)

1. Enter the content of the content block(s), and click the **[!UICONTROL Create]** button.

您的內容區塊現在可以用於訊息的內容編輯器或登陸頁面中。

>[!CAUTION]
>
>When editing the content of a block, make sure there are no extra white spaces between the beginning and the end of your *if* statements. 在HTML中，空格會顯示在螢幕上，因此會影響您的內容版面。

## About targeting dimension {#about-targeting-dimension}

定位維度可讓您定義可使用內容區塊的訊息類型。這是為了避免在訊息中使用不適當的區塊，因而可能導致錯誤。

的確，編輯訊息時，您只能使用與該訊息的定位維度相容的定位維度來選取內容區塊。

For example, the **[!UICONTROL Unsubscription link]** block's targeting dimension is **[!UICONTROL Profiles]** because it contains personalization fields specific to the **[!UICONTROL Profiles]** resource. Therefore, you cannot use an **[!UICONTROL Unsubscription link]** block in an [event transactional message](../../channels/using/event-transactional-messages.md), because the targeting dimension of that type of message is **[!UICONTROL Real-time events]**. However, you can use the **Unsubscription link** block in a [profile transactional message](../../channels/using/profile-transactional-messages.md), because the targeting dimension of that type of message is **Profiles**. Finally, the **[!UICONTROL Link to mirror page]** block does not have a targeting dimension, so you can use it in any message.

如果您將此欄位保留空白，內容區塊將與所有訊息相容，不論定位維度是甚麼。如果您設定定位維度，該區塊只會與具有相同定位維度的訊息相容。

For more on this, refer to [Targeting dimensions and resources](../../automating/using/query.md#targeting-dimensions-and-resources).
