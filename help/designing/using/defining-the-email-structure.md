---
title: 定義電子郵件結構
seo-title: 定義電子郵件結構
description: 定義電子郵件結構
seo-description: 瞭解如何使用Campaign中的電子郵件設計工具來塑造電子郵件，並使用內容元件填入它們。
page-status-flag: 從未啓動
uuid: 6ec63f65-1425-4c28-84e8-b09574458 db3
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: design
content-type: reference
topic-tags: editing-email-content
discoiquuid: 207fdf6d-165a-41af-ad53-ba97 d3403 b62
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a12df43de55dedf388a397fbf4670d99e3ea7f3d

---


# Defining the email structure{#defining-the-email-structure}

## Editing the email structure {#editing-the-email-structure}

電子郵件設計人員可讓您輕鬆定義電子郵件的結構。透過簡單的拖放動作新增及移動結構元素，即可在數秒內設計電子郵件的形狀。

若要編輯電子郵件的結構：

1. 開啓現有內容或建立新的電子郵件內容。
1. Access the **[!UICONTROL Structure components]** by selecting the **+** icon on the left.

   ![](assets/email_designer_structure.png)

1. 拖放您需要的結構元件，以建立您的電子郵件格式。

   ![](assets/email_designer_structure_components.png)

   藍色線條會先重新整理結構元件的確切位置，然後再放下。您可以將它放置在任何其他元件之間或下方，但不能放在內部。

   >[!NOTE]
   >
   >置入電子郵件後，除非已有內容元件或置於內部，否則您無法移動或移除元件。

1. 可使用由一欄或多欄組成的數個結構元件。

   Select the **[!UICONTROL n:n column]** component to define the number of columns of your choice (between 3 and 10). 您也可以移動每欄底部的箭頭，定義每欄的寬度。

   ![](assets/email_designer_n-n-column.png)

   >[!NOTE]
   >
   >每個欄大小不能低於結構元件總寬度的10%以下。您無法移除非空白的欄。

在定義結構後，您可以將內容片段和元件新增至您的電子郵件。

## Adding fragments and content components {#adding-fragments-and-content-components}

透過電子郵件設計工具，在新增元件至電子郵件後，您可以定義其內容。若要這麼做，您必須在每個結構元件中新增元素。

There are two categories of content elements that you can use: **fragments** and **content components**.

### About fragments {#about-fragments}

片段是可重復使用的元件，可在一或多封電子郵件中參照。

若要在電子郵件設計工具中充分使用片段：

