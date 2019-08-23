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
source-git-commit: c2316d35c582efc8a3cc9be5de810c5dbe3f5e97

---


# 定義電子郵件結構{#defining-the-email-structure}

## 編輯電子郵件結構 {#editing-the-email-structure}

電子郵件設計人員可讓您輕鬆定義電子郵件的結構。透過簡單的拖放動作新增及移動結構元素，即可在數秒內設計電子郵件的形狀。

若要編輯電子郵件的結構：

1. 開啓現有內容或建立新的電子郵件內容。
1. 選取 **[!UICONTROL Structure components]** 左邊的 **+** 圖示即可存取。

   ![](assets/email_designer_structure.png)

1. 拖放您需要的結構元件，以建立您的電子郵件格式。

   ![](assets/email_designer_structure_components.png)

   藍色線條會先重新整理結構元件的確切位置，然後再放下。您可以將它放置在任何其他元件之間或下方，但不能放在內部。

   >[!NOTE]
   >
   >置入電子郵件後，除非已有內容元件或置於內部，否則您無法移動或移除元件。

1. 可使用由一欄或多欄組成的數個結構元件。

   選取 **[!UICONTROL n:n column]** 元件以定義您所選擇的欄數(到10之間)。您也可以移動每欄底部的箭頭，定義每欄的寬度。

   ![](assets/email_designer_n-n-column.png)

   >[!NOTE]
   >
   >每個欄大小不能低於結構元件總寬度的10%以下。您無法移除非空白的欄。

在定義結構後，您可以將內容片段和元件新增至您的電子郵件。

## 新增片段和內容元件 {#adding-fragments-and-content-components}

透過電子郵件設計工具，在新增元件至電子郵件後，您可以定義其內容。若要這麼做，您必須在每個結構元件中新增元素。

您可使用兩種類別的內容元素： **片段** 和 **內容元件**。

### 關於片段 {#about-fragments}

片段是可重復使用的元件，可在一或多封電子郵件中參照。

若要在電子郵件設計工具中充分使用片段：

