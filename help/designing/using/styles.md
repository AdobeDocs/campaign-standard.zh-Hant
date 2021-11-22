---
title: 管理電子郵件樣式
description: 了解如何在電子郵件設計工具中管理電子郵件樣式。
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: User
level: Intermediate
exl-id: 8daeb12d-4170-464f-ba33-afb681f72a91
source-git-commit: 13d419c5fc51845ee14f8a3b288f4c467e0a60d9
workflow-type: tm+mt
source-wordcount: '1052'
ht-degree: 1%

---

# 管理電子郵件樣式 {#managing-styles}


在電子郵件設計工具中選取元素時，與所選內容類型相關的數個選項會顯示在 **[!UICONTROL Settings]** 框。 您可以使用這些選項輕鬆變更電子郵件的樣式。

## 選取元素 {#selecting-an-element}

若要在「電子郵件設計工具」介面中選取元素，您可以：

* 直接在電子郵件中按一下，
* 或瀏覽左側選項中可用的結構樹 **浮動視窗**.

![](assets/des_tree_structure.png)

瀏覽結構樹可讓您進行更精確的選取。 您可以選取下列任一項：

* 整個結構，
* 組成結構元件的列之一，
* 或僅包含位於欄內的元件。

![](assets/des_tree_structure_selection.png)

若要選取欄，您也可以執行下列操作：

1. 選取結構元件(直接在電子郵件中，或使用左側可用的結構樹 **浮動視窗**)。
1. 從 **內容工具列**，按一下 **[!UICONTROL Select a column]** 來選擇所需的欄。

