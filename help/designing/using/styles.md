---
title: 管理電子郵件樣式
description: 瞭解如何在電子郵件設計器中管理電子郵件樣式。
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: User
level: Intermediate
exl-id: 8daeb12d-4170-464f-ba33-afb681f72a91
source-git-commit: 5435e1dbfbe08399c488322320ac5bb8e681a79d
workflow-type: tm+mt
source-wordcount: '1038'
ht-degree: 2%

---

# 管理電子郵件樣式 {#managing-styles}


在電子郵件設計器中，選擇元素時，將在中顯示特定於所選內容類型的幾個選項 **[!UICONTROL Settings]** 的子菜單。 您可以使用這些選項輕鬆更改電子郵件的樣式。

## 選擇元素 {#selecting-an-element}

要在電子郵件設計器介面中選擇元素，您可以執行以下任一操作：

* 直接在電子郵件中按一下，
* 或瀏覽位於左側的選項中的結構樹 **調色板**。

![](assets/des_tree_structure.png)

瀏覽結構樹可以進行更準確的選擇。 您可以選擇以下任一項：

* 整個結構，
* 組成結構元件的列之一，
* 或僅包含位於列中的元件。

![](assets/des_tree_structure_selection.png)

要選擇列，還可以執行以下操作：

1. 選擇結構元件（直接在電子郵件中或使用左側提供的結構樹） **調色板**)。
1. 從 **上下文工具欄**&#x200B;按一下 **[!UICONTROL Select a column]** 的子菜單。

