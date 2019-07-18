---
title: 著陸頁面內容編輯器介面
seo-title: 著陸頁面內容編輯器介面
description: 著陸頁面內容編輯器介面
seo-description: 瞭解如何使用編輯器的不同區段(例如動作列)修改著陸頁面內容。
page-status-flag: 從未啓動
uuid: 53729a68-ester2-4c5 d-bc14-02c80 e897 c44
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: design
content-type: reference
topic-tags: editing-landing-page-content
discoiquuid: 08e2bda-e409-467f-b462-d74256 dc6 eBC
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 76c3d473f6cc7e825fdabadeec2405cb5c13abd1

---


# Landing page content editor interface{#landing-page-content-editor-interface}

著陸頁面內容編輯器可讓您輕鬆定義、修改和個人化Adobe Campaign中的內容。To access it, click the **[!UICONTROL Content]** block in a landing page dashboard.

內容編輯器可分為三個不同區段。這些區段可讓您檢視和編輯內容。

![](assets/des_lp_content_8.png)

1. The **palette** on the left-hand side of the screen allows you to modify the general options linked to a selected block. 可修改的選項為：背景顏色、邊框、文字對齊、可見度條件等。See [Inserting a personalization field](../../designing/using/inserting-a-personalization-field.md).
1. **動作列** 包含頁面的一般選項。您可以選取範本並變更顯示模式。See [Landing page editor action bar](../../designing/using/landing-page-content-editor-interface.md#landing-page-editor-action-bar).
1. The main **editing zone** allows you to directly interact with the content using the contextual toolbar: insert a link into an image, change the font, delete a field, etc. See [Landing page editor toolbar](../../designing/using/landing-page-content-editor-interface.md#landing-page-editor-toolbar).

## Landing page editor action bar {#landing-page-editor-action-bar}

動作列包含不同的按鈕，可讓您與正在建立的內容互動。

![](assets/des_lp_content_9.png)

<table> 
 <thead> 
  <tr> 
   <th> Icon<br /> </th> 
   <th> Button name<br /> </th> 
   <th> Channel<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <img height="21px" src="assets/download_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">變更內容</span><br /> </td> 
   <td> Landing page and email<br /> </td> 
   <td> 可讓您選取立即可用的內容，或匯入您自己的HTML內容。Refer to <a href="../../designing/using/selecting-an-existing-content.md">Loading an existing content</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/undo_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">還原</span><br /> </td> 
   <td> All<br /> </td> 
   <td> Cancels the last action carried out.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/redo_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">重做</span><br /> </td> 
   <td> All<br /> </td> 
   <td> Redoes the last action that you canceled.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/display_block_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">顯示區塊</span><br /> </td> 
   <td> Landing page and email<br /> </td> 
   <td> Allows you to show the boxes around the content blocks (corresponds to the <strong>&lt;div&gt;</strong> HTML tag).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/code_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">顯示來源</span><br /> </td> 
   <td> Landing page and email<br /> </td> 
   <td> Allows you to show the HTML source code of the page.<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Landing page editor toolbar {#landing-page-editor-toolbar}

The toolbar is a **contextual element** of the editor interface that offers various functionalities depending on the zone selected. 它包含動作按鈕和按鈕，可讓您變更文字樣式。執行的修改一律適用於選取的區域。當您選取區塊後，可以刪除或複製它。在區塊中選取文字後，您可以將它轉換為連結或使其大膽。

![](assets/delivery_content_17.png)

>[!CAUTION]
>
>某些工具列函數可讓您格式化HTML內容。However, if the page contains a CSS style sheet, the **instructions** from the style sheet may prove to take **priority** over the instructions specified via the toolbar.

<table> 
 <thead> 
  <tr> 
   <th> Icon<br /> </th> 
   <th> Button name<br /> </th> 
   <th> Context<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <img height="21px" src="assets/link_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">連結至外部URL</span><br /> </td> 
   <td> Any element<br /> </td> 
   <td> 可讓您新增URL連結。<a href="../../designing/using/inserting-a-link.md">插入連結</a> 區段中會顯示如何設定連結的詳細資訊。<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/linkpage_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">連結至登陸頁面</span><br /> </td> 
   <td> Any element<br /> </td> 
   <td> 允許存取Adobe Campaign登陸頁面。<a href="../../designing/using/inserting-a-link.md">插入連結</a> 區段中會顯示如何設定連結的詳細資訊。<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/link_subscribe_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">訂閱連結</span><br /> </td> 
   <td> Any element<br /> </td> 
   <td> 可讓您插入服務訂閱連結。<a href="../../designing/using/inserting-a-link.md">插入連結</a> 區段中會顯示如何設定連結的詳細資訊。<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/link_unsubscribe_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">取消訂閱連結</span><br /> </td> 
   <td> Any element<br /> </td> 
   <td> 可讓您插入服務取消訂閱連結。<a href="../../designing/using/inserting-a-link.md">插入連結</a> 區段中會顯示如何設定連結的詳細資訊。<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/linkoff_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">移除連結</span><br /> </td> 
   <td> Link<br /> </td> 
   <td> Allows you to delete the link, as well as all the configurations linked to it, after confirming.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/personalization_field_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">插入個人化欄位</span><br /> </td> 
   <td> Text element<br /> </td> 
   <td> 可讓您將欄位從資料庫新增至內容。Refer to <a href="../../designing/using/inserting-a-personalization-field.md">Inserting a personalization field</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/personalization_block_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">插入內容區塊</span><br /> </td> 
   <td> Text element<br /> </td> 
   <td> 可讓您新增個人化區塊至內容。Refer to <a href="../../designing/using/adding-a-content-block.md">Adding a content block</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/dynamiccontent_24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">啓用動態內容</span><br /> </td> 
   <td> Text element<br /> </td> 
   <td> 可讓您在內容中插入動態內容。Refer to <a href="../../designing/using/defining-dynamic-content-in-a-landing-page.md">Defining dynamic content</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/dynamiccontentdisable_24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">停用動態內容</span><br /> </td> 
   <td> Text element<br /> </td> 
   <td> Allows you to delete dynamic content.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/increase_fontsize_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">大型字體</span><br /> </td> 
   <td> Text element<br /> </td> 
   <td> Increases the size of the selected text (adds <strong>&lt;span style="font-size:"&gt;</strong>).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/decrease_fontsize_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">減少字型</span><br /> </td> 
   <td> Text element<br /> </td> 
   <td> Reduces the size of the selected text (adds <strong>&lt;span style="font-size:"&gt;</strong>).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/textbold_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">粗體</span><br /> </td> 
   <td> Text element<br /> </td> 
   <td> Adds the bold style to the selected text (wraps the text with the <strong>&lt;strong&gt;</strong><strong>&lt;/strong&gt;</strong> tags).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/textitalic_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">斜體</span><br /> </td> 
   <td> Text element<br /> </td> 
   <td> Adds the italic style to the selected text (wraps the text with the <strong>&lt;em&gt;</strong><strong>&lt;/em&gt;</strong> tags).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/textunderline_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">底線</span><br /> </td> 
   <td> Text element<br /> </td> 
   <td> Underlines the selected text (wraps the selected text with the <strong>&lt;span style="text-decoration: underline;"&gt;</strong> tag).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/colorselector_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">變更背景顏色</span><br /> </td> 
   <td> Text element<br /> </td> 
   <td> Allows you to change the background color of the block selected (adds style="background-color: rgba(170, 86, 255, 0.87)).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/textcolor_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">變更字體顏色</span><br /> </td> 
   <td> Text element<br /> </td> 
   <td> Allows you to change the color of all the text in the block or just the text selected in the block (<strong>&lt;span style="color: #56ff56;"&gt;</strong>).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/image_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">影像</span><br /> </td> 
   <td> Block containing an image<br /> </td> 
   <td> Allows you to insert an image from a file saved locally.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/delete_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">刪除</span><br /> </td> 
   <td> Any block<br /> </td> 
   <td> Deletes the block and its content.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/duplicate_fontsize_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">複製重復</span><br /> </td> 
   <td> Any block<br /> </td> 
   <td> Duplicates the block including any styles linked to it.<br /> </td> 
  </tr> 
 </tbody> 
</table>