請參閱 [本節](#example--adjusting-vertical-alignment-and-padding).

## 調整樣式設定 {#adjusting-style-settings}

1. 在電子郵件中選取元素。 有關詳細資訊，請參閱 [選取元素](#selecting-an-element).
1. 根據您的需求調整設定。 每個選取的元素都提供不同的設定集。

   您可以插入背景、更改大小、修改水準或垂直對齊、管理顏色、添加 [邊距](#selecting-an-element)等。

   若要這麼做，請使用 **[!UICONTROL Settings]** 窗格 [新增內嵌樣式屬性](#adding-inline-styling-attributes).

   ![](assets/des_settings_pane.png)

1. 儲存您的內容。

## 調整邊框間距和邊距 {#about-padding-and-margin}

電子郵件設計工具介面可讓您快速調整邊框間距和邊距設定。

**[!UICONTROL Padding]**:此設定可讓您管理元素邊框內的空間。

![](assets/des_padding.png)

例如：

* 使用邊框間距設定影像的左側和右側邊距。
* 使用上下邊框間距為 **[!UICONTROL Text]** 或 **[!UICONTROL Divider]** 元件。
* 若要設定結構元素內各欄之間的邊框，請定義每欄的邊框間距。

**[!UICONTROL Margin]**:此設定可讓您管理元素邊框與下一個元素之間的空間。

![](assets/des_margin.png)

>[!NOTE]
>
>根據您的選取項目（結構元件、欄或內容元件），結果將不相同。 Adobe建議將 **[!UICONTROL Padding]** 和 **[!UICONTROL Margin]** 參數。

兩者皆適用 **[!UICONTROL Padding]** 和 **[!UICONTROL Margin]**，按一下鎖定圖示以中斷上下或左右參數之間的同步。 這可讓您分別調整每個參數。

![](assets/des_padding_lock_icon.png)

## 樣式對齊 {#about-alignment}

* **文字對齊方式**:將滑鼠游標放在某些文字上，然後使用內容工具列來對齊。

   ![](assets/des_text_alignment.png)

* **水準對齊** 可套用至文字、影像和按鈕 — 目前不適用於 **[!UICONTROL Divider]** 和 **[!UICONTROL Social]** 元件。

   ![](assets/des_horizontal_alignment.png)

* 若要設定 **垂直對齊**，請選取結構元件內的欄，然後從「設定」窗格中選擇選項。

   ![](assets/des_set_vertical_alignment.png)

## 設定背景 {#about-backgrounds}

>[!CONTEXTUALHELP]
>id="ac_edition_backgroundimage"
>title="背景設定"
>abstract="電子郵件設計工具可讓您個人化內容的背景顏色或背景影像。請注意，並非所有電子郵件用戶端都支援背景影像。"
>additional-url="https://docs.google.com/spreadsheets/d/1TLo62YKm3tThUWDOIliCQFWs3dpNjpDfw6DdTr1oGOw/edit#gid=0" text="其他資訊"

若是使用電子郵件設計工具來設定背景，Adobe建議使用下列項目：

1. 如果設計需要，請將背景顏色套用至電子郵件的正文。
1. 在大多數情況下，在列級別設定背景顏色。
1. 請盡量不要在影像或文字元件上使用背景顏色，因為這些顏色難以管理。

以下是您可使用的可用背景設定。

* 設定 **[!UICONTROL Background color]** 整封電子郵件。 請務必在導覽樹狀結構中選取可從左側浮動視窗存取的內文設定。

   ![](assets/des_background_body.png)

* 通過選擇 **[!UICONTROL Viewport background color]**. 此選項可讓您從背景顏色中選取不同的設定。

   ![](assets/des_background_viewport.png)

* 為每個結構元件設定不同的背景顏色。 在導航樹中選擇一個結構，可從左側調色板訪問，以僅將特定背景顏色應用於該結構。

   ![](assets/des_background_structure.png)

   請確定您未設定檢視區背景顏色，因為它可能會隱藏結構背景顏色。

* 設定 **[!UICONTROL Background image]** （對於結構元件的內容）。

   ![](assets/des_background_image.png)

   >[!NOTE]
   >
   >有些電子郵件程式不支援背景影像。 若不支援，則會改用列背景顏色。 請務必選取適當的後援背景顏色，以備影像無法顯示時使用。

* 在列級別設定背景顏色。

   ![](assets/des_background_column.png)

   >[!NOTE]
   >
   >這是最常見的使用案例。 Adobe建議在欄層級設定背景顏色，因為這樣在編輯整個電子郵件內容時可提供更大的彈性。

   您也可以在欄層級設定背景影像，但此功能很少使用。

### 範例：調整垂直對齊和填充 {#example--adjusting-vertical-alignment-and-padding}

要調整由三列組成的結構元件內的邊框間距和垂直對齊方式。 要執行此操作，請遵循下列步驟：

1. 直接在電子郵件中選取結構元件，或使用左側可用的結構樹 **浮動視窗**.
1. 從 **內容工具列**，按一下 **[!UICONTROL Select a column]** 並選擇要編輯的。 您也可以從結構樹中選取它。

   ![](assets/des_selecting_column.png)

   該列的可編輯參數顯示在 **[!UICONTROL Settings]** 窗格。

1. 在 **[!UICONTROL Vertical alignment]**，選取 **[!UICONTROL Up]**.

   ![](assets/des_vertical_alignment.png)

   內容元件會顯示在欄的頂端。

1. 在 **[!UICONTROL Padding]**，定義欄內的上邊框間距。 按一下鎖定圖示以中斷與底部邊框間距的同步。

   定義該欄的左邊框和右邊框間距。

   ![](assets/des_adjusting_padding.png)

1. 以類似方式繼續調整其他列的對齊方式和邊框間距。

   ![](assets/des_adjusting_columns.png)

1. 儲存您的變更。

## 樣式連結 {#about-styling-links}

您可以在電子郵件設計工具中為連結加底線，並選取其顏色和目標。

1. 在插入連結的元件中，選取連結的標籤文字。

1. 在元件設定中，勾選 **[!UICONTROL Underline link]** 將連結的標籤文字加上底線。

   ![](assets/stylelinks-selecttext.png)

1. 若要選取將開啟您連結的瀏覽內容，請選取 **[!UICONTROL Target]**.

   ![](assets/stylelinks-target.png)

1. 若要變更連結的顏色，請按一下 **[!UICONTROL Link color]**.

   ![](assets/stylelinks-colorpicker.png)

1. 選擇所需的顏色。

   ![](assets/stylelinks-colorchanged.png)

1. 儲存您的變更。

## 新增內嵌樣式屬性 {#adding-inline-styling-attributes}

在「電子郵件設計工具」介面中，當您選取元素並在側面板顯示其設定時，可以自訂該特定元素的內嵌屬性及其值。

1. 在內容中選取元素。
1. 在側面板上，查找 **[!UICONTROL Styles Inline]** 設定。

   ![](assets/email_designer_inlineattributes.png)

1. 修改現有屬性的值，或使用 **+** 按鈕。 您可以新增任何與CSS相容的屬性和值。

樣式隨後會套用至選取的元素。 如果子元素未定義特定樣式屬性，則會繼承父元素的樣式。
