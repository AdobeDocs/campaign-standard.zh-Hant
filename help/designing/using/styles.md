---
title: 管理樣式
description: 瞭解如何在電子郵件設計工具中管理電子郵件樣式。
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


# 管理樣式 {#managing-styles}

## 編輯電子郵件樣式{#editing-email-styles}

### 編輯元素 {#editing-an-element}

在「電子郵件設計器」中，選取元素時，窗格中會顯示特定於所選內容類型的幾個選 **[!UICONTROL Settings]** 項。 您可以使用這些選項輕鬆變更電子郵件的樣式。

### 選取元素 {#selecting-an-element}

要在「電子郵件設計器」介面中選擇元素，您可以：

* 直接在電子郵件中按一下，
* 或瀏覽左側「浮動視窗」( **Palette)選項中可用的結構樹**。

![](assets/des_tree_structure.png)

瀏覽結構樹可讓您進行更精確的選擇。 您可以選擇下列任一項：

* 整個結構，
* 組成結構元件的列之一，
* 或僅包含位於欄內的元件。

![](assets/des_tree_structure_selection.png)

要選擇列，您還可以執行以下操作：

1. 選取結構元件(直接在電子郵件中或使用左側浮動視窗中提供的結構 **樹狀**)。
1. 從內容相 **關工具列**，按一 **[!UICONTROL Select a column]** 下以選擇所要的欄。

