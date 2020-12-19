---
solution: Campaign Standard
product: campaign
title: 管理電子郵件樣式
description: 瞭解如何在電子郵件設計工具中管理電子郵件樣式。
audience: designing
content-type: reference
topic-tags: editing-email-content
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '1052'
ht-degree: 1%

---


# 管理電子郵件樣式 {#managing-styles}


在「電子郵件設計器」中，選取元素時，會在&#x200B;**[!UICONTROL Settings]**&#x200B;窗格中顯示特定於所選內容類型的選項。 您可以使用這些選項輕鬆變更電子郵件的樣式。

## 選擇元素{#selecting-an-element}

要在「電子郵件設計器」介面中選擇元素，您可以：

* 直接在電子郵件中按一下，
* 或瀏覽左側&#x200B;**Palette**&#x200B;選項中可用的結構樹。

![](assets/des_tree_structure.png)

瀏覽結構樹可讓您進行更精確的選擇。 您可以選擇下列任一項：

* 整個結構，
* 組成結構元件的列之一，
* 或僅包含位於欄內的元件。

![](assets/des_tree_structure_selection.png)

要選擇列，您還可以執行以下操作：

1. 選擇結構元件（直接在電子郵件中或使用左側&#x200B;**調色板**&#x200B;的結構樹）。
1. 在&#x200B;**上下文工具列**&#x200B;中，按一下&#x200B;**[!UICONTROL Select a column]**&#x200B;選擇所需列。

