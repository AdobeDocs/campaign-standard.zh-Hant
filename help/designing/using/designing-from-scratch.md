---
title: '從頭設計電子郵件 '
seo-title: '從頭設計電子郵件 '
description: '從頭設計電子郵件 '
seo-description: 瞭解如何在電子郵件設計工具中從頭開始設計電子郵件內容。
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
source-git-commit: 51d80fc9c683e39b9d08ba7d36b76b71a9dd1e8c

---


# 從頭設計電子郵件 {#designing-an-email-content-from-scratch}

瞭解如何掌握電子郵件內容版本。 使用電子郵件設計工具，您可以建立電子郵件和範本，不論是否使用您自己預先定義的內容。

## 建立電子郵件的關鍵步驟 {#key-steps-to-create-your-email}

以下是使用電子郵件設計工具從頭開始建立和設計電子郵件內容的主要步驟：

1. 建立電子郵件並開啟其內容。
1. 新增結構元件以塑造電子郵件。 請參閱 [編輯電子郵件結構](#defining-the-email-structure)。
1. 在結構元件中插入內容元件和片段。 請參 [閱新增片段和內容元件](#defining-the-email-structure)。
1. 新增影像並編輯電子郵件的文字。 請參 [閱插入影像](../../designing/using/images.md#inserting-images)。
1. 新增個人化欄位、連結等，以個人化您的電子郵件。 請參 [閱插入個人化欄位](../../designing/using/personalization.md#inserting-a-personalization-field)、 [插入連結](../../designing/using/links.md#inserting-a-link)[和定義電子郵件中的動態內容](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)。
1. 定義您電子郵件的主旨行。 請參 [閱個人化電子郵件的主旨行](../../designing/using/subject-line.md#defining-the-subject-line-of-an-email)。
1. 預覽您的電子郵件。
1. 儲存您的內容，並在確定您已定義對象並正確排程傳送後繼續處理訊息。

您也可以檢視此簡 [介影片](https://video.tv.adobe.com/v/22771/?autoplay=true&hidetitle=true&captions=chi_hant)。

>[!NOTE]
>
>為避免從頭開始設計電子郵件內容，您可以使用現成可用的內容範本。 如需詳細資訊，請參閱「內 [容範本」](../../designing/using/using-reusable-content.md#content-templates)。

### 定義電子郵件結構 {#defining-the-email-structure}

電子郵件設計工具可讓您輕鬆定義電子郵件的結構。 透過使用簡單的拖放動作新增和移動結構元素，您可以在數秒內設計電子郵件的形狀。

要編輯電子郵件的結構：

1. 開啟現有內容或建立新的電子郵件內容。
1. 選取 **[!UICONTROL Structure components]** 左側的 **+** 圖示以存取。

   ![](assets/email_designer_structure.png)

1. 拖放您塑造電子郵件形狀所需的結構元件。

   ![](assets/email_designer_structure_components.png)

   在放置結構元件之前，藍線會實體化其確切位置。 您可以將它放在任何其他元件之上、之間或之下，但不能放在內部。

   >[!NOTE]
   >
   >一旦置入電子郵件中，您就無法移動或移除元件，除非其中已有內容元件或片段。

1. 多個由一個或多個列組成的結構元件可用。

   選取 **[!UICONTROL n:n column]** 元件以定義您選擇的欄數（介於3和10之間）。 您也可以移動每欄底部的箭頭來定義每欄的寬度。

   ![](assets/email_designer_n-n-column.png)

   >[!NOTE]
   >
   >每個列大小不能低於結構元件總寬度的10%。 您無法刪除非空的欄。

定義結構後，您就可以將內容片段和元件新增至電子郵件。

### 使用內容元件 {#about-content-components}

內容元件是原始的空白元件，放入電子郵件後，您就可以編輯這些元件。

您可以在結構元件中新增任意數量的內容元件。 也可將它們在結構元件內或移動到另一個結構元件。

以下是「電子郵件設計器」中可用元件的清單：

- **[!UICONTROL Button]**

   如果您需要使用多個按鈕，而不是從頭開始編輯每個按鈕，則可使用內容相關工 **[!UICONTROL Button]** 具列來複製元件。

   您也可以將按鈕儲存至可重複使用的片段。 如需詳細資訊，請參 [閱「建立內容片段](../../designing/using/using-reusable-content.md#creating-a-content-fragment) 」 [和「將內容儲存為片段」](../../designing/using/using-reusable-content.md#saving-content-as-a-fragment)。

1. 選擇 **[!UICONTROL Fallback view]** 以在電子郵件設計器中顯示備援影像。

- **[!UICONTROL Text]**

   使用此元件在您的電子郵件中插入文字。 您可以調整文字的顏色、樣式和大小(在 **[!UICONTROL Component Settings]**)。

- **[!UICONTROL Divider]**

   使用此元件在電子郵件中插入分界線。 可以在中選擇分行的顏色、樣式和大小 **[!UICONTROL Component Settings]**。

- **[!UICONTROL Html]**

   使用此元件可複製並貼上現有HTML的不同部分。 這可讓您建立免費的模組化HTML元件。

   >[!NOTE]
   >
   >免費的HTML元件可以編輯，但選項有限。 如果未內嵌所有樣式，請務必在HTML程式碼的 **head** （標題）區段中新增正確的CSS，否則電子郵件將無法回應。 使用按 **[!UICONTROL Preview]** 鈕來測試內容的回應速度(請參閱 [預覽訊息](../../sending/using/previewing-messages.md))。

   為了讓外部內容與電子郵件設計人員相容，Adobe建議從頭開始建立訊息，並將內容從您現有的電子郵件複製到片段和元件。

   當您有無法重新建立的內容時，您可以使用內容元件從原始電子郵件複製並貼上HTML **[!UICONTROL Html]** 程式碼。 繼續之前，請務必熟悉HTML。

   <!-- A full example is presented below. -->

   >[!NOTE]
   >
   >新內容不會是原始電子郵件的完整副本，但下列步驟會引導您建立盡可能接近的訊息。

   **複製內容之前**

   1. 在原始電子郵件中，從您要傳送的每封電子郵件中識別可重複使用的區段。
   1. 儲存您要使用的所有影像和資產。
   1. 如果您熟悉HTML，請將原始HTML內容分割為不同的部分。

- **[!UICONTROL Video]**

   使用此元件將影片插入您的電子郵件中。

   將視訊元件插入電子郵件的結構元件，並在中輸入視訊連結 **[!UICONTROL Component Settings]**。

- **[!UICONTROL Image]**

   使用此元件將影像插入您的電子郵件中。

   將影像元件插入結構元件，然後按一下「瀏覽」，從電腦上傳影像檔案。

- **[!UICONTROL Social]**

   使用此元件，在電子郵件中插入社交媒體頁面的連結。 您可以選取要顯示的連結及其圖示大小 **[!UICONTROL Component Settings]**。

- **[!UICONTROL Carousel]**

   1. 將元件拖放 **[!UICONTROL Carousel]** 到結構元件內。
   1. 瀏覽以從您的電腦選取影像。
   ![](assets/des_carousel_browse.png)

   1. 在窗格 **[!UICONTROL Settings]** 中，設定您要在轉盤中的縮圖數。
   1. 從您的電腦選擇備援影像。
   ![](assets/des_carousel_fallback.png)

   轉盤元件與所有電子郵件程式不相容。 當電子郵件不支援轉盤時，上傳備援以顯示影像。

   >[!NOTE]
   >
   >轉盤元件與下列電子郵件平台相容：Apple Mail 7、Apple Mail 8、Outlook 2011 for Mac、Outlook 2016 for Mac、Mozilla Thunderbird、iPad和iPad mini iOS、iPhone iOS、Android、AOL（Chrome、Firefox和Safari）。

**相關主題**:

- [建立電子郵件](../../channels/using/creating-an-email.md)
- [在訊息中選取對象](../../audiences/using/selecting-an-audience-in-a-message.md)
- [排程訊息](../../sending/using/about-scheduling-messages.md)
- [預覽訊息](../../sending/using/previewing-messages.md)
- [電子郵件轉換](../../sending/using/email-rendering.md)