* 建立您自己的片段。See [Creating a content fragment](../../designing/using/defining-the-email-structure.md#creating-a-content-fragment) and [Saving content as a fragment](../../designing/using/defining-the-email-structure.md#saving-content-as-a-fragment).
* 您可以在電子郵件中多次使用它們。See [Inserting elements into an email](../../designing/using/defining-the-email-structure.md#inserting-elements-into-an-email).
* 當您編輯片段時，變更會同步化：會自動傳播至所有包含該片段的電子郵件(但尚未準備或傳送)。

新增至電子郵件時，預設會鎖定片段。如果您想要修改特定電子郵件的片段，可以在使用該電子郵件時將其解除鎖定，以中斷與原始片段的同步。變更不再同步。

若要解除鎖定電子郵件中的片段，請選取該片段並從內容相關工具列按一下鎖定圖示。

![](assets/des_unlocking_fragment.png)

該片段會變成不會再連結至原始片段的獨立元件。然後它就可以當做任何其他內容元件進行編輯。See [About content components](../../designing/using/defining-the-email-structure.md#about-content-components).

### About content components {#about-content-components}

內容元件是原始的空白元件，您只需將它置於電子郵件中即可。

您可以在結構元件中新增任意數量的內容元件。您也可以將它們移至結構元件內或另一個結構元件中。

以下是電子郵件設計人員中可用元件的清單：

* **[!UICONTROL Button]**

   If you need to use multiple buttons, rather than editing each button from scratch, you can duplicate the **[!UICONTROL Button]** component using the contextual toolbar.

   您也可以將按鈕儲存為可重復使用的片段。For more on this, see [Creating a content fragment](../../designing/using/defining-the-email-structure.md#creating-a-content-fragment) and [Saving content as a fragment](../../designing/using/defining-the-email-structure.md#saving-content-as-a-fragment).

* **[!UICONTROL Carousel]**

   For more on this, see [Using the carousel component](../../designing/using/defining-the-email-structure.md#using-the-carousel-component).

* **[!UICONTROL Divider]**
* **[!UICONTROL Html]**

   使用此元件複製現有HTML的不同部分。這可讓您建立免費的模組式HTML元件。

   >[!NOTE]
   >
   >使用有限選項可編輯免費HTML元件。If all styles are not inlined, make sure to add the proper CSS in the **head** section of the HTML code, otherwise the email will not be responsive. Use the **[!UICONTROL Preview]** button to test the responsiveness of your content (see [Previewing messages](../../sending/using/previewing-messages.md)).

* **[!UICONTROL Image]**
* **[!UICONTROL Social]**
* **[!UICONTROL Text]**

#### Using the carousel component {#using-the-carousel-component}

1. Drag and drop the **[!UICONTROL Carousel]** component inside a structure component.
1. 瀏覽以從電腦選取影像。

   ![](assets/des_carousel_browse.png)

1. From the **[!UICONTROL Settings]** pane, set the number of thumbnails that you want in the carousel.
1. 從電腦選取後援影像。

   ![](assets/des_carousel_fallback.png)

   轉盤元件與所有電子郵件程式不相容。當電子郵件中不支援轉盤時，請上傳後援以顯示影像。

   >[!NOTE]
   >
   >轉盤元件與下列電子郵件平台相容：Apple Mail7、Apple Mail8、Outlook2011for Mac、Outlook2016for Mac、Mozilla Thunderbird、iPad和iPad mini iOS、iPhone iOS、Android、AOL(Chrome、Firefox和Safari)。

1. Select **[!UICONTROL Fallback view]** to display the fallback image in the Email Designer.

### Inserting elements into an email {#inserting-elements-into-an-email}

若要定義電子郵件內容，您可以在您先前放置的結構元件中新增內容元素。See [Editing the email structure](../../designing/using/defining-the-email-structure.md#editing-the-email-structure).

1. Access the content elements by selecting the **+** icon on the left. Select [Fragments](../../designing/using/defining-the-email-structure.md#about-fragments) or [Content components](../../designing/using/defining-the-email-structure.md#about-content-components).
1. 如果您已經知道要新增的標籤標籤或部分標籤，可以搜尋它。

   ![](assets/email_designer_fragmentsearch.png)

1. 從浮動視窗拖放片段或內容元件至電子郵件的結構元件。

   ![](assets/email_designer_addfragment.png)

   將元素新增至電子郵件後，就可以在結構元件內或電子郵件中的另一個結構元件中移動。

   ![](assets/email_designer_movefragment.png)

1. 編輯元素以符合此電子郵件的實際需要。您可以新增文字、連結、影像等。

   >[!NOTE]
   >
   >當新增至電子郵件時，片段預設為鎖定。如果您要修改特定電子郵件的片段，或直接在片段中變更，可以中斷與原始片段的同步。See [About fragments](../../designing/using/defining-the-email-structure.md#about-fragments).

1. 針對您需要新增至電子郵件的所有元素重復此程序。
1. 儲存您的電子郵件。

現在您的電子郵件結構已填入，您可以編輯每個內容元素的樣式。See [Editing an element](../../designing/using/editing-email-styles.md#editing-an-element).

>[!NOTE]
>
>如果已修改片段，則變更會自動傳播在使用該片段的電子郵件中。For more on this, see [About fragments](../../designing/using/defining-the-email-structure.md#about-fragments).

### Creating a content fragment {#creating-a-content-fragment}

您可以根據需要建立自己的內容片段，以便在一或多封電子郵件中使用。

1. Go to **[!UICONTROL Resources]** &gt; **[!UICONTROL Content templates & fragments]** and click **[!UICONTROL Create]**.
1. Click the email label to access the **[!UICONTROL Properties]** tab of the Email Designer.
1. 指定可識別的標籤，並選取下列參數，以便稍後在新電子郵件中找到片段：

   * Because fragments are only compatible with emails, select **[!UICONTROL Delivery]** from the **[!UICONTROL Content type]** drop-down list.
   * Select **[!UICONTROL Fragment]** from the **[!UICONTROL HTML type]** drop-down list to be able to use this content as a fragment in your emails.
   ![](assets/email_designer_createfragment.png)

1. 如有需要，您可以設定將做為片段縮圖的影像。Select it from the **[!UICONTROL Thumbnail]** tab of the template properties.

   ![](assets/email_designer_createfragment_thumbnail.png)

   編輯電子郵件時，此縮圖會顯示在片段標籤旁。

1. 儲存變更以返回主工作區。
1. 新增結構元件和您可視需要自訂的內容元件。
1. 編輯後，儲存片段。

此片段現在可用於使用電子郵件設計工具建立的任何電子郵件中。It appears under the **[!UICONTROL Fragments]** section of the Palette.

>[!NOTE]
>
>除非電子郵件中使用了個人化欄位，否則您無法插入其個人化欄位。若要這麼做，您必須解除鎖定此片段。See [About fragments](../../designing/using/defining-the-email-structure.md#about-fragments).

### Saving content as a fragment {#saving-content-as-a-fragment}

使用電子郵件設計工具編輯電子郵件時，您無法直接將該電子郵件的部分儲存為片段。

您需要複製對應至您要儲存至新片段之區段的HTML。

>[!NOTE]
>
>若要這麼做，您必須熟悉HTML程式碼。

若要將您所建立的部分電子郵件內容儲存為片段，請依照下列步驟進行。

1. When editing an email in the Email Designer, select **[!UICONTROL Edit]** &gt; **[!UICONTROL HTML]** to open the HTML version of that email.
1. 選取並複製對應您要儲存之部分的HTML。
1. Go to **[!UICONTROL Resources]** &gt; **[!UICONTROL Content templates & fragments]** and click **[!UICONTROL Create]**.
1. Click the email label to access the **[!UICONTROL Properties]** tab of the Email Designer and select **[!UICONTROL Fragment]** from the **[!UICONTROL HTML type]** drop-down list.
1. Select **[!UICONTROL Edit]** &gt; **[!UICONTROL HTML]** to open the HTML version of the fragment.
1. 貼上您在適當位置複製的HTML。
1. Switch back to the **[!UICONTROL Edit]** view to check the result and save the new fragment.