* 建立您自己的片段。請參閱 [建立內容片段](../../designing/using/defining-the-email-structure.md#creating-a-content-fragment) 並 [將內容儲存為片段](../../designing/using/defining-the-email-structure.md#saving-content-as-a-fragment)。
* 您可以在電子郵件中多次使用它們。請參閱 [將元素插入電子郵件](../../designing/using/defining-the-email-structure.md#inserting-elements-into-an-email)中。
* 當您編輯片段時，變更會同步化：會自動傳播至所有包含該片段的電子郵件(但尚未準備或傳送)。

新增至電子郵件時，預設會鎖定片段。如果您想要修改特定電子郵件的片段，可以在使用該電子郵件時將其解除鎖定，以中斷與原始片段的同步。變更不再同步。

若要解除鎖定電子郵件中的片段，請選取該片段並從內容相關工具列按一下鎖定圖示。

![](assets/des_unlocking_fragment.png)

該片段會變成不會再連結至原始片段的獨立元件。然後它就可以當做任何其他內容元件進行編輯。請參閱 [關於內容元件](../../designing/using/defining-the-email-structure.md#about-content-components)。

### 關於內容元件 {#about-content-components}

內容元件是原始的空白元件，您只需將它置於電子郵件中即可。

您可以在結構元件中新增任意數量的內容元件。您也可以將它們移至結構元件內或另一個結構元件中。

以下是電子郵件設計人員中可用元件的清單：

* **[!UICONTROL Button]**

   如果您需要使用多個按鈕，而不是從頭開始編輯每個按鈕，可以使用內容相關工具列複製 **[!UICONTROL Button]** 元件。

   您也可以將按鈕儲存為可重復使用的片段。如需詳細資訊，請參閱 [「建立內容片段](../../designing/using/defining-the-email-structure.md#creating-a-content-fragment) 和 [將內容儲存為片段](../../designing/using/defining-the-email-structure.md#saving-content-as-a-fragment)」。

* **[!UICONTROL Carousel]**

   如需詳細資訊，請參閱 [「使用轉盤元件](../../designing/using/defining-the-email-structure.md#using-the-carousel-component)」。

* **[!UICONTROL Divider]**
* **[!UICONTROL Html]**

   使用此元件可複製現有HTML的不同部分。這可讓您建立免費的模組式HTML元件。

   >[!NOTE]
   >
   >使用有限選項可編輯免費HTML元件。如果所有樣式未內嵌，請務必在HTML程式碼的 **head** 區段中新增適當的CSS，否則電子郵件將無法回應。使用 **[!UICONTROL Preview]** 按鈕測試內容的回應速度(請參閱 [預覽訊息](../../sending/using/previewing-messages.md))。

* **[!UICONTROL Image]**
* **[!UICONTROL Social]**
* **[!UICONTROL Text]**

#### 使用轉盤元件 {#using-the-carousel-component}

1. 將 **[!UICONTROL Carousel]** 元件拖放至結構元件中。
1. 瀏覽以從電腦選取影像。

   ![](assets/des_carousel_browse.png)

1. 在 **[!UICONTROL Settings]** 窗格中，設定您要在轉盤中使用的縮圖數目。
1. 從電腦選取後援影像。

   ![](assets/des_carousel_fallback.png)

   轉盤元件與所有電子郵件程式不相容。當電子郵件中不支援轉盤時，請上傳後援以顯示影像。

   >[!NOTE]
   >
   >轉盤元件與下列電子郵件平台相容：Apple Mail7、Apple Mail8、Outlook2011for Mac、Outlook2016for Mac、Mozilla Thunderbird、iPad和iPad mini iOS、iPhone iOS、Android、AOL(Chrome、Firefox和Safari)。

1. 選取 **[!UICONTROL Fallback view]** 以顯示電子郵件設計工具中的備援影像。

### 將元素插入電子郵件中 {#inserting-elements-into-an-email}

若要定義電子郵件內容，您可以在您先前放置的結構元件中新增內容元素。請參閱 [編輯電子郵件結構](../../designing/using/defining-the-email-structure.md#editing-the-email-structure)。

1. 選取左側 **的+** 圖示以存取內容元素。選取 [片段](../../designing/using/defining-the-email-structure.md#about-fragments) 或 [內容元件](../../designing/using/defining-the-email-structure.md#about-content-components)。
1. 如果您已經知道要新增的標籤標籤或部分標籤，可以搜尋它。

   ![](assets/email_designer_fragmentsearch.png)

1. 從浮動視窗拖放片段或內容元件至電子郵件的結構元件。

   ![](assets/email_designer_addfragment.png)

   將元素新增至電子郵件後，就可以在結構元件內或電子郵件中的另一個結構元件中移動。

   ![](assets/email_designer_movefragment.png)

1. 編輯元素以符合此電子郵件的實際需要。您可以新增文字、連結、影像等。

   >[!NOTE]
   >
   >當新增至電子郵件時，片段預設為鎖定。如果您要修改特定電子郵件的片段，或直接在片段中變更，可以中斷與原始片段的同步。請參閱 [關於片段](../../designing/using/defining-the-email-structure.md#about-fragments)。

1. 針對您需要新增至電子郵件的所有元素重復此程序。
1. 儲存您的電子郵件。

現在您的電子郵件結構已填入，您可以編輯每個內容元素的樣式。請參閱 [編輯元素](../../designing/using/editing-email-styles.md#editing-an-element)。

>[!NOTE]
>
>如果已修改片段，則變更會自動傳播在使用該片段的電子郵件中。如需詳細資訊，請參閱 [關於片段](../../designing/using/defining-the-email-structure.md#about-fragments)。

### 建立內容片段 {#creating-a-content-fragment}

您可以根據需要建立自己的內容片段，以便在一或多封電子郵件中使用。

1. 前往 **[!UICONTROL Resources]** &gt; **[!UICONTROL Content templates & fragments]** 並按一下 **[!UICONTROL Create]**。
1. 按一下電子郵件標籤以存取電子郵件設計工具 **[!UICONTROL Properties]** 的標籤。
1. 指定可識別的標籤，並選取下列參數，以便稍後在新電子郵件中找到片段：

   * 因為片段只能與電子郵件相容，請 **[!UICONTROL Delivery]** 從 **[!UICONTROL Content type]** 下拉式清單中選取。
   * 從 **[!UICONTROL Fragment]****[!UICONTROL HTML type]** 下拉式清單中選取，可將此內容用作電子郵件中的片段。
   ![](assets/email_designer_createfragment.png)

1. 如有需要，您可以設定將做為片段縮圖的影像。從範本屬性 **[!UICONTROL Thumbnail]** 的標籤中選取它。

   ![](assets/email_designer_createfragment_thumbnail.png)

   編輯電子郵件時，此縮圖會顯示在片段標籤旁。

1. 儲存變更以返回主工作區。
1. 新增結構元件和您可視需要自訂的內容元件。
1. 編輯後，儲存片段。

此片段現在可用於使用電子郵件設計工具建立的任何電子郵件中。它會出現在浮動視窗的 **[!UICONTROL Fragments]** 區段下方。

>[!NOTE]
>
>除非電子郵件中使用了個人化欄位，否則您無法插入其個人化欄位。若要這麼做，您必須解除鎖定此片段。請參閱 [關於片段](../../designing/using/defining-the-email-structure.md#about-fragments)。

### 將內容儲存為片段 {#saving-content-as-a-fragment}

使用電子郵件設計工具編輯電子郵件時，您可以直接將該電子郵件的部分儲存為片段。

>[!CAUTION]
>
>您無法將結構儲存為包含個人化欄位、動態內容或其他片段的結構片段。

1. 在電子郵件設計工具中編輯電子郵件時，請從 **[!UICONTROL Save as fragment]** 主工具列中選取。

   ![](assets/email_designer_save-as-fragment.png)

1. 從工作區中選取將編譯片段的結構。

   ![](assets/email_designer_save-as-fragment_select.png)

   >[!NOTE]
   >
   >您只能選取彼此相鄰的結構。

1. Click **[!UICONTROL Create]**.

1. 視需要新增標籤和說明，然後按一下 **[!UICONTROL Save]**。

   ![](assets/email_designer_save-as-fragment_popup.png)

1. 若要尋找剛建立的片段，請前往 **[!UICONTROL Resources]** &gt; **[!UICONTROL Content templates & fragments]**。

   ![](assets/email_designer_save-as-fragment_list.png)

1. 若要使用新片段，請開啓任何電子郵件內容，然後從片段清單中選取。

![](assets/email_designer_save-as-fragment_in-new-email.png)

<!--You need to copy-paste the HTML corresponding to the section that you want to save into a new fragment.

>[!NOTE]
>
>To do this, you need to be familiar with HTML code.

To save as a fragment some email content that you created, follow the steps below.

1. When editing an email in the Email Designer, select **[!UICONTROL Edit]** > **[!UICONTROL HTML]** to open the HTML version of that email.
1. Select and copy the HTML corresponding to the part that you want to save.
1. Go to **[!UICONTROL Resources]** > **[!UICONTROL Content templates & fragments]** and click **[!UICONTROL Create]**.
1. Click the email label to access the **[!UICONTROL Properties]** tab of the Email Designer and select **[!UICONTROL Fragment]** from the **[!UICONTROL HTML type]** drop-down list.
1. Select **[!UICONTROL Edit]** > **[!UICONTROL HTML]** to open the HTML version of the fragment.
1. Paste the HTML that you copied where appropriate.
1. Switch back to the **[!UICONTROL Edit]** view to check the result and save the new fragment.-->