請參閱中的示例 [此部分](#example--adjusting-vertical-alignment-and-padding)。

## 調整樣式設定 {#adjusting-style-settings}

1. 在電子郵件中選擇元素。 有關此的詳細資訊，請參閱 [選擇元素](#selecting-an-element)。
1. 根據需要調整設定。 每個選定元素提供不同的設定集。

   您可以插入背景、更改大小、修改水準或垂直對齊、管理顏色、添加 [填充或邊距](#selecting-an-element)等等。

   為此，請使用 **[!UICONTROL Settings]** 或 [添加內聯樣式屬性](#adding-inline-styling-attributes)。

   ![](assets/des_settings_pane.png)

1. 保存您的內容。

## 調整填充和邊距 {#about-padding-and-margin}

電子郵件設計器介面允許您快速調整填充和邊距設定。

**[!UICONTROL Padding]**:此設定允許您管理位於元素邊框內的空間。

![](assets/des_padding.png)

例如：

* 使用填充設定影像左側和右側的邊距。
* 使用頂部和底部填充為 **[!UICONTROL Text]** 或 **[!UICONTROL Divider]** 元件。
* 要設定結構元素內各列之間的邊框，請為每列定義填充。

**[!UICONTROL Margin]**:此設定使您能夠管理元素邊框和下一個元素之間的空間。

![](assets/des_margin.png)

>[!NOTE]
>
>根據您的選擇（結構元件、列或內容元件），結果將不相同。 Adobe建議設定 **[!UICONTROL Padding]** 和 **[!UICONTROL Margin]** 列級的參數。

對於兩者 **[!UICONTROL Padding]** 和 **[!UICONTROL Margin]**，按一下鎖定表徵圖可中斷上下或右左參數之間的同步。 這使您能夠單獨調整每個參數。

![](assets/des_padding_lock_icon.png)

## 造型對齊 {#about-alignment}

* **文本對齊**:將滑鼠的游標置於某些文本上，然後使用上下文工具欄對齊它。

   ![](assets/des_text_alignment.png)

* **水準對齊** 可應用於文本、影像和按鈕 — 當前不適用於 **[!UICONTROL Divider]** 和 **[!UICONTROL Social]** 元件。

   ![](assets/des_horizontal_alignment.png)

* 設定 **垂直對齊**，選擇結構元件內的列，然後從「設定」窗格中選擇一個選項。

   ![](assets/des_set_vertical_alignment.png)

## 設定背景 {#about-backgrounds}

>[!CONTEXTUALHELP]
>id="ac_edition_backgroundimage"
>title="背景設定"
>abstract="電子郵件設計器允許您個性化內容的背景顏色或背景影像。請注意，並非所有電子郵件客戶端都支援背景影像。"

在使用電子郵件設計器設定背景時，Adobe建議使用以下內容：

1. 如果設計需要，請將背景色應用於電子郵件正文。
1. 在大多數情況下，在列級別設定背景顏色。
1. 由於影像或文本元件難以管理，請盡量不要使用背景顏色。

下面是您可以使用的可用背景設定。

* 設定 **[!UICONTROL Background color]** 整封郵件。 確保在可從左側元件面板訪問的導航樹中選擇主體設定。

   ![](assets/des_background_body.png)

* 通過選擇 **[!UICONTROL Viewport background color]**。 此選項允許您從背景顏色中選擇其他設定。

   ![](assets/des_background_viewport.png)

* 為每個結構元件設定不同的背景顏色。 在導航樹中選擇一個結構，該結構可從左側的調色板訪問，以僅將特定背景顏色應用於該結構。

   ![](assets/des_background_structure.png)

   請確保未設定視區背景顏色，因為它可能隱藏結構背景顏色。

* 設定 **[!UICONTROL Background image]** 的子菜單。

   ![](assets/des_background_image.png)

   >[!NOTE]
   >
   >某些電子郵件程式不支援背景影像。 不支援時，將改用行背景顏色。 確保在無法顯示影像時選擇適當的後退背景顏色。

* 在列級別設定背景顏色。

   ![](assets/des_background_column.png)

   >[!NOTE]
   >
   >這是最常見的使用案例。 Adobe建議在列級別設定背景顏色，因為這樣在編輯整個電子郵件內容時就更加靈活。

   也可以在列級別設定背景影像，但很少使用。

### 示例：調整垂直對齊和填充 {#example--adjusting-vertical-alignment-and-padding}

要在由三列組成的結構元件內調整填充和垂直對齊。 要執行此操作，請遵循下列步驟：

1. 直接在電子郵件中選擇結構元件，或使用左側提供的結構樹 **調色板**。
1. 從 **上下文工具欄**&#x200B;按一下 **[!UICONTROL Select a column]** 選擇要編輯的。 也可以從結構樹中選取它。

   ![](assets/des_selecting_column.png)

   該列的可編輯參數顯示在 **[!UICONTROL Settings]** 的子菜單。

1. 下 **[!UICONTROL Vertical alignment]**&#x200B;選中 **[!UICONTROL Up]**。

   ![](assets/des_vertical_alignment.png)

   內容元件顯示在列的頂部。

1. 下 **[!UICONTROL Padding]**，定義列內的頂部填充。 按一下鎖定表徵圖以用底部填充中斷同步。

   定義該列的左邊距和右邊距。

   ![](assets/des_adjusting_padding.png)

1. 同樣，繼續調整其他列的對齊和填充。

   ![](assets/des_adjusting_columns.png)

1. 儲存您的變更。

## 樣式連結 {#about-styling-links}

您可以在電子郵件設計器中為連結加下划線並選擇其顏色和目標。

1. 在插入連結的元件中，選擇連結的標籤文本。

1. 在元件設定中，檢查 **[!UICONTROL Underline link]** 為連結的標籤文本加下划線。

   ![](assets/stylelinks-selecttext.png)

1. 要選擇將開啟連結的瀏覽上下文，請選擇 **[!UICONTROL Target]**。

   ![](assets/stylelinks-target.png)

1. 要更改連結的顏色，請按一下 **[!UICONTROL Link color]**。

   ![](assets/stylelinks-colorpicker.png)

1. 選擇所需的顏色。

   ![](assets/stylelinks-colorchanged.png)

1. 儲存您的變更。

## 添加內聯樣式屬性 {#adding-inline-styling-attributes}

在「電子郵件設計器」介面中，選擇某個元素並在側面板上顯示其設定時，可以自定義該特定元素的內嵌屬性及其值。

1. 在內容中選擇元素。
1. 在側面板上，查找 **[!UICONTROL Styles Inline]** 的子菜單。

   ![](assets/email_designer_inlineattributes.png)

1. 修改現有屬性的值，或使用 **+** 按鈕 您可以添加符合CSS的任何屬性和值。

樣式隨後應用於所選元素。 如果子元素沒有定義特定的樣式屬性，則父元素的樣式將繼承。
