---
title: '使用現有內容設計電子郵件 '
description: 探索如何使用電子郵件設計工具中現有的內容電子郵件內容來設計電子郵件。
page-status-flag: never-activated
uuid: 571ffc01-6e41-4501-9094-2f812b041a10
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: designing
content-type: reference
topic-tags: editing-email-content
discoiquuid: 39b86fda-7766-4e5f-ab48-bcc536ab66b3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 9e17218048daa091538a09dea6e2eabca0814a5f

---

# Designing using existing content {#designing-using-existing-content}

## 選取現有內容{#selecting-an-existing-content}

Adobe Campaign隨附一組預先定義的內容，以協助您開始使用。 您可以使用其中一項，或者，如果您需要傳送的訊息內容是在Adobe Campaign以外準備，則可從電腦或URL匯入。

建立電子郵件或登陸頁面時，您可以選擇從其他來源載入現有內容。

>[!NOTE]
>
>下圖顯示如何使用電子郵件設計器載入現有 [內容](../../designing/using/overview.md)。

1. 建立電子郵件或登陸頁面後，請開啟其內容。
1. 按一下首頁圖示以存取 **[!UICONTROL Email Designer]** 首頁。

   ![](assets/des_loading_1.png)

1. 選取您要載入之內容的來源：

   * [內容範本](../../designing/using/using-reusable-content.md#content-templates):按一下標 **[!UICONTROL Templates]** 簽。
   * [從頭開始](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)，開始創作：按一下按 **[!UICONTROL Create]** 鈕。
   * [以ZIP或HTML檔案形式從您的電腦取得內容](#importing-content-from-a-file):按一下按 **[!UICONTROL Upload]** 鈕。
   * [來自現有URL的內容](#importing-content-from-a-url) （僅限電子郵件）:按一下按 **[!UICONTROL Import from URL]** 鈕。
   ![](assets/des_loading_2.png)

1. 載入內容。 選取的內容會取代目前的內容。

   匯入後，內容就可以編輯並個人化。

   >[!NOTE]
   >
   >電子郵 [件設計器](../../designing/using/overview.md) (Email Designer)使用特定標籤。 上傳至Campaign的標準HTML內容必須符合預期的標籤，才能完全相容並可從電子郵件設計工具編輯。 如果不符合，您的內容會以相容模式 [上傳](#compatibility-mode)。 若要讓現有內容相容，請參 [閱本節](#editing-existing-contents-with-the-email-designer)。

**相關主題：**

* [建立電子郵件](../../channels/using/creating-an-email.md)
* [管理著陸頁面](../../channels/using/getting-started-with-landing-pages.md)

## 使用電子郵件設計工具編輯現有內容{#editing-existing-contents-with-the-email-designer}

若要充份運用電子郵件設計工具的 [版本可能性](../../designing/using/overview.md)，您上傳的HTML必須包含特定的標籤，才能與WYSIWYG編輯器相容。

如果HTML的全部或部分沒有此標籤，則內容會以「相容模式 [](#compatibility-mode)」載入。

若要讓現有的外部內容在電子郵件設計器中完全可編輯，請參 [閱使用現有內容設計電子郵件](../../designing/using/using-existing-content.md) 。

## 匯入現有的電子郵件內容 {#importing}

### 從檔案匯入內容 {#importing-content-from-a-file}

在「電子郵件設計器」首頁中，按一 **[!UICONTROL Upload]** 下按鈕，從電腦上傳檔案，然後確認。

zip檔案結構沒有限制。 但是，參照HTML檔案必須是相對的，並且必須遵循zip檔案夾的樹狀結構。

匯入支援下列格式：

* 包含合併樣式表的HTML檔案
* 包含HTML檔案、樣式表(.CSS)和影像的。zip檔案夾

>[!NOTE]
>
>對於電子郵件內容，我們建議您匯入包含樣式表的單一HTML檔案。

#### 從URL匯入內容 {#importing-content-from-a-url}

在從URL匯入內容之前，請務必遵循下列要求：

* 內容必須透過此URL公開提供。
* 出於安全原因，僅允許以開頭 **[!UICONTROL https]** 的URL。
* 請確定所有資源（影像、CSS）都已設定在絕對連結和HTTPS中。 否則，在發送電子郵件後，鏡像頁面將不會顯示其資源。 以下是絕對連結定義的範例：

   ```
   <a href="https://www.mywebsite.com/images/myimage.png">
   ```

>[!NOTE]
>
>從URL載入內容僅適用於電子郵件頻道。

若要從URL擷取現有內容，請遵循下列步驟：

1. 從「電子郵件設計器」首頁中，選擇該 **[!UICONTROL Import from URL]** 按鈕。

   ![](assets/email_designer_importfromurl.png)

1. 定義將從中擷取內容的URL。
1. Click **[!UICONTROL Confirm]**.

**相關主題：**

[從URL視訊匯入內容](https://helpx.adobe.com/campaign/kt/acs/using/acs-email-designer-tutorial.html#Workingwithexistingcontent)

### 準備時自動從URL擷取內容 {#retrieving-content-from-a-url-automatically-at-preparation-time}

在準備訊息時從URL匯入內容，可讓您在每次準備電子郵件時擷取最新的HTML內容。 如此，循環電子郵件的內容在傳送時都會隨時更新。 此功能也可讓您建立排程在特定日期的訊息，即使內容尚未就緒亦然。

若要在準備時擷取內容，請遵循下列步驟：

1. 選擇選 **[!UICONTROL Content imported during preparation]** 項。

   ![](assets/email_designer_importfromurl2.png)

1. URL內容會在編輯器中顯示為唯讀。

   >[!CAUTION]
   >
   >在此步驟中，不應將內容編輯器中顯示的HTML納入考量。 將在準備階段檢索。

1. 若要預覽已擷取的URL內容，請在建立訊息後開啟訊息，然後按一下按 **[!UICONTROL Preview]** 鈕。

您可以個人化將擷取內容的遠端URL。 若要這麼做，請依照下列步驟進行：

1. 按一下畫面上方的電子郵件標籤，以存取「電子郵件設計器」 **[!UICONTROL Properties]** 標籤。
1. 尋找欄 **[!UICONTROL Remote URL]** 位。

   ![](assets/email_designer_importfromurl4.png)

1. 插入所需的個人化欄位、內容區塊或動態文字。

   例 **[!UICONTROL Current date - YYYYMMDD]** 如，內容區塊可讓您插入當天的日期。

   >[!NOTE]
   >
   >可用的個人化欄位僅連結 **至「傳送** 」屬性（電子郵件建立日期、狀態、促銷活動標籤……）。

### 相容模式 {#compatibility-mode}

上傳內容時，它必須包含特定標籤，才能與「電子郵件設計器」的WYSIWYG編輯器完全相容並可編輯。

如果所上傳的HTML的全部或部分不符合預期的標籤，則內容會以「相容模式」載入，這會限制透過UI的版本可能性。

當內容以相容模式載入時，您仍可透過介面執行下列修改（隱藏不可用的動作）:

* 變更文字或變更影像
* 插入連結和個人化欄位
* 在選取的HTML區塊上編輯某些樣式選項
* 定義條件式內容

![](assets/email_designer_compatibility.png)

其他修改（例如在電子郵件中新增章節或進階樣式）必須直接在電子郵件的原始碼中透過HTML模式進行。

有關將現有電子郵件轉換為與電子郵件設計人員相容的電子郵件的詳細資訊，請參 [閱本節](../../designing/using/using-existing-content.md)。

**相關主題**:

* [建立電子郵件](../../channels/using/creating-an-email.md)
* [電子郵件設計人員簡介影片](https://video.tv.adobe.com/v/22771/?autoplay=true&hidetitle=true&captions=chi_hant)
* [從頭設計電子郵件內容](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)

## 轉換HTML內容 {#converting-an-html-content}

如果您想要建立模組範本和片段的架構，以便結合在多封電子郵件中重複使用，您應考慮將電子郵件的HTML轉換為電子郵件設計人員範本。

此使用案例提供將HTML電子郵件轉換為電子郵件設計器元件的快速方式。

>[!CAUTION]
>
>本節適用於熟悉HTML程式碼的進階使用者。

>[!NOTE]
>
>和相容性模式一樣，HTML元件也可編輯，但選項有限：您只能執行就地版本。

在「電子郵件設計器」外，請確定原始HTML會分為可重複使用的區段。

如果不是這樣，請從HTML中剪下不同的區塊。 例如：

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

在您識別所有區塊後，請在「電子郵件設計器」中，針對現有電子郵件的每個區段重複下列步驟：

1. 開啟「電子郵件設計工具」以建立空的電子郵件內容。
1. 設定主體級別屬性：背景顏色、寬度等。 如需詳細資訊，請參閱「編輯 [電子郵件樣式](../../designing/using/styles.md)」。
1. 添加結構元件。 如需詳細資訊，請參閱「 [編輯電子郵件結構」](../../designing/using/designing-from-scratch.md#defining-the-email-structure)。
1. 新增HTML元件。 如需詳細資訊，請參 [閱新增片段和元件](../../designing/using/designing-from-scratch.md#defining-the-email-structure)。
1. 將HTML複製並貼入該元件。
1. 切換至行動裝置檢視。 有關此內容的詳細資訊，請參 [閱本節](../../designing/using/plain-text-html-modes.md#switching-to-mobile-view)。

   回應式檢視會中斷，因為您的CSS遺失。

1. 若要修正此問題，請切換至原始碼模式，並將樣式區段複製貼至新的樣式區段。 例如：

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
   >請務必在此之後，在另一個自訂樣式標籤中新增您的樣式。
   >
   >請勿修改電子郵件設計人員產生的CSS:
   >
   >* `<style data-name="default" type="text/css">(##)</style>`
   >* `<style data-name="supportIOS10" type="text/css">(##)</style>`
   >* `<style data-name="mediaIOS8" type="text/css">(##)</style>`
   >* `<style data-name="media-default-max-width-500px" type="text/css">(##)</style>`
   >* `<style data-name="media-default--webkit-min-device-pixel-ratio-0" type="text/css">(##)</style>`


1. 返回行動裝置檢視，檢查您的內容是否正確顯示並儲存變更。
