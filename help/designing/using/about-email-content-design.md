---
title: 關於電子郵件內容設計
seo-title: 關於電子郵件內容設計
description: 關於電子郵件內容設計
seo-description: 探索電子郵件設計人員，讓您設計電子郵件內容。
page-status-flag: 從未啓動
uuid: 571ffc01-6e41-4501-9094-2f812b041a10
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: design
content-type: reference
topic-tags: editing-email-content
discoiquuid: 39b86fda-7766-4e5f-ab48-bcc536 ab66 b3 b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f85995fc5a331b57e42a58d979940751dbe7ce97

---


# About email content design{#about-email-content-design}

使用電子郵件設計人員拖放介面，在Adobe Campaign中建立及修改電子郵件內容。

本節說明電子郵件設計人員的具體資訊：

* [關於電子郵件設計人員](../../designing/using/about-email-content-design.md#about-the-email-designer)
* [定義電子郵件結構](../../designing/using/defining-the-email-structure.md)
* [編輯電子郵件樣式](../../designing/using/editing-email-styles.md)

若要深入瞭解一或多個行銷活動常用的動作，請參閱下列章節：

* For more on personalizing an email content, see [Inserting a personalization field](../../designing/using/inserting-a-personalization-field.md) and [Adding a content block](../../designing/using/adding-a-content-block.md).
* For more on importing another email content, see [Selecting an existing content](../../designing/using/selecting-an-existing-content.md).
* For more on defining dynamic content in an email, see [Defining dynamic content in an email](../../designing/using/defining-dynamic-content-in-an-email.md).
* For more on inserting links in an email, see [Inserting a link](../../designing/using/inserting-a-link.md).
* For more on inserting images in an email, see [Inserting images](../../designing/using/inserting-images.md).

Also check the [general best practices for content design](../../designing/using/content-design-best-practices.md).

## About the Email Designer {#about-the-email-designer}

電子郵件設計人員可讓您建立電子郵件內容和電子郵件內容範本。它與簡單電子郵件、交易電子郵件、A/B測試電子郵件、多語言電子郵件和週期性電子郵件相容。

To get started with the Email Designer, watch this [set of videos](https://helpx.adobe.com/campaign/kt/acs/using/acs-email-designer-tutorial.html#GettingStarted) that explain the general functionality of the Email Designer and how to design an email from scratch or using templates.

### Email Designer home page {#email-designer-home-page}

[建立電子郵件](../../channels/using/creating-an-email.md)時，在選取電子郵件內容時會自動顯示 **[!UICONTROL Email Designer]** 首頁。

![](assets/email_designer_home_page.png)

**[!UICONTROL Properties]** 此標籤可讓您編輯電子郵件詳細資訊，例如標籤、傳送者的地址和名稱，或電子郵件主旨。您也可以按一下螢幕頂端的電子郵件標籤，存取此標籤。

![](assets/email_designer_home_properties.png)

**[!UICONTROL Templates]** 此標籤可讓您從現成可用的HTML內容或您已建立的範本中選擇，快速開始設計您的電子郵件。See [Content templates](../../start/using/about-templates.md#content-templates).

![](assets/email_designer_home_templates.png)

**[!UICONTROL Learn & support]** 此標籤可讓您輕鬆存取相關說明文件和教學課程。

![](assets/email_designer_home_support.png)

如果您未選取範本，「電子郵件設計人員」首頁也可讓您選擇開始設計內容的方式：

* Click the **[!UICONTROL Create]** button to start a new content from scratch. See [Designing an email content from scratch](../../designing/using/about-email-content-design.md#designing-an-email-content-from-scratch).
* Click the **[!UICONTROL Upload]** button to upload a file from your computer. See [Importing content from a file](../../designing/using/importing-content-from-a-file.md).
* Click the **[!UICONTROL Import from URL]** button to retrieve existing content form a URL. See [Importing content from a URL](../../designing/using/importing-content-from-a-url.md).

### Email Designer interface {#email-designer-interface}

電子郵件設計人員提供許多選項，可讓您建立、編輯和自訂內容的各個層面。

此介面由數個提供不同功能的區域組成：

![](assets/email_designer_overview.png)

From the elements available in the **Palette** (1), drag and drop structure components and content fragments into the main **Workspace** (2). Select a component or element in the **Workspace** (2) and customize its main styling and display characteristics from the **Settings** pane (3).

Access more general options and settings from the main **Toolbar** (4).

>[!NOTE]
>
>**「設定」** 窗格可以根據螢幕解析度移至左側並顯示。

![](assets/email_designer_toolbar.png)

The **Contextual toolbar** of the editor interface offers various functionalities depending on the zone selected. 它包含動作按鈕和按鈕，可讓您變更文字樣式。執行的修改一律適用於選取的區域。

### General recommendations for using the Email Designer {#general-recommendations-for-using-the-email-designer}

為了適當地使用電子郵件設計人員並盡可能建立最佳電子郵件，建議您套用下列原則：

* 在HTML的&lt; head&gt;區段中使用內嵌樣式，而非個別的CSS和CSS。透過內嵌樣式，您可以最佳化內容片段儲存並重復使用。

   See [Adding inline styling attributes](../../designing/using/editing-email-styles.md#adding-inline-styling-attributes).

* 建立和重復使用內容片段，讓行銷活動保持一致性，輕鬆地結算您的品牌。

   See [Creating a content fragment](../../designing/using/defining-the-email-structure.md#creating-a-content-fragment).

Also check the [general best practices for content design](../../designing/using/content-design-best-practices.md).

### Email Designer compatibility mode {#email-designer-compatibility-mode}

上傳內容時，它必須包含特定標記，才能完全符合併可使用電子郵件設計工具的WYSIWYG編輯器編輯。

如果上傳的HTML全部或部分不符合預期的標記，則內容會載入'相容性模式'，以限制透過UI的版本可能性。

在相容性模式載入內容時，您仍可透過介面執行下列修改(無法使用的動作隱藏)：

* 變更文字或變更影像
* 插入連結和個人化欄位
* 編輯選取HTML區塊上的某些樣式選項
* 定義條件式內容

![](assets/email_designer_compatibility.png)

其他修改，例如新增區段至您的電子郵件或進階樣式，必須透過HTML模式直接在電子郵件的來源程式碼中完成。

For more on converting an existing email into an Email Designer-compatible email, see [this section](../../designing/using/about-email-content-design.md#designing-an-email-using-existing-contents).

### Email Designer limitations {#email-designer-limitations}

* 您無法在片段中使用個人化欄位。For more on fragments, see [this section](../../designing/using/defining-the-email-structure.md#about-fragments).
* 您無法直接將其儲存為您在電子郵件設計人員內編輯的電子郵件內容。您需要將對應該內容的HTML複製到新片段中。For more on this, see [Saving content as a fragment](../../designing/using/defining-the-email-structure.md#saving-content-as-a-fragment).
* 編輯樣式時，只有大部分電子郵件用戶端才會提供正式支援的網頁字體。
* 樣式無法儲存為主題，以便日後重復使用。不過，CSS樣式可以儲存在內容範本或電子郵件中。For more on styles, see [this section](../../designing/using/editing-email-styles.md).

### Email Designer updates {#email-designer-updates}

電子郵件設計人員正在不斷改進。如果您從頭開始建立電子郵件內容，從現成可用的範本或您建立的片段，就可以在下次開啓內容時收到下列更新訊息：

![](assets/email_designer_fragment_patch_message.png)

Adobe建議您將內容更新為最新版本，以避免發生CSS衝突問題。Click **[!UICONTROL Update now]**.

如果內容更新期間發生錯誤，請檢查您的HTML並加以修正，然後再執行此更新。

有關片段，請注意下列事項：

* 如果您想要新增片段至新的電子郵件或範本，如果收到此訊息，您必須先更新此片段。

* 如果您有多個片段，必須更新您要在電子郵件內容中使用的每個片段。

* 為了避免對目前電子郵件訊息造成影響，因為其中有些可能處於準備階段或特定促銷活動中，您不想要變更，您可以選擇不更新部分片段。

* 您仍然可以傳送未更新的片段，但無法編輯該片段的電子郵件。

## Designing an email content from scratch {#designing-an-email-content-from-scratch}

以下是使用電子郵件設計人員從頭開始建立和設計電子郵件內容的主要步驟：

1. 建立電子郵件並開啓其內容。
1. 新增結構元件以繪制電子郵件。See [Editing the email structure](../../designing/using/defining-the-email-structure.md#editing-the-email-structure).
1. 在結構元件中插入內容元件和片段。See [Adding fragments and content components](../../designing/using/defining-the-email-structure.md#adding-fragments-and-content-components).
1. 新增影像並編輯電子郵件文字。See [Inserting images](../../designing/using/inserting-images.md).
1. 透過新增個人化欄位、連結等，個人化您的電子郵件。See [Inserting a personalization field](../../designing/using/inserting-a-personalization-field.md), [Inserting a link](../../designing/using/inserting-a-link.md) and [Defining dynamic content in an email](../../designing/using/defining-dynamic-content-in-an-email.md).
1. 定義電子郵件的主旨行。See [Personalizing the subject line of an email](../../designing/using/personalizing-the-subject-line-of-an-email.md).
1. 預覽您的電子郵件。
1. 儲存您的內容，然後繼續您的訊息，確定您已定義對象並正確排程傳送。

You can also check out this [introduction video](https://video.tv.adobe.com/v/22771/?autoplay=true&hidetitle=true&captions=chi_hant).

>[!NOTE]
>
>為避免從頭開始設計電子郵件內容，您可以使用現成可用的內容範本。For more on this, see [Content templates](../../start/using/about-templates.md#content-templates).

**相關主題**：

* [建立電子郵件](../../channels/using/creating-an-email.md)
* [選取現有內容](../../designing/using/selecting-an-existing-content.md)
* [在訊息中選取對象](../../audiences/using/selecting-an-audience-in-a-message.md)
* [排程訊息](../../sending/using/about-scheduling-messages.md)
* [預覽訊息](../../sending/using/previewing-messages.md)
* [電子郵件演算](../../sending/using/email-rendering.md)

## Designing an email using existing contents {#designing-an-email-using-existing-contents}

本節說明如何將現有電子郵件轉換為電子郵件設計人員相容電子郵件。

By default, if you just upload any HTML (see [Importing content from a file](../../designing/using/importing-content-from-a-file.md)), the content is loaded in '[compatibility mode](../../designing/using/about-email-content-design.md#email-designer-compatibility-mode)', which limits the edition possibilities through the UI (only in-place edition, no drag-and-drop).

不過，如果您想要建立模組化範本和片段的架構，以便結合在多封電子郵件中，則應考慮將電子郵件HTML轉換為電子郵件設計人員範本。

使用電子郵件設計工具設計內容時，您有三個選項：

* [從現成可用的範本建立內容](../../designing/using/about-email-content-design.md#building-content-from-an-out-of-the-box-template)
* [使用片段和元件](../../designing/using/about-email-content-design.md#using-fragments-and-components)，從頭開始建立HTML設計
* [將HTML內容](../../designing/using/about-email-content-design.md#converting-an-html-content) 電子郵件轉換為模組化電子郵件設計人員內容

### Building content from an out-of-the-box template {#building-content-from-an-out-of-the-box-template}

1. 建立電子郵件並開啓其內容。For more on this, see [Creating an email](../../channels/using/creating-an-email.md).
1. Click the home icon to access the **[!UICONTROL Email Designer]** home page.
1. Click the **[!UICONTROL Templates]** tab.
1. 選擇現成可用的HTML範本。

   不同的範本顯示各種元素的組合。例如，「Bundher」範本具有邊界，而「Astro」範本則沒有其邊界。For more on this, see [Content templates](../../start/using/about-templates.md#content-templates).

1. 您可以結合這些元素來建立數個電子郵件變數。For example, you can duplicate an email section by selecting a structure component and clicking **[!UICONTROL Duplicate]** from the contextual toolbar.
1. 您可以使用左側藍色箭頭來移動元素，將結構元件拖曳至下方或更上方。For more on this, see [Editing the email structure](../../designing/using/defining-the-email-structure.md#editing-the-email-structure).
1. 您也可以移動元件來變更每個結構元素的組織。For more on this, see [Adding fragments and components](../../designing/using/defining-the-email-structure.md#adding-fragments-and-content-components).
1. 根據您的需求修改每個元素的內容：影像、文字、連結。
1. 視需要調整內容的樣式選項。For more on this, see [Editing email styles](../../designing/using/editing-email-styles.md).

### Using fragments and components {#using-fragments-and-components}

為了讓外部內容符合電子郵件設計人員的規定，Adobe建議您從頭開始建立訊息，並將現有電子郵件中的內容複製到片段和元件中。

When you have a content that cannot be recreated, you can copy-paste the HTML code from the original email using the **[!UICONTROL Html]** content component. 請務必先熟悉HTML，然後再繼續。

以下是完整範例。

>[!NOTE]
>
>新內容不會是原始電子郵件的確切副本，但下列步驟將引導您建立最接近可能的訊息。

假設您想要使用在Adobe Campaign之外建立的現有電子報。

您希望所有電子郵件中的頁首和頁尾都能隨Adobe Campaign一起傳送。電子郵件的內文會根據您要在每份電子報中顯示的內容而變更。

**必要條件**

1. 在原始電子郵件中，從您將傳送的每封電子郵件專屬的區段識別可重復使用的章節。
1. 儲存您要使用的所有影像和資產。
1. 如果您熟悉HTML，請將原始的HTML內容分割為不同的部分。

**建立可重復使用內容的片段**

使用電子郵件設計工具，為每個可重復使用的區段建立片段。在此範例中，您將建立兩個片段：一個用於標題，另一個用於頁尾。然後，您可以將現有內容中的相關部分複製到這些片段中。

若要執行此動作，請執行下列步驟：

1. In Adobe Campaign, go to **[!UICONTROL Resources]** &gt; **[!UICONTROL Content templates & fragments]** and create a fragment for your header. For more on this, see [Creating a content fragment](../../designing/using/defining-the-email-structure.md#creating-a-content-fragment).
1. 視需要新增任意數量的結構元件。

   ![](assets/des_loading_compatible_fragment_1.png)

1. 將影像和文字元件插入您的結構中。

   ![](assets/des_loading_compatible_fragment_2.png)

1. 上傳對應的影像，輸入文字並調整設定。

   For more on managing style settings and inline attributes, see [Editing email styles](../../designing/using/editing-email-styles.md).

   ![](assets/des_loading_compatible_fragment_3.png)

1. 儲存片段。
1. 同樣地繼續建立頁尾並儲存。

   ![](assets/des_loading_compatible_fragment_4.png)

   If you are familiar with HTML, you can copy-paste the HTML code from the original footer using the **[!UICONTROL Html]** content component. For more on this, see [About content components](../../designing/using/defining-the-email-structure.md#about-content-components).

   ![](assets/des_loading_compatible_fragment_9.png)

您的片段現在可以用於範本中。

**插入片段和元件至範本中**

您現在可以使用電子郵件設計工具建立電子郵件範本。使用內容元件來反映電子郵件的不同區段，並調整設定，使其盡可能接近原始電子報。最後插入您剛才建立的片段。

1. 使用電子郵件設計工具建立範本。For more on this, see [Content templates](../../start/using/about-templates.md#content-templates).
1. 將數個結構元件插入您的範本中，對應至電子郵件的頁首、頁尾和內文。For more on adding structure components, see [Editing the email structure with the Email Designer](../../designing/using/defining-the-email-structure.md#editing-the-email-structure).
1. 視需要插入任意數量的內容元件，以建立電子報。這將是您每個月更新的電子郵件的可編輯內容。

   ![](assets/des_loading_compatible_fragment_5.png)

   If you are familiar with HTML code, Adobe recommends leveraging **[!UICONTROL Html]** components where you can copy-paste the more complex elements of the original email. Use other components such as **[!UICONTROL Button]**, **[!UICONTROL Image]** or **[!UICONTROL Text]** for the rest of the content. For more on this, see [About content components](../../designing/using/defining-the-email-structure.md#about-content-components).

   >[!NOTE]
   >
   >Using the **[!UICONTROL Html]** component results in creating components that are editable with limited options. 在選取此元件之前，請確定您知道如何處理HTML程式碼。

1. 調整內容元件，以符合您的原始電子郵件。

   ![](assets/des_loading_compatible_fragment_6.png)

   For more on managing style settings and inline attributes, see [Editing email styles](../../designing/using/editing-email-styles.md).

1. 插入您先前建立至所需結構元件的兩個片段(頁首和頁尾)。

   ![](assets/des_loading_compatible_fragment_10.png)

1. 儲存範本。

您現在可以完全管理電子郵件設計人員內的此範本，建立並更新每個月傳送給收件人的電子報。

若要使用它，請建立電子郵件並選取您剛才建立的內容範本。

**相關主題**：

* [建立電子郵件](../../channels/using/creating-an-email.md)
* [電子郵件設計人員簡介影片](https://video.tv.adobe.com/v/22771/?autoplay=true&hidetitle=true&captions=chi_hant)
* [從頭開始設計電子郵件內容](../../designing/using/about-email-content-design.md#designing-an-email-content-from-scratch)

### Converting an HTML content {#converting-an-html-content}

此使用案例可讓您快速將HTML電子郵件轉換為電子郵件設計人員元件。

>[!CAUTION]
>
>本節適用於熟悉HTML程式碼的進階使用者。

>[!NOTE]
>
>與相容性模式類似，HTML元件可使用有限選項編輯：您只能執行就地執行版本。

在「電子郵件設計工具」之外，確定原始HTML分割為可重復使用的區段。

如果不是這樣，請剪下HTML中不同的區塊。例如：

```
<!-- 3 COLUMN w/CTA (SCALED) -->
<table width="100%" align="center" cellspacing="0" cellpadding="0" border="0" role="presentation" style="max-width:680px;">
<tbody>
<tr>
<td class="padh10" align="center" valign="top" style="padding:0 5px 20px 5px;">
<table width="100%" cellspacing="0" cellpadding="0" border="0" role="presentation">
<tbody>
<tr>
...
</tr>
</tbody>
</table>
</td>
</tr>
</tbody>
</table>
<!-- //3 COLUMN w/CTA (SCALED) -->
```

在您識別所有區塊後，請在電子郵件設計人員中，針對現有電子郵件的每個區段重復下列程序：

1. 開啓「電子郵件設計工具」以建立空白的電子郵件內容。
1. 設定內文層級屬性：背景顏色、寬度等。For more on this, see [Editing email styles](../../designing/using/editing-email-styles.md).
1. 新增結構元件。For more on this, see [Editing the email structure](../../designing/using/defining-the-email-structure.md#editing-the-email-structure).
1. 新增HTML元件。For more on this, see [Adding fragments and components](../../designing/using/defining-the-email-structure.md#adding-fragments-and-content-components).
1. 將您的HTML複製到該元件中。
1. 切換至行動裝置檢視。For more on this, see [this section](../../designing/using/about-email-content-design.md#switching-to-mobile-view).

   自適應檢視中斷，因為您的CSS遺失了。

1. 若要修正這個問題，請切換至原始程式碼模式，然後將樣式區段複製到新樣式區段中。例如：

   ```
   <style type="text/css">
   a {text-decoration:none;}
   body {min-width:100% !important; margin:0 auto !important; padding:0 !important;}
   img {line-height:100%; text-decoration:none; -ms-interpolation-mode:bicubic;}
   ...
   </style>
   ```

   >[!NOTE]
   >
   >Do not modify the CSS generated by the Email Designer: `<style acrite-template-css="true">` and `<style acrite-custom-styles="" type="text/css">`. 請確定您之後新增樣式。

1. 返回行動裝置檢視，檢查內容是否正確顯示並儲存您的變更。

## Switching to mobile view {#switching-to-mobile-view}

您可以個別編輯行動顯示的所有樣式選項，微調電子郵件的多方互動設計。例如，您可以調整邊界和間距、使用較小或更大的字體大小、變更按鈕，或套用不同於行動版電子郵件的不同背景顏色。

行動檢視中提供所有樣式選項。The Email Designer style settings are presented in the [Editing email styles](../../designing/using/editing-email-styles.md) section.

1. 建立電子郵件並開始編輯內容。For more on this, see [Designing an email content from scratch](../../designing/using/about-email-content-design.md#designing-an-email-content-from-scratch).
1. To access the dedicated mobile view, select the **[!UICONTROL Switch to mobile view]** button.

   ![](assets/email_designer_mobile_view_switch.png)

   隨即顯示電子郵件的行動版本。它包含桌面檢視中定義的所有元件和樣式。

1. 單獨編輯所有樣式設定，例如背景顏色、對齊、填補空間、邊界、字體系列、文字色彩等。

   ![](assets/email_designer_mobile_view.png)

1. 在行動檢視中編輯任何樣式設定時，修改只會套用至行動顯示。

   例如，減少影像大小、新增綠色背景並變更行動檢視中的間距。

   ![](assets/email_designer_mobile_view_change.png)

1. 在行動裝置上顯示時，您可以隱藏元件。To do this, select **[!UICONTROL Show only on desktop devices]** from the **[!UICONTROL Display options]**.
您也可以選擇將此元件隱藏在桌面裝置上，這表示它只會顯示在行動裝置上。To do this, select **[!UICONTROL Show only on mobile devices]**.
例如，此選項可讓您在行動裝置上顯示特定影像，以及在桌面裝置上顯示其他影像。
您可以從行動裝置或桌面檢視設定此選項。

   ![](assets/email_designer_mobile_hide.png)

1. Click again the **[!UICONTROL Switch to mobile view]** button to go back to the standard desktop view. 您所做的樣式變更不會反映出來。

   ![](assets/email_designer_mobile_view_desktop_no-change.png)

   >[!NOTE]
   >
   >The only exception is the **[!UICONTROL Style inline]** settings. 任何樣式內嵌設定變更也會套用至標準桌面檢視。

1. 對結構或電子郵件內容的其他變更，例如文字編輯、上傳新影像、新增元件等。也會套用至標準檢視。

   例如，切換回行動裝置檢視，編輯某些文字並取代影像。

   ![](assets/email_designer_mobile_view_change_content.png)

   Click again the **[!UICONTROL Switch to mobile view]** button to go back to the standard desktop view. 系統會反映變更。

   ![](assets/email_designer_mobile_view_desktop_content-change.png)

1. 移除行動檢視中的樣式會帶您回到桌面模式中套用的樣式。

   例如，在行動檢視中，將綠色背景顏色套用至按鈕。

   ![](assets/email_designer_mobile_view_background_mobile.png)

1. 切換至桌面檢視，並將灰色背景套用至相同的按鈕。

   ![](assets/email_designer_mobile_view_background_desktop.png)

1. Switch again to mobile view, and now disable the **[!UICONTROL Background color]** setting.

   ![](assets/email_designer_mobile_view_background_mobile_disabled.png)

   現在已套用桌面檢視中定義的背景顏色：會變成灰色(非空白)。

   The only exception is the **[!UICONTROL Border color]** setting. 在行動檢視中停用時，即使在桌面檢視中定義邊框顏色，也不會再套用邊框。

## Plain text and HTML modes {#plain-text-and-html-modes}

### Generating a text version of the email {#generating-a-text-version-of-the-email}

By default, the **[!UICONTROL Plain text]** version of your email is automatically generated and synchronized with the **[!UICONTROL Edit]** version.

HTML版本中新增的個人化欄位和內容區塊也會與純文字版本同步。

>[!NOTE]
>
>若要使用純文字版本的內容區塊，請確定它們不包含HTML程式碼。

To have a plain text version different from the HTML version, you can disable this synchronization by clicking the **[!UICONTROL Sync with HTML]** switch from the **[!UICONTROL Plain text]** view of your email.

![](assets/email_designer_textversion.png)

然後您可以視需要編輯純文字版本。

>[!NOTE]
>
>If you edit the **[!UICONTROL Plain text]** version while synchronization is disabled, the next time you enable the **[!UICONTROL Sync with HTML]** option, all the changes you made in the plain text version will be replaced with the HTML version. **[!UICONTROL Plain text]** 檢視中所做的變更無法反映在 **[!UICONTROL HTML]** 檢視中。

### Editing an email content source in HTML {#editing-an-email-content-source-in-html}

對於大多數進階使用者和除錯，您可以直接在HTML中檢視並編輯電子郵件內容。

您有兩種方式可編輯電子郵件的HTML版本：

* Select **[!UICONTROL Edit]** &gt; **[!UICONTROL HTML]** to open the HTML version of the entire email.

   ![](assets/email_designer_html1.png)

* From the WYSIWYG interface, select an element and click the **[!UICONTROL Source code]** icon.

   只會顯示所選元素的來源。You can edit the source code if the selected element is a **[!UICONTROL HTML]** content component. 其他元件處於唯讀模式，但仍可在電子郵件的完整HTML版本中編輯。

   ![](assets/email_designer_html2.png)

如果您修改HTML程式碼，電子郵件的回應速度可能會中斷。Make sure to test it using the **[!UICONTROL Preview]** button. See [Previewing messages](../../sending/using/previewing-messages.md).

## Design through Adobe Campaign integrations {#design-through-adobe-campaign-integrations}

### Editing content in Dreamweaver {#editing-content-in-dreamweaver}

Adobe Campaign Standard與Dreamweaver的整合可讓您在Dreamweaver介面中編輯電子郵件的內容。您可存取強大的Dreamweaver介面，以設計和開發回應式電子郵件內容。

* **雙向同步**

   只要在一個產品中編輯，就會在另一個產品中即時更新。如果您想要變更Dreamweaver中文字的色彩，當您在進行編輯時，文字的色彩就會在Campaign中即時顯示。此外，當您在Dreamweaver或Campaign中選取程式碼時，由於行號是相同的，所以這兩種產品之間的選擇會維持不變，這在尋找程式碼中的特定內容時非常有用。

* **透過Dreamweaver將本機影像上傳至AC**

   在Dreamweaver中建立或編輯電子郵件時，您只需從桌上型電腦或本機電腦選取影像即可。雖然Dreamweaver一直允許您這麼做，但當Dreamweaver和Campaign連線時，本機檔案會立即上傳至Adobe Campaign伺服器：不需要隨著內容變更而手動上傳影像。此外，它可確保在Campaign中隨時都能使用最新的影像。

* **在Dreamweaver中新增促銷活動個人化**

   For the email developer there is no longer a need to add text like ```[[FIRSTNAME_PLACEHOLDER]]``` nor to look up the syntax of your data model’s tables. Dreamweaver中的促銷活動工具列會直接連線至您的促銷活動例項資料模型。也就是說，您可以從「名字」之類的「名字」中提取個人化的任何資料。如果您已在Campaign中建立了「內容區塊」，也可以直接將這些區塊提取到Dreamweaver中。

This capability is detailed in the Dreamweaver Documentation accessible [here](https://helpx.adobe.com/dreamweaver/using/working-with-dreamweaver-and-campaign.html). A demonstration [video](https://helpx.adobe.com/campaign/kt/acs/using/acs-dreamweaver-integration-feature-video-use.html) is also available.

### Editing content in Experience Manager {#editing-content-in-experience-manager}

您可以在Experience Manager中編輯電子郵件內容，然後在Adobe Campaign Standard中用於一或數個電子郵件訊息。Refer to [this document](../../integrating/using/integrating-with-experience-manager.md).

### Email design options comparison {#email-design-options-comparison}

Adobe Campaign提供數個電子郵件製作選項。下表顯示每個表格的主要可能性、優點和限制。

<table> 
 <thead> 
  <tr> 
   <th> </th> 
   <th> Email Designer<br /> </th> 
   <th> Experience Manager<br /> </th> 
   <th> Dreamweaver<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <strong>開始空白電子郵件</strong><br /> </td> 
   <td> Supported<br /> </td> 
   <td> Supported<br /> </td> 
   <td> Supported<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>編寫HTML</strong><br /> </td> 
   <td> Supported<br /> </td> 
   <td> Not supported<br /> </td> 
   <td> Supported<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>更新HTML</strong><br /> </td> 
   <td> Only inside an HTML component<br /> </td> 
   <td> Not supported<br /> </td> 
   <td> Supported<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>基本個人化</strong><br /> </td> 
   <td> Supported<br /> </td> 
   <td> Supported<br /> </td> 
   <td> Supported<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>進階個人化</strong><br /> </td> 
   <td> Supported<br /> </td> 
   <td> Not supported<br /> </td> 
   <td> Not supported<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>校樣/預覽</strong><br /> </td> 
   <td> Supported<br /> </td> 
   <td> Preview in AEM<br /> Proof in Campaign<br /> </td> 
   <td> Preview and proof in Campaign<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>產品清單</strong><br /> </td> 
   <td> Supported in email transactional messages<br /> </td> 
   <td> Not supported<br /> </td> 
   <td> Not supported<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>優點</strong><br /> </td> 
   <td> 
     - Easy email building through drag-and-drop experience<br/>
     - Functionalities similar to legacy content editor<br/>
     - Reusable content with fragments
  </td> 
   <td> 
     - Reusing assets from website in emails<br/>
     - Leveraging the power of Experience Manager in email contents
    </td> 
   <td> 
    - Capability for a developer to directly code an email<br/>
    - Bi-directional synchronization<br/>
    - Editing offline in Dreamweaver and synchronizing later<br/>
    - Uploading images to Adobe Campaign through Dreamweaver
  </td> 
  </tr> 
  <tr> 
   <td> <strong>限制</strong><br /> </td> 
   <td> 
     - No conditional content within fragments<br/>
     - Using Experience Manager fragments not possible
  </td> 
   <td> 
     - Advanced personalization difficult to implement<br/>
     - Need to send tests in Adobe Campaign
  </td> 
   <td> Dynamic content not supported<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>對象群</strong><br /> </td> 
   <td> Marketers who want to keep the flexibility to use HTML components in combination with drag-and-drop features<br /> </td> 
   <td> Marketers already using Experience Manager who want to use standard email templates with little personalization<br /> </td> 
   <td> Developers who want to code email contents and integrate directly with Adobe Campaign<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>若要進一步瞭解</strong><br /> </td> 
   <td> See <a href="../../designing/using/about-email-content-design.md#about-the-email-designer">About the Email Designer</a><br /> </td> 
   <td> See <a href="../../integrating/using/integrating-with-experience-manager.md">Integrating with Experience Manager</a><br /> </td> 
   <td> See <a href="https://helpx.adobe.com/dreamweaver/using/working-with-dreamweaver-and-campaign.html">Dreamweaver and Campaign</a> and watch this <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-dreamweaver-integration-feature-video-use.html">video</a><br /> </td> 
  </tr> 
 </tbody> 
</table>

