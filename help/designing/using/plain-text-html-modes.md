---
solution: Campaign Standard
product: campaign
title: 編輯純文字、HTML和行動電子郵件格式
description: 探索純文字和HTML模式
audience: designing
content-type: reference
topic-tags: editing-email-content
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '776'
ht-degree: 0%

---


# 編輯純文字、HTML和行動電子郵件格式 {#plain-text-and-html-modes}

電子郵件設計工具可讓您編輯數個轉譯電子郵件。 您可以產生電子郵件的文字版本、編輯電子郵件的HTML來源，並設計行動裝置檢視的電子郵件。

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

* 選擇 **[!UICONTROL Edit]** > **[!UICONTROL HTML]** 以開啟整個電子郵件的HTML版本。

   ![](assets/email_designer_html1.png)

* 從WYSIWYG介面中，選取元素並按一下圖 **[!UICONTROL Source code]** 示。

   只顯示所選元素的源。 如果所選元素是內容元件，則可以編輯源 **[!UICONTROL HTML]** 代碼。 其他元件則為唯讀模式，但仍可在電子郵件的完整HTML版本中編輯。

   ![](assets/email_designer_html2.png)

如果您修改程式碼的HTML，電子郵件的回應速度可能會中斷。 請務必使用按鈕來測 **[!UICONTROL Preview]** 試。 請參閱「[預覽訊息](../../sending/using/previewing-messages.md)」。

## 設計適用於行動裝置轉換的電子郵件 {#switching-to-mobile-view}

您可以個別編輯行動顯示的所有樣式選項，以微調電子郵件的互動式設計。 例如，您可以調整邊界和填補空白、使用較小或較大的字型大小、變更按鈕，或套用行動版電子郵件專用的不同背景顏色。

所有樣式選項都可在行動裝置檢視中使用。 「電子郵件設計器」樣式設定先前會顯示在此頁面。

1. 建立電子郵件並開始編輯內容。 如需詳細資訊，請參 [閱從頭設計電子郵件內容](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)。
1. 若要存取專用的行動裝置檢視，請選取 **[!UICONTROL Switch to mobile view]** 按鈕。

   ![](assets/email_designer_mobile_view_switch.png)

   隨即顯示電子郵件的行動版本。 它包含案頭檢視中定義的所有元件和樣式。

1. 獨立編輯所有樣式設定，例如背景顏色、對齊、填補、邊界、字型系列、文字顏色等。

   ![](assets/email_designer_mobile_view.png)

1. 在行動檢視中編輯任何樣式設定時，修改僅會套用至行動顯示。

   例如，縮小影像大小、新增綠色背景並變更行動檢視中的間距。

   ![](assets/email_designer_mobile_view_change.png)

1. 您可以在行動裝置上顯示元件時隱藏元件。 要執行此操作，請從 **[!UICONTROL Show only on desktop devices]** 中選擇 **[!UICONTROL Display options]**。

   您也可以選擇在桌上型裝置上隱藏此元件，這表示此元件只會顯示在行動裝置上。 若要這麼做，請選取 **[!UICONTROL Show only on mobile devices]**。

   例如，此選項可讓您在行動裝置上顯示特定影像，在桌上型裝置上顯示其他影像。

   您可以從行動裝置或案頭檢視設定此選項。

   ![](assets/email_designer_mobile_hide.png)

1. 再按一下按 **[!UICONTROL Switch to mobile view]** 鈕，返回標準案頭檢視。 您剛做的樣式變更不會反映在內。

   ![](assets/email_designer_mobile_view_desktop_no-change.png)

   >[!NOTE]
   >
   >唯一的例外是設 **[!UICONTROL Style inline]** 定。 任何樣式內嵌設定變更也會套用至標準案頭檢視。

1. 任何對電子郵件結構或內容的其他變更，例如文字編輯、上傳新影像、新增元件等。 也會套用至標準檢視。

   例如，切換回行動裝置檢視、編輯部分文字並取代影像。

   ![](assets/email_designer_mobile_view_change_content.png)

1. 再按一下按 **[!UICONTROL Switch to mobile view]** 鈕，返回標準案頭檢視。 會反映變更。

   ![](assets/email_designer_mobile_view_desktop_content-change.png)

1. 移除行動檢視中的樣式會帶您回到案頭模式中套用的樣式。

   例如，在行動裝置檢視中，將綠色背景顏色套用至按鈕。

   ![](assets/email_designer_mobile_view_background_mobile.png)

1. 切換至案頭檢視，並將灰色背景套用至相同的按鈕。

   ![](assets/email_designer_mobile_view_background_desktop.png)

1. 再次切換至行動檢視，現在停用設 **[!UICONTROL Background color]** 定。

   ![](assets/email_designer_mobile_view_background_mobile_disabled.png)

   案頭檢視中定義的背景顏色現在會套用：會變成灰色（而非空白）。

   唯一的例外是設 **[!UICONTROL Border color]** 定。 在行動檢視中停用時，即使在案頭檢視中定義了邊框色彩，也不會再套用邊框。

>[!NOTE]
>
>行動裝置檢視無法用於 [片段](../../designing/using/using-reusable-content.md#about-fragments)。
