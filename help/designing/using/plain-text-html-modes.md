---
title: 純文字和 HTML 模式
description: 探索純文字和HTML模式
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
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 純文字和 HTML 模式 {#plain-text-and-html-modes}

## 產生電子郵件的文字版本 {#generating-a-text-version-of-the-email}

依預設，會 **[!UICONTROL Plain text]** 自動產生您的電子郵件版本，並與版本同 **[!UICONTROL Edit]** 步。

新增至HTML版本的個人化欄位和內容區塊也會與純文字版本同步。

>[!NOTE]
>
>若要在純文字版本中使用內容區塊，請確定它們不包含HTML程式碼。

要使純文字檔案版本與HTML版本不同，可以通過從電子郵件視圖中按一下 **[!UICONTROL Sync with HTML]** 切換來禁 **[!UICONTROL Plain text]** 用此同步。

![](assets/email_designer_textversion.png)

然後，您可以視需要編輯純文字版本。

>[!NOTE]
>
>如果您在同 **[!UICONTROL Plain text]** 步禁用時編輯版本，下次啟用該選項時 **[!UICONTROL Sync with HTML]** ，在純文字檔案版本中所做的所有更改都將替換為HTML版本。 在視圖中所做的 **[!UICONTROL Plain text]** 更改不能反映在視 **[!UICONTROL HTML]** 圖中。

## 在HTML中編輯電子郵件內容來源 {#editing-an-email-content-source-in-html}

對於最進階的使用者和除錯，您可以直接在HTML中檢視和編輯電子郵件內容。

您有兩種方式可編輯HTML版本的電子郵件：

* 選擇 **[!UICONTROL Edit]** &gt; **[!UICONTROL HTML]** 以開啟整個電子郵件的HTML版本。

   ![](assets/email_designer_html1.png)

* 從WYSIWYG介面中，選取元素並按一下圖 **[!UICONTROL Source code]** 示。

   只顯示所選元素的源。 如果所選元素是內容元件，則可以編輯源 **[!UICONTROL HTML]** 代碼。 其他元件則為唯讀模式，但仍可在電子郵件的完整HTML版本中編輯。

   ![](assets/email_designer_html2.png)

如果您修改程式碼的HTML，電子郵件的回應速度可能會中斷。 請務必使用按鈕來測 **[!UICONTROL Preview]** 試。 請參閱 [預覽訊息](../../sending/using/previewing-messages.md)。
