---
title: 編輯純文字、HTML和行動電子郵件格式
description: 探索純文字和HTML模式
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: User
level: Intermediate
exl-id: 760c3c30-c899-4cf4-ba59-fb2fade9fc5e
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '776'
ht-degree: 0%

---

# 編輯純文字、HTML和行動電子郵件格式 {#plain-text-and-html-modes}

電子郵件設計工具可讓您編輯數次轉譯的電子郵件。 您可以產生電子郵件的文字版本、編輯電子郵件的HTML來源，以及設計行動檢視的電子郵件。

## 產生電子郵件的文字版本 {#generating-a-text-version-of-the-email}

依預設， **[!UICONTROL Plain text]** 會自動產生您的電子郵件版本，並與 **[!UICONTROL Edit]** 版本。

新增至HTML版本的個人化欄位和內容區塊也會與純文字版本同步。

>[!NOTE]
>
>若要以純文字版本使用內容區塊，請確定其中不包含HTML程式碼。

若要使純文字版本與HTML版本不同，您可以按一下 **[!UICONTROL Sync with HTML]** 從 **[!UICONTROL Plain text]** 電子郵件的檢視。

![](assets/email_designer_textversion.png)

然後，您可以視需要編輯純文字版本。

>[!NOTE]
>
>如果您編輯 **[!UICONTROL Plain text]** 同步時的版本，則下次啟用 **[!UICONTROL Sync with HTML]** 選項，則在純文字版本中所做的所有更改都將替換為HTML版本。 在 **[!UICONTROL Plain text]** 檢視無法反映在 **[!UICONTROL HTML]** 檢視。

## 在HTML中編輯電子郵件內容來源 {#editing-an-email-content-source-in-html}

對於最進階的使用者和除錯，您可以直接以HTML檢視和編輯電子郵件內容。

您有兩種方式可編輯電子郵件的HTML版本：

* 選擇 **[!UICONTROL Edit]** > **[!UICONTROL HTML]** 開啟整個電子郵件的HTML版本。

   ![](assets/email_designer_html1.png)

* 從WYSIWYG介面中，選取元素並按一下 **[!UICONTROL Source code]** 表徵圖。

   僅顯示所選元素的源。 如果所選元素是 **[!UICONTROL HTML]** 內容元件。 其他元件處於唯讀模式，但仍可以以電子郵件的完整HTML版本進行編輯。

   ![](assets/email_designer_html2.png)

如果您修改程式碼的HTML，電子郵件的回應可能會中斷。 請務必使用 **[!UICONTROL Preview]** 按鈕。 請參閱「[預覽訊息](../../sending/using/previewing-messages.md)」。

## 為行動轉譯設計電子郵件 {#switching-to-mobile-view}

您可以分別編輯行動顯示的所有樣式選項，微調電子郵件的回應式設計。 例如，您可以調整邊距和邊框間距、使用較小或較大的字型大小、更改按鈕，或應用特定於行動版電子郵件的不同背景顏色。

所有樣式選項均可在行動檢視中使用。 電子郵件設計工具樣式設定先前會顯示在此頁面上。

1. 建立電子郵件並開始編輯內容。 有關詳細資訊，請參閱 [從草稿開始設計電子郵件內容](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).
1. 若要存取專用的行動檢視，請選取 **[!UICONTROL Switch to mobile view]** 按鈕。

   ![](assets/email_designer_mobile_view_switch.png)

   螢幕上會顯示電子郵件的行動版本。 它包含案頭檢視中定義的所有元件和樣式。

1. 獨立編輯所有樣式設定，如背景顏色、對齊方式、邊框間距、邊距、字型系列、文字顏色等。

   ![](assets/email_designer_mobile_view.png)

1. 在行動檢視中編輯任何樣式設定時，修改只會套用至行動顯示。

   例如，縮小影像大小、新增綠色背景並變更行動檢視中的邊框間距。

   ![](assets/email_designer_mobile_view_change.png)

1. 在行動裝置上顯示元件時，您可以隱藏該元件。 要執行此操作，請選取 **[!UICONTROL Show only on desktop devices]** 從 **[!UICONTROL Display options]**.

   您也可以選擇在桌上型電腦裝置上隱藏此元件，這表示此元件只會顯示在行動裝置上。 要執行此操作，請選取 **[!UICONTROL Show only on mobile devices]**.

   例如，此選項可讓您在行動裝置上顯示特定影像，在案頭裝置上顯示另一個影像。

   您可以從行動或案頭檢視設定此選項。

   ![](assets/email_designer_mobile_hide.png)

1. 再按一下 **[!UICONTROL Switch to mobile view]** 按鈕，返回標準案頭視圖。 您剛做的樣式變更不會反映在內。

   ![](assets/email_designer_mobile_view_desktop_no-change.png)

   >[!NOTE]
   >
   >唯一的例外是 **[!UICONTROL Style inline]** 設定。 任何樣式內嵌設定變更也會套用至標準案頭檢視。

1. 對電子郵件的結構或內容進行任何其他變更，例如文字編輯、上傳新影像、新增元件等。 也會套用至標準檢視。

   例如，切換回行動檢視、編輯一些文字並取代影像。

   ![](assets/email_designer_mobile_view_change_content.png)

1. 再按一下 **[!UICONTROL Switch to mobile view]** 按鈕，返回標準案頭視圖。 會反映變更。

   ![](assets/email_designer_mobile_view_desktop_content-change.png)

1. 移除行動檢視中的樣式會回到案頭模式中已套用的樣式。

   例如，在行動檢視中，將綠色背景顏色套用至按鈕。

   ![](assets/email_designer_mobile_view_background_mobile.png)

1. 切換至案頭檢視，並將灰色背景套用至相同按鈕。

   ![](assets/email_designer_mobile_view_background_desktop.png)

1. 再次切換至行動檢視，並現在停用 **[!UICONTROL Background color]** 設定。

   ![](assets/email_designer_mobile_view_background_mobile_disabled.png)

   現在已套用案頭檢視中定義的背景顏色：會變成灰色（非空白）。

   唯一的例外是 **[!UICONTROL Border color]** 設定。 在行動檢視中停用時，即使案頭檢視中已定義邊框顏色，也不會再套用邊框。

>[!NOTE]
>
>行動檢視無法在 [片段](../../designing/using/using-reusable-content.md#about-fragments).