請參閱本節的 [範例](#example--adjusting-vertical-alignment-and-padding)。

### 調整樣式設定 {#adjusting-style-settings}

1. 在電子郵件中選取元素。 如需詳細資訊，請參 [閱選取元素](#selecting-an-element)。
1. 根據您的需求調整設定。 每個選取的元素都提供不同的設定集。

   您可以插入背景、變更大小、修改水準或垂直對齊、管理顏色、 [新增填補](#selecting-an-element)或邊界等。

   若要這麼做，請使用窗格中顯示的選項或 **[!UICONTROL Settings]** 新增內 [嵌樣式屬性](#adding-inline-styling-attributes)。

   ![](assets/des_settings_pane.png)

1. 儲存您的內容。

### 關於間距和邊界 {#about-padding-and-margin}

電子郵件設計器介面可讓您快速調整填補空間和邊界設定。

**[!UICONTROL Padding]**:此設定可讓您管理位於元素邊框內的空間。

![](assets/des_padding.png)

例如：

* 使用填補功能來設定影像左側和右側的邊界。
* 使用上下填充為或元件添加更 **[!UICONTROL Text]** 多間 **[!UICONTROL Divider]** 距。
* 要設定結構元素內各列之間的邊界，請定義每列的間距。

**[!UICONTROL Margin]**:此設定可讓您管理元素邊框與下一個元素之間的間距。

![](assets/des_margin.png)

>[!NOTE]
>
>根據您的選擇（結構元件、欄或內容元件），結果將不相同。 Adobe建議在欄 **[!UICONTROL Padding]** 層級 **[!UICONTROL Margin]** 設定和參數。

對於和 **[!UICONTROL Padding]** ，單 **[!UICONTROL Margin]**&#x200B;擊鎖定表徵圖可中斷頂部和底部或右和左參數之間的同步。 這可讓您個別調整每個參數。

![](assets/des_padding_lock_icon.png)

### 關於對齊 {#about-alignment}

* **文字對齊**:將滑鼠游標置於某些文字上，然後使用內容相關工具列來對齊。

   ![](assets/des_text_alignment.png)

* **水準對齊** (Horizontal alignment)可套用至文字、影像和按鈕——目前不套用至 **[!UICONTROL Divider]** 和元 **[!UICONTROL Social]** 件。

   ![](assets/des_horizontal_alignment.png)

* 要設定垂 **直對齊**，請在結構元件中選擇一個列，然後從「設定」窗格中選擇一個選項。

   ![](assets/des_set_vertical_alignment.png)

### 關於背景 {#about-backgrounds}

在使用電子郵件設計工具設定背景時，Adobe建議您：

1. 如果您的設計需要，請將背景顏色套用至電子郵件的正文。
1. 在大多數情況下，請在欄層級設定背景顏色。
1. 請盡量不要在影像或文字元件上使用背景色彩，因為這些色彩很難管理。

以下是您可使用的背景設定。

* 為整個 **[!UICONTROL Background color]** 電子郵件設定。 請務必在導覽樹狀結構中選取可從左側浮動視窗存取的內文設定。

   ![](assets/des_background_body.png)

* 通過選擇，為所有結構元件設定相同的背景顏色 **[!UICONTROL Viewport background color]**。 此選項可讓您從背景顏色中選取不同的設定。

   ![](assets/des_background_viewport.png)

* 為每個結構元件設定不同的背景顏色。 在導覽樹狀結構中，從左側的浮動視窗中選取可存取的結構，以僅將特定背景顏色套用至該結構。

   ![](assets/des_background_structure.png)

   請確定您未設定檢視區背景顏色，因為它可能會隱藏結構背景顏色。

* 設定 **[!UICONTROL Background image]** 結構元件的內容。

   ![](assets/des_background_image.png)

   >[!NOTE]
   >
   >有些電子郵件程式不支援背景影像。 請務必選取適當的備援背景顏色，以防影像無法顯示。

* 在欄層級設定背景顏色。

   ![](assets/des_background_column.png)

   >[!NOTE]
   >
   >這是最常見的使用案例。 Adobe建議在欄層級設定背景顏色，因為這樣在編輯整個電子郵件內容時，可提供更大的彈性。

   您也可以在欄層級設定背景影像，但很少使用。

#### 範例：調整垂直對齊和間距 {#example--adjusting-vertical-alignment-and-padding}

要在由三列組成的結構元件中調整填充和垂直對齊。 要執行此操作，請遵循下列步驟：

1. 直接在電子郵件中或使用左側元件面板中的結構樹選擇結構 **元件**。
1. 從內容 **相關工具**，按一 **[!UICONTROL Select a column]** 下並選擇要編輯的工具列。 也可以從結構樹中選取它。

   ![](assets/des_selecting_column.png)

   該列的可編輯參數顯示在右 **[!UICONTROL Settings]** 側窗格中。

1. 在下 **[!UICONTROL Vertical alignment]**&#x200B;面，選擇 **[!UICONTROL Up]**。

   ![](assets/des_vertical_alignment.png)

   內容元件會顯示在欄的頂端。

1. 在下 **[!UICONTROL Padding]**&#x200B;面，定義列內的頂部填充。 按一下鎖定表徵圖以中斷與底部填充的同步。

   定義該列的左邊距和右邊距。

   ![](assets/des_adjusting_padding.png)

1. 同樣地，繼續調整其他列的對齊和間距。

   ![](assets/des_adjusting_columns.png)

1. 儲存您的變更。

### 關於樣式連結 {#about-styling-links}

>[!NOTE]
>
>此功能將從Campaign Standard 19.4版開始提供。

您可以在電子郵件設計器中為連結加下划線，並選擇其顏色和目標。

1. 在插入連結的元件中，選擇連結的標籤文本。

1. 在元件設定中，勾選以 **[!UICONTROL Underline link]** 在連結的標籤文字上加底線。

   ![](assets/stylelinks-selecttext.png)

1. 若要選取將開啟連結的瀏覽內容，請選取 **[!UICONTROL Target]**。

   ![](assets/stylelinks-target.png)

1. 若要變更連結的顏色，請按一下 **[!UICONTROL Link color]**。

   ![](assets/stylelinks-colorpicker.png)

1. 選擇您需要的顏色。

   ![](assets/stylelinks-colorchanged.png)

1. 儲存您的變更。

### 添加內嵌樣式屬性 {#adding-inline-styling-attributes}

在「電子郵件設計器」介面中，當您選取元素並在側面板顯示其設定時，可以自訂該特定元素的內嵌屬性及其值。

1. 選取內容中的元素。
1. 在側面板上，查找設 **[!UICONTROL Styles Inline]** 置。

   ![](assets/email_designer_inlineattributes.png)

1. 修改現有屬性的值，或使用+按鈕添加 **新屬** 性。 您可以新增任何與CSS相容的屬性和值。

樣式隨即會套用至選取的元素。 如果子元素沒有定義特定的樣式屬性，則會繼承父元素的樣式。

## 切換至行動裝置檢視 {#switching-to-mobile-view}

您可以個別編輯行動顯示的所有樣式選項，以微調電子郵件的互動式設計。 例如，您可以調整邊界和填補空白、使用較小或較大的字型大小、變更按鈕，或套用行動版電子郵件專用的不同背景顏色。

所有樣式選項都可在行動裝置檢視中使用。 「編輯電子郵件樣式」區段中會顯示「電子郵件設 [計器」樣式設](#editing-email-styles) 定。

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

   再按一下按 **[!UICONTROL Switch to mobile view]** 鈕，返回標準案頭檢視。 會反映變更。

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
