---
title: 管理電子郵件樣式
description: 瞭解如何在電子郵件設計工具中管理電子郵件樣式。
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
ht-degree: 26%

---

# 管理電子郵件樣式 {#managing-styles}


在電子郵件設計工具中，選取元素時，所選內容型別的數個特定選項會顯示在 **[!UICONTROL Settings]** 窗格。 您可以使用這些選項輕鬆變更電子郵件的樣式。

## 選取元素 {#selecting-an-element}

若要在電子郵件設計工具介面中選取元素，您可以：

* 直接在電子郵件中按一下
* 或瀏覽左側選項中可用的結構樹 **浮動視窗**.

![](assets/des_tree_structure.png)

瀏覽結構樹可讓您進行更精確的選取。 您可以選取：

* 整個結構元件，
* 構成結構元件的其中一個欄
* 或只有位於欄內的元件。

![](assets/des_tree_structure_selection.png)

若要選取欄，您也可以執行下列動作：

1. 選取結構元件（直接在電子郵件中，或使用左側可用的結構樹） **浮動視窗**)。
1. 從 **內容工具列**，按一下 **[!UICONTROL Select a column]** 以選擇所需的欄。

請參閱中的範例 [本節](#example--adjusting-vertical-alignment-and-padding).

## 調整樣式設定 {#adjusting-style-settings}

1. 選取電子郵件中的元素。 有關詳細資訊，請參閱 [選取元素](#selecting-an-element).
1. 根據您的需求調整設定。 每個選取的元素提供一組不同的設定。

   您可以插入背景、變更大小、修改水平或垂直對齊、管理顏色、新增 [邊框間距或邊界](#selecting-an-element)、等等。

   要執行此操作，請使用 **[!UICONTROL Settings]** 窗格或 [新增內嵌樣式屬性](#adding-inline-styling-attributes).

   ![](assets/des_settings_pane.png)

1. 儲存您的內容。

## 調整邊框間距和邊界 {#about-padding-and-margin}

電子郵件設計工具介面可讓您快速調整邊框間距和邊界設定。

**[!UICONTROL Padding]**：此設定可讓您管理元素邊框內的空間。

![](assets/des_padding.png)

例如：

* 使用內距來設定影像左右兩側的邊界。
* 使用頂端和底部內距來增加間距 **[!UICONTROL Text]** 或 **[!UICONTROL Divider]** 元件。
* 若要設定結構元素內各欄之間的邊界，請定義各欄的邊距。

**[!UICONTROL Margin]**：此設定可讓您管理元素邊框與下一個元素之間的間距。

![](assets/des_margin.png)

>[!NOTE]
>
>根據您的選取（結構元件、欄或內容元件），結果將不同。 Adobe建議設定 **[!UICONTROL Padding]** 和 **[!UICONTROL Margin]** 欄層級的引數。

針對兩者 **[!UICONTROL Padding]** 和 **[!UICONTROL Margin]**，按一下鎖定圖示以中斷上下或左右引數之間的同步化。 這可讓您分別調整每個引數。

![](assets/des_padding_lock_icon.png)

## 樣式對齊方式 {#about-alignment}

* **文字對齊方式**：將滑鼠游標移至某些文字上，並使用內容工具列對齊文字。

  ![](assets/des_text_alignment.png)

* **水準對齊方式** 可套用至文字、影像和按鈕 — 目前不可套用至 **[!UICONTROL Divider]** 和 **[!UICONTROL Social]** 元件。

  ![](assets/des_horizontal_alignment.png)

* 要設定 **垂直對齊方式**，選取結構元件內的欄，然後從「設定」窗格中選擇選項。

  ![](assets/des_set_vertical_alignment.png)

## 設定背景 {#about-backgrounds}

>[!CONTEXTUALHELP]
>id="ac_edition_backgroundimage"
>title="背景設定"
>abstract="電子郵件設計工具讓您將內容的背景顏色或背景影像個人化。請注意，並非所有電子郵件用戶端都支援背景影像。"

在使用電子郵件設計工具設定背景時，Adobe 建議以下做法：

1. 為您的電子郵件內文套用背景顏色 (如果您的設計需要)。
1. 在大多數情況下，請在欄層級設定背景顏色。
1. 盡量不要在影像或文字元件上使用背景顏色，因為難以管理。

以下是您可以使用的可用背景設定。

* 設定 **[!UICONTROL Background color]** 整個電子郵件。 請務必在可從左側浮動視窗存取的導覽樹狀結構中選取內文設定。

  ![](assets/des_background_body.png)

* 選取「 」，為所有結構元件設定相同的背景顏色 **[!UICONTROL Viewport background color]**. 此選項可讓您從背景顏色中選取不同的設定。

  ![](assets/des_background_viewport.png)

* 為每個結構元件設定不同的背景顏色。在導覽樹狀結構中選取可從左側浮動視窗存取的結構，以僅將特定背景顏色套用至該結構。

  ![](assets/des_background_structure.png)

  確保您沒有設定檢視區的背景顏色，因為它可能會隱藏結構背景顏色。

* 設定 **[!UICONTROL Background image]** 結構元件的內容。

  ![](assets/des_background_image.png)

  >[!NOTE]
  >
  >某些電子郵件程式不支援背景影像。當不支援時，將改用列背景顏色。 確保選取合適的後備背景顏色，以防影像無法顯示。

* 在欄層級設定背景顏色。

  ![](assets/des_background_column.png)

  >[!NOTE]
  >
  >這是最常見的使用案例。Adobe 建議在欄層級設定背景顏色，因為這樣可以在編輯整個電子郵件內容時具有更大的彈性。

  您也可以在欄層級設定背景影像，但這很少使用。

### 範例：調整垂直對齊與邊框間距 {#example--adjusting-vertical-alignment-and-padding}

您想要調整由三欄組成的結構元件內的邊框間距和垂直對齊方式。 要執行此操作，請遵循下列步驟：

1. 直接在電子郵件中選取結構元件，或使用左側可用的結構樹 **浮動視窗**.
1. 從 **內容工具列**，按一下 **[!UICONTROL Select a column]** 並選擇要編輯的專案。 您也可以從結構樹中選取它。

   ![](assets/des_selecting_column.png)

   該欄可編輯的引數會顯示在 **[!UICONTROL Settings]** 窗格在右邊。

1. 在 **[!UICONTROL Vertical alignment]**，選取 **[!UICONTROL Up]**.

   ![](assets/des_vertical_alignment.png)

   內容元件會顯示在欄頂端。

1. 在 **[!UICONTROL Padding]**，定義欄內的頂端內距。 按一下鎖定圖示以中斷與底部邊框間距的同步。

   定義該欄的左右內距。

   ![](assets/des_adjusting_padding.png)

1. 以類似的方式調整其他欄的對齊方式和邊框間距。

   ![](assets/des_adjusting_columns.png)

1. 儲存您的變更。

## 樣式連結 {#about-styling-links}

您可以為連結加底線，然後在電子郵件設計工具中選取其顏色和目標。

1. 在插入連結的元件中，選取連結的標籤文字。

1. 在元件設定中，勾選「 」 **[!UICONTROL Underline link]** 將連結的標籤文字加底線。

   ![](assets/stylelinks-selecttext.png)

1. 若要選取要在哪個瀏覽內容中開啟您的連結，請選取 **[!UICONTROL Target]**.

   ![](assets/stylelinks-target.png)

1. 若要變更連結的顏色，請按一下 **[!UICONTROL Link color]**.

   ![](assets/stylelinks-colorpicker.png)

1. 挑選您需要的色彩。

   ![](assets/stylelinks-colorchanged.png)

1. 儲存您的變更。

## 新增內嵌樣式屬性 {#adding-inline-styling-attributes}

在電子郵件設計工具介面中，當您選取元素並在側面板上顯示其設定時，您可以自訂該特定元素的內嵌屬性及其值。

1. 選取內容中的元素。
1. 在側面板上，尋找 **[!UICONTROL Styles Inline]** 設定。

   ![](assets/email_designer_inlineattributes.png)

1. 修改現有屬性的值，或使用 **+** 按鈕。 您可以新增任何符合 CSS 的屬性和值。

然後，樣式會套用至選取的元素。 如果子元素沒有定義特定的樣式屬性，則繼承父元素的樣式。
