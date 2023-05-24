---
title: 編輯純文字檔案、HTML和移動電子郵件格式
description: 發現純文字檔案和HTML模式
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

# 編輯純文字檔案、HTML和移動電子郵件格式 {#plain-text-and-html-modes}

電子郵件設計器使您能夠編輯電子郵件的幾種呈現。 您可以生成電子郵件的文本版本、編輯電子郵件的HTML源並設計用於移動視圖的電子郵件。

## 生成電子郵件的文本版本 {#generating-a-text-version-of-the-email}

預設情況下， **[!UICONTROL Plain text]** 自動生成電子郵件版本並與 **[!UICONTROL Edit]** 。

添加到HTML版本的個性化欄位和內容塊也與純文字檔案版本同步。

>[!NOTE]
>
>要在純文字檔案版本中使用內容塊，請確保它們不包含HTML代碼。

要使純文字檔案版本與HTML版本不同，可通過按一下 **[!UICONTROL Sync with HTML]** 從 **[!UICONTROL Plain text]** 電子郵件的視圖。

![](assets/email_designer_textversion.png)

然後，您可以視需要編輯純文字版本。

>[!NOTE]
>
>如果編輯 **[!UICONTROL Plain text]** 同步時的版本，下次啟用時 **[!UICONTROL Sync with HTML]** 選項，在純文字檔案版本中所做的所有更改將替換為HTML版本。 中所做的更改 **[!UICONTROL Plain text]** 視圖無法反映在 **[!UICONTROL HTML]** 的子菜單。

## 在HTML中編輯電子郵件內容源 {#editing-an-email-content-source-in-html}

對於最高級的用戶和調試，您可以直接在HTML中查看和編輯電子郵件內容。

編輯電子郵件的HTML版本有兩種方法：

* 選擇 **[!UICONTROL Edit]** > **[!UICONTROL HTML]** 開啟整個電子郵件的HTML版本。

   ![](assets/email_designer_html1.png)

* 在WYSIWYG介面中，選擇一個元素，然後按一下 **[!UICONTROL Source code]** 表徵圖

   只顯示選定元素的源。 如果所選元素是 **[!UICONTROL HTML]** 內容元件。 其他元件處於只讀模式，但仍可以以電子郵件的完整HTML版本進行編輯。

   ![](assets/email_designer_html2.png)

如果修改代碼的HTML，則電子郵件的響應可能會中斷。 確保使用test **[!UICONTROL Preview]** 按鈕 請參閱「[預覽訊息](../../sending/using/previewing-messages.md)」。

## 設計用於移動渲染的電子郵件 {#switching-to-mobile-view}

您可以通過單獨編輯移動顯示的所有樣式選項來微調電子郵件的響應設計。 例如，您可以調整邊距和填充，使用較小或較大的字型大小，更改按鈕，或應用特定於電子郵件移動版本的不同背景顏色。

所有樣式選項均可在移動視圖中使用。 「電子郵件設計器」樣式設定以前在此頁上顯示。

1. 建立電子郵件並開始編輯內容。 有關此的詳細資訊，請參閱 [從頭設計電子郵件內容](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)。
1. 要訪問專用移動視圖，請選擇 **[!UICONTROL Switch to mobile view]** 按鈕

   ![](assets/email_designer_mobile_view_switch.png)

   將顯示電子郵件的移動版本。 它包含在案頭視圖中定義的所有元件和樣式。

1. 獨立編輯所有樣式設定，如背景顏色、對齊方式、填充、邊距、字型系列、文本顏色等。

   ![](assets/email_designer_mobile_view.png)

1. 當編輯移動視圖中的任何樣式設定時，這些修改僅應用於移動顯示。

   例如，減小影像大小，添加綠色背景並更改移動視圖中的填充。

   ![](assets/email_designer_mobile_view_change.png)

1. 在移動設備上顯示時，可以隱藏元件。 要執行此操作，請選擇 **[!UICONTROL Show only on desktop devices]** 從 **[!UICONTROL Display options]**。

   您也可以選擇在案頭設備上隱藏此元件，這意味著它將僅顯示在移動設備上。 要執行此操作，請選擇 **[!UICONTROL Show only on mobile devices]**。

   例如，此選項允許您在移動設備上顯示特定影像，在案頭設備上顯示其他影像。

   可以從移動或案頭視圖中設定此選項。

   ![](assets/email_designer_mobile_hide.png)

1. 再次按一下 **[!UICONTROL Switch to mobile view]** 按鈕以返回標準案頭視圖。 您剛做的樣式更改不會反映。

   ![](assets/email_designer_mobile_view_desktop_no-change.png)

   >[!NOTE]
   >
   >唯一的例外是 **[!UICONTROL Style inline]** 的子菜單。 任何樣式內聯設定更改也應用於標準案頭視圖。

1. 對電子郵件的結構或內容所做的任何其他更改，如文本編輯、上載新影像、添加新元件等。 也應用於標準視圖。

   例如，切換回移動視圖，編輯一些文本並替換影像。

   ![](assets/email_designer_mobile_view_change_content.png)

1. 再次按一下 **[!UICONTROL Switch to mobile view]** 按鈕以返回標準案頭視圖。 這些變化被反映。

   ![](assets/email_designer_mobile_view_desktop_content-change.png)

1. 在移動視圖中刪除樣式會使您返回到在案頭模式下應用的樣式。

   例如，在移動視圖中，將綠色背景顏色應用於按鈕。

   ![](assets/email_designer_mobile_view_background_mobile.png)

1. 切換到案頭視圖，並將灰色背景應用於同一按鈕。

   ![](assets/email_designer_mobile_view_background_desktop.png)

1. 再次切換到移動視圖，現在禁用 **[!UICONTROL Background color]** 的子菜單。

   ![](assets/email_designer_mobile_view_background_mobile_disabled.png)

   案頭視圖中定義的背景顏色現在已應用：它變灰（不是空白）。

   唯一的例外是 **[!UICONTROL Border color]** 的子菜單。 在移動視圖中禁用時，即使在案頭視圖中定義了邊框顏色，也不再應用邊框。

>[!NOTE]
>
>中的移動視圖不可用 [碎片](../../designing/using/using-reusable-content.md#about-fragments)。