請參閱[本節](#example--adjusting-vertical-alignment-and-padding)中的範例。

## 調整樣式設定{#adjusting-style-settings}

1. 在電子郵件中選取元素。 有關詳細資訊，請參閱[選擇元素](#selecting-an-element)。
1. 根據您的需求調整設定。 每個選取的元素都提供不同的設定集。

   您可以插入背景、變更大小、修改水準或垂直對齊、管理顏色、新增[填補或邊界](#selecting-an-element)等。

   若要這麼做，請使用&#x200B;**[!UICONTROL Settings]**&#x200B;窗格或[中顯示的選項來新增內嵌樣式屬性](#adding-inline-styling-attributes)。

   ![](assets/des_settings_pane.png)

1. 儲存您的內容。

## 調整間距和邊界{#about-padding-and-margin}

電子郵件設計器介面可讓您快速調整填補空間和邊界設定。

**[!UICONTROL Padding]**:此設定可讓您管理位於元素邊框內的空間。

![](assets/des_padding.png)

例如：

* 使用填補功能來設定影像左側和右側的邊界。
* 使用上下填充為&#x200B;**[!UICONTROL Text]**&#x200B;或&#x200B;**[!UICONTROL Divider]**&#x200B;元件添加更多間距。
* 要設定結構元素內各列之間的邊界，請定義每列的間距。

**[!UICONTROL Margin]**:此設定可讓您管理元素邊框與下一個元素之間的間距。

![](assets/des_margin.png)

>[!NOTE]
>
>根據您的選擇（結構元件、欄或內容元件），結果將不相同。 Adobe建議在欄層級設定&#x200B;**[!UICONTROL Padding]**&#x200B;和&#x200B;**[!UICONTROL Margin]**&#x200B;參數。

對於&#x200B;**[!UICONTROL Padding]**&#x200B;和&#x200B;**[!UICONTROL Margin]**，按一下鎖定表徵圖可中斷頂部和底部或右和左參數之間的同步。 這可讓您個別調整每個參數。

![](assets/des_padding_lock_icon.png)

## 樣式對齊{#about-alignment}

* **文字對齊**:將滑鼠游標置於某些文字上，然後使用內容相關工具列來對齊。

   ![](assets/des_text_alignment.png)

* **水準** 對齊功能可套用至文字、影像和按鈕——目前不適用於 **[!UICONTROL Divider]** 和元 **[!UICONTROL Social]** 件。

   ![](assets/des_horizontal_alignment.png)

* 要設定&#x200B;**垂直對齊**，請在結構元件內選擇一個列，然後從「設定」窗格中選擇一個選項。

   ![](assets/des_set_vertical_alignment.png)

## 設定背景{#about-backgrounds}

>[!CONTEXTUALHELP]
>id="ac_edition_backgroundimage"
>title="背景設定"
>abstract="電子郵件設計工具可讓您個人化內容的背景色彩或背景影像。請注意，並非所有電子郵件客戶都支援背景影像。"
>additional-url="https://docs.google.com/spreadsheets/d/1TLo62YKm3tThUWDOIliCQFWs3dpNjpDfw6DdTr1oGOw/edit#gid=0" text="其他資訊"

在使用電子郵件設計工具設定背景時，Adobe建議您：

1. 如果您的設計需要，請將背景顏色套用至電子郵件的正文。
1. 在大多數情況下，請在欄層級設定背景顏色。
1. 請盡量不要在影像或文字元件上使用背景色彩，因為這些色彩很難管理。

以下是您可使用的可用背景設定。

* 為整封電子郵件設定&#x200B;**[!UICONTROL Background color]**。 請務必在導覽樹狀結構中選取可從左側浮動視窗存取的內文設定。

   ![](assets/des_background_body.png)

* 通過選擇&#x200B;**[!UICONTROL Viewport background color]**&#x200B;為所有結構元件設定相同的背景顏色。 此選項可讓您從背景顏色中選取不同的設定。

   ![](assets/des_background_viewport.png)

* 為每個結構元件設定不同的背景顏色。 在導覽樹狀結構中，從左側的浮動視窗中選取可存取的結構，以僅將特定背景顏色套用至該結構。

   ![](assets/des_background_structure.png)

   請確定您未設定檢視區背景顏色，因為它可能會隱藏結構背景顏色。

* 為結構元件的內容設定&#x200B;**[!UICONTROL Background image]**。

   ![](assets/des_background_image.png)

   >[!NOTE]
   >
   >有些電子郵件程式不支援背景影像。 不支援時，會改用列背景顏色。 請務必選取適當的備援背景顏色，以防影像無法顯示。

* 在欄層級設定背景顏色。

   ![](assets/des_background_column.png)

   >[!NOTE]
   >
   >這是最常見的使用案例。 Adobe建議在欄層級設定背景顏色，因為這樣在編輯整個電子郵件內容時，可提供更大的彈性。

   您也可以在欄層級設定背景影像，但很少使用。

### 範例：調整垂直對齊和間距{#example--adjusting-vertical-alignment-and-padding}

要在由三列組成的結構元件中調整填充和垂直對齊。 要執行此操作，請遵循下列步驟：

1. 直接在電子郵件中或使用左側&#x200B;**調色板**&#x200B;中的結構樹選擇結構元件。
1. 在&#x200B;**上下文工具欄**&#x200B;中，按一下&#x200B;**[!UICONTROL Select a column]**&#x200B;並選擇要編輯的工具欄。 也可以從結構樹中選取它。

   ![](assets/des_selecting_column.png)

   該列的可編輯參數顯示在右側的&#x200B;**[!UICONTROL Settings]**&#x200B;窗格中。

1. 在&#x200B;**[!UICONTROL Vertical alignment]**&#x200B;下，選擇&#x200B;**[!UICONTROL Up]**。

   ![](assets/des_vertical_alignment.png)

   內容元件會顯示在欄的頂端。

1. 在&#x200B;**[!UICONTROL Padding]**&#x200B;下，定義列內的頂部填充。 按一下鎖定表徵圖以中斷與底部填充的同步。

   定義該列的左邊距和右邊距。

   ![](assets/des_adjusting_padding.png)

1. 同樣地，繼續調整其他列的對齊和間距。

   ![](assets/des_adjusting_columns.png)

1. 儲存您的變更。

## 樣式連結{#about-styling-links}

您可以在電子郵件設計器中為連結加下划線，並選擇其顏色和目標。

1. 在插入連結的元件中，選擇連結的標籤文本。

1. 在元件設定中，選中&#x200B;**[!UICONTROL Underline link]**&#x200B;可將連結的標籤文本加底線。

   ![](assets/stylelinks-selecttext.png)

1. 要選擇將開啟連結的瀏覽上下文，請選擇&#x200B;**[!UICONTROL Target]**。

   ![](assets/stylelinks-target.png)

1. 若要變更連結的顏色，請按一下&#x200B;**[!UICONTROL Link color]**。

   ![](assets/stylelinks-colorpicker.png)

1. 選擇您需要的顏色。

   ![](assets/stylelinks-colorchanged.png)

1. 儲存您的變更。

## 添加內嵌樣式屬性{#adding-inline-styling-attributes}

在「電子郵件設計器」介面中，當您選取元素並在側面板顯示其設定時，可以自訂該特定元素的內嵌屬性及其值。

1. 選取內容中的元素。
1. 在側面板上，查找&#x200B;**[!UICONTROL Styles Inline]**&#x200B;設定。

   ![](assets/email_designer_inlineattributes.png)

1. 修改現有屬性的值，或使用&#x200B;**+**&#x200B;按鈕添加新屬性。 您可以新增任何與CSS相容的屬性和值。

樣式隨即會套用至選取的元素。 如果子元素沒有定義特定的樣式屬性，則會繼承父元素的樣式。
