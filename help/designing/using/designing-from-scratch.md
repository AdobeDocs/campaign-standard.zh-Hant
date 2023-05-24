---
title: 從頭開始設計電子郵件
description: 瞭解如何在電子郵件設計器中從頭開始設計電子郵件內容。
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: User
level: Beginner
exl-id: 052d24b7-d3e0-41d7-8b2c-92bd3addb3a2
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '1239'
ht-degree: 23%

---

# 從頭開始設計電子郵件 {#designing-an-email-content-from-scratch}

瞭解如何掌握電子郵件內容版本。 使用電子郵件設計器，您可以建立電子郵件和模板，這些電子郵件和模板以您自己的預定義內容開始或不包含。

以下是使用電子郵件設計器從頭建立和設計電子郵件內容的主要步驟：

1. 建立電子郵件並開啟其內容。
1. 添加結構元件以塑造電子郵件。 請參閱 [編輯電子郵件結構](#defining-the-email-structure)。
1. 在結構元件中插入內容元件和片段。 請參閱 [添加片段和內容元件](#defining-the-email-structure)。
1. 添加影像並編輯電子郵件文本。 請參閱 [插入影像](../../designing/using/images.md#inserting-images)。
1. 通過添加個性化欄位、連結等來個性化您的電子郵件。 請參閱 [插入個性化欄位](../../designing/using/personalization.md#inserting-a-personalization-field)。 [插入連結](../../designing/using/links.md#inserting-a-link) 和 [在電子郵件中定義動態內容](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)。
1. 定義電子郵件的主題行。 請參閱 [個性化電子郵件的主題行](../../designing/using/subject-line.md#defining-the-subject-line-of-an-email)。
1. 預覽您的電子郵件.
1. 保存您的內容，並在確保定義了受眾並正確安排發送後繼續處理您的消息。

您也可以查看此 [簡介視頻](https://video.tv.adobe.com/v/22771/?autoplay=true&hidetitle=true)。

>[!NOTE]
>
>為避免從頭開始設計電子郵件內容，您可以使用現成內容模板。 有關此的詳細資訊，請參閱 [內容模板](../../designing/using/using-reusable-content.md#content-templates)。

## 定義電子郵件結構 {#defining-the-email-structure}

>[!CONTEXTUALHELP]
>id="ac_structure_components"
>title="關於結構元件"
>abstract="結構元件會定義電子郵件的版面。"

>[!CONTEXTUALHELP]
>id="ac_edition_columns"
>title="定義電子郵件欄"
>abstract="電子郵件設計工具可讓您透過定義欄結構輕鬆定義電子郵件的版面。"

電子郵件設計工具可讓您輕鬆定義電子郵件的結構。通過使用簡單的拖放操作添加和移動結構元素，您可以在幾秒鐘內設計電子郵件的形狀。

要編輯電子郵件的結構：

1. 開啟現有內容或建立新電子郵件內容。
1. 訪問 **[!UICONTROL Structure components]** 選擇 **+** 表徵圖。

   ![](assets/email_designer_structure.png)

1. 拖放您需要塑造電子郵件形狀的結構元件。

   ![](assets/email_designer_structure_components.png)

   在放置結構元件之前，一條藍線將材料化其確切位置。 可以將其放在上方、任何其它元件之間或下方，但不能放在內部。

   >[!NOTE]
   >
   >請注意，並非所有電子郵件程式都與欄堆疊相容。當不受支援時，將不會堆疊欄。
   >
   >一旦放入電子郵件中，您就不能移動或刪除元件，除非其中已經放有內容元件或片段。

1. 多個由一個或多個列組成的結構元件可用。

   選擇 **[!UICONTROL n:n column]** 定義所選列數（介於3和10之間）的元件。 您也可以移動每個欄底部的箭頭來定義其寬度。

   ![](assets/email_designer_n-n-column.png)

   >[!NOTE]
   >
   >每個欄的大小不能小於結構元件總寬度的 10%。如果欄不是空的，則無法移除。

定義結構後，您就可以將內容片段和元件添加到電子郵件中。

## 使用預覽文字 {#preheader}

>[!CONTEXTUALHELP]
>id="ac_edition_preheader"
>title="使用預覽文字"
>abstract="預覽文字讓您設定簡短的摘要文字，這會為您的電子郵件實現更高的開啟率。"

前標是短的摘要文本，在查看收件箱中的電子郵件時，它跟在主題行後。 預報頭提供較高的開啟率。

選擇 **[!UICONTROL Preheader]** 編輯框並完成內容。

![](assets/email_designer_preheader.png)

可以添加 **[!UICONTROL Content block]**&#x200B;的 **[!UICONTROL Dynamic content]** 或 **[!UICONTROL Personalization fields]** 的子菜單。

>[!NOTE]
>
>請注意，並非所有電子郵件程式都與預覽文字相容。當不受支援時，將不會顯示預覽文字。

## 使用內容元件 {#about-content-components}

>[!CONTEXTUALHELP]
>id="ac_content_components"
>title="關於內容元件"
>abstract="內容元件指可進行編輯以建立電子郵件的空白內容預留位置。"

內容元件是原始的空元件，一旦放入電子郵件中，您就可以編輯這些元件。

可以在結構元件中添加任意數量的內容元件。 也可將它們移動到結構元件或其它結構元件中。

以下是電子郵件設計器中可用元件的清單：

### **[!UICONTROL Button]**

如果需要使用多個按鈕，而不是從頭開始編輯每個按鈕，則可以複製 **[!UICONTROL Button]** 元件。

還可以將按鈕保存到可重複使用的片段中。 有關此的詳細資訊，請參閱 [建立內容片段](../../designing/using/using-reusable-content.md#creating-a-content-fragment) 和 [將內容另存為片段](../../designing/using/using-reusable-content.md#saving-content-as-a-fragment)。

選擇 **[!UICONTROL Fallback view]** 在電子郵件設計器中顯示回退影像。

### **[!UICONTROL Text]**

使用此元件在電子郵件中插入文本。 您可以調整文本的顏色、樣式和大小 **[!UICONTROL Component Settings]**。

### **[!UICONTROL Divider]**

使用此元件在電子郵件中插入分隔線。 可以在中選擇斷線的顏色、樣式和大小 **[!UICONTROL Component Settings]**。

### **[!UICONTROL HTML]**

使用此元件可複製貼上現有HTML的不同部分。 這使您能夠建立免費的模組化HTML元件。

>[!NOTE]
>
>可編輯自由HTML元件，其選項有限。 如果所有樣式都未內置，請確保在 **頭** HTML碼的部分，否則電子郵件將無法響應。 使用 **[!UICONTROL Preview]** 按鈕以test內容的響應(請參閱 [預覽消息](../../sending/using/previewing-messages.md))。

要使外部內容與電子郵件設計器相容，Adobe建議從頭開始建立郵件，並將現有電子郵件的內容複製到碎片和元件中。

當您有無法重新建立的內容時，可以使用 **[!UICONTROL Html]** 內容元件。 在繼續之前，請確保您熟悉HTML。

>[!NOTE]
>
>新內容將不是原始電子郵件的準確副本，但以下步驟將指導您完成盡可能接近的郵件的建立。

**複製內容之前**

1. 在原始電子郵件中，從您將要發送的每封電子郵件中唯一的部分中確定可重複使用的部分。
1. 保存您要使用的所有映像和資產。
1. 如果您熟悉HTML，請將原始HTML內容拆分為不同的部分。

### 視訊 {#video-settings}

>[!CONTEXTUALHELP]
>id="ac_edition_video"
>title="影片設定"
>abstract="使用此元件即可在您的電子郵件中插入影片。請注意，影片並非在所有電子郵件用戶端上都適用。我們建議設定備援影像。"
>additional-url="https://www.emailonacid.com/blog/article/email-development/a_how_to_guide_to_embedding_html5_video_in_email/" text="額外資訊"

將視頻元件插入電子郵件的結構元件，並在 **[!UICONTROL Component Settings]**。

>[!NOTE]
>
>請注意，並非所有電子郵件程式都與視訊相容。當不受支援時，將會顯示遞補內容。

### 影像

使用此元件在電子郵件中插入影像。

將影像元件插入結構元件，然後按一下瀏覽以從電腦上載影像檔案。

### **[!UICONTROL Social]**

使用此元件在電子郵件中插入指向社交媒體頁面的連結。 您可以選擇要顯示的連結及其表徵圖的大小 **[!UICONTROL Component Settings]**。

### 輪播 {#carousel-settings}

>[!CONTEXTUALHELP]
>id="ac_edition_carousel"
>title="輪播設定"
>abstract="了解如何在您的內容中插入和設定輪播。請注意，輪播並非在所有電子郵件用戶端上都適用，如果不支援輪播，則會顯示備援影像。"

1. 拖放 **[!UICONTROL Carousel]** 構件內部的元件。
1. 瀏覽以從您的電腦中選擇影像。

   ![](assets/des_carousel_browse.png)

1. 從 **[!UICONTROL Settings]** 框中，設定要在旋轉傳送過程中顯示的縮略圖數。
1. 從電腦中選擇回退映像。

   ![](assets/des_carousel_fallback.png)

旋轉傳送元件與所有電子郵件程式不相容。 當電子郵件中不支援傳送帶時，上載回退以顯示影像。

>[!NOTE]
>
>旋轉傳送元件與以下電子郵件平台相容：Apple郵件7、Apple郵件8、MacOutlook 2011、MacOutlook 2016、Mozilla Thunderbird、iPad和iPad迷你iOS、iPhoneiOS、安卓、AOL（Chrome、火狐和Safari）。

**相關主題**：

- [建立電子郵件](../../channels/using/creating-an-email.md)
- [在訊息中選取對象](../../audiences/using/selecting-an-audience-in-a-message.md)
- [排程訊息](../../sending/using/about-scheduling-messages.md)
- [預覽訊息](../../sending/using/previewing-messages.md)
- [電子郵件轉譯](../../sending/using/email-rendering.md)
