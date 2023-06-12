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
ht-degree: 1%

---

# 編輯純文字、HTML和行動電子郵件格式 {#plain-text-and-html-modes}

電子郵件設計工具可讓您編輯電子郵件的數個轉譯。 您可以產生電子郵件的文字版本、編輯電子郵件的HTML來源，並設計電子郵件以利行動檢視。

## 產生電子郵件的文字版本 {#generating-a-text-version-of-the-email}

根據預設， **[!UICONTROL Plain text]** 系統會自動產生您電子郵件的版本，並會與 **[!UICONTROL Edit]** 版本。

新增至HTML版本的個人化欄位和內容區塊也會與純文字版本同步。

>[!NOTE]
>
>若要以純文字版本使用內容區塊，請確定它們不包含HTML程式碼。

若要使用與HTML版本不同的純文字版本，您可以按一下 **[!UICONTROL Sync with HTML]** 切換自 **[!UICONTROL Plain text]** 電子郵件檢視。

![](assets/email_designer_textversion.png)

然後，您可以視需要編輯純文字版本。

>[!NOTE]
>
>如果您編輯 **[!UICONTROL Plain text]** 版本進行更新，但下次您啟用 **[!UICONTROL Sync with HTML]** 選項，您在純文字版本中所做的所有變更都將以HTML版本取代。 在中進行的變更 **[!UICONTROL Plain text]** 檢視無法反映在 **[!UICONTROL HTML]** 檢視。

## 編輯HTML中的電子郵件內容來源 {#editing-an-email-content-source-in-html}

對於最進階的使用者和偵錯，您可以直接在HTML中檢視和編輯電子郵件內容。

編輯電子郵件HTML版本的方法有兩種：

* 選取 **[!UICONTROL Edit]** > **[!UICONTROL HTML]** 以開啟整封電子郵件的HTML版本。

   ![](assets/email_designer_html1.png)

* 從WYSIWYG介面中，選取元素並按一下 **[!UICONTROL Source code]** 圖示。

   只會顯示所選元素的來源。 如果選取的元素為，您可以編輯原始程式碼 **[!UICONTROL HTML]** 內容元件。 其他元件處於唯讀模式，但仍可在電子郵件的完整HTML版本中編輯。

   ![](assets/email_designer_html2.png)

如果您修改程式碼的HTML，電子郵件的回應速度可能會中斷。 請務必使用 **[!UICONTROL Preview]** 按鈕。 請參閱「[預覽訊息](../../sending/using/previewing-messages.md)」。

## 為行動呈現設計電子郵件 {#switching-to-mobile-view}

您可以個別編輯行動顯示的所有樣式選項，微調電子郵件的回應式設計。 例如，您可以調整邊界與內距、使用較小或較大的字型大小、變更按鈕，或套用您的電子郵件行動版本特定的不同背景顏色。

行動檢視中提供所有樣式選項。 電子郵件設計工具樣式設定會先顯示在此頁面上。

1. 建立電子郵件並開始編輯內容。 如需詳細資訊，請參閱 [從頭開始設計電子郵件內容](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).
1. 若要存取專用的行動檢視，請選取 **[!UICONTROL Switch to mobile view]** 按鈕。

   ![](assets/email_designer_mobile_view_switch.png)

   隨即顯示電子郵件的行動版本。 它包含案頭檢視中定義的所有元件和樣式。

1. 獨立編輯所有樣式設定，例如背景顏色、對齊、邊框間距、邊界、字型系列、文字顏色等。

   ![](assets/email_designer_mobile_view.png)

1. 在行動檢視中編輯任何樣式設定時，修改只會套用至行動顯示。

   例如，縮小影像大小、新增綠色背景並變更行動檢視中的邊框間距。

   ![](assets/email_designer_mobile_view_change.png)

1. 在行動裝置上顯示元件時，您可以隱藏元件。 要執行此操作，請選取 **[!UICONTROL Show only on desktop devices]** 從 **[!UICONTROL Display options]**.

   您也可以選擇在案頭裝置上隱藏此元件，這表示它只會顯示在行動裝置上。 要執行此操作，請選取 **[!UICONTROL Show only on mobile devices]**.

   例如，此選項可讓您在行動裝置上顯示特定影像，而在桌上型裝置上顯示另一個影像。

   您可以從行動或案頭檢視設定此選項。

   ![](assets/email_designer_mobile_hide.png)

1. 再按一下 **[!UICONTROL Switch to mobile view]** 按鈕以返回標準案頭檢視。 您剛才所做的樣式變更不會反映出來。

   ![](assets/email_designer_mobile_view_desktop_no-change.png)

   >[!NOTE]
   >
   >唯一的例外是 **[!UICONTROL Style inline]** 設定。 任何樣式內嵌設定變更也會套用至標準案頭檢視。

1. 對電子郵件結構或內容的任何其他變更，例如文字編輯、上傳新影像、新增元件等。 也會套用至標準檢視。

   例如，切換回行動檢視、編輯部分文字並取代影像。

   ![](assets/email_designer_mobile_view_change_content.png)

1. 再按一下 **[!UICONTROL Switch to mobile view]** 按鈕以返回標準案頭檢視。 變更會反映出來。

   ![](assets/email_designer_mobile_view_desktop_content-change.png)

1. 移除行動檢視中的樣式時，系統會帶您回到先前在案頭模式中套用的樣式。

   例如，在行動檢視中，將綠色背景顏色套用至按鈕。

   ![](assets/email_designer_mobile_view_background_mobile.png)

1. 切換至案頭檢視，並將灰色背景套用至相同的按鈕。

   ![](assets/email_designer_mobile_view_background_desktop.png)

1. 再次切換至行動檢視，現在停用 **[!UICONTROL Background color]** 設定。

   ![](assets/email_designer_mobile_view_background_mobile_disabled.png)

   現在會套用案頭檢視中定義的背景顏色：它會變成灰色（非空白）。

   唯一的例外是 **[!UICONTROL Border color]** 設定。 在行動檢視中停用時，即使案頭檢視中定義了邊框顏色，也不會再套用邊框。

>[!NOTE]
>
>行動檢視無法用於 [片段](../../designing/using/using-reusable-content.md#about-fragments).
