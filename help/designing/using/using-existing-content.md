---
title: '使用現有內容設計電子郵件 '
description: 探索如何使用電子郵件設計工具中的現有內容電子郵件內容來設計電子郵件。
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: User
level: Intermediate
exl-id: 3bda4227-2a6e-4813-a288-93a4388a9787
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '1212'
ht-degree: 6%

---

# 使用現有內容進行設計 {#designing-using-existing-content}

## 選取現有內容{#selecting-an-existing-content}

Adobe Campaign隨附一組預先定義的內容，可協助您快速上手。 您可以使用其中一個，或者，如果您要傳送的訊息內容是在Adobe Campaign以外準備，則可從電腦或URL匯入。

建立電子郵件或登錄頁面時，您可以選擇從其他來源載入現有內容。

>[!NOTE]
>
>下圖顯示如何使用[電子郵件設計工具](../../designing/using/designing-content-in-adobe-campaign.md)載入現有內容。

1. 建立電子郵件或登錄頁面後，請開啟其內容。
1. 按一下首頁圖示以存取&#x200B;**[!UICONTROL Email Designer]**&#x200B;首頁。

   ![](assets/des_loading_1.png)

1. 選取要載入的內容來源：

   * [內容範本](../../designing/using/using-reusable-content.md#content-templates):按一下「 」 **[!UICONTROL Templates]** 標籤。
   * [從頭開始](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)，從頭開始：按一下 **[!UICONTROL Create]** 按鈕。
   * [以ZIP或HTML檔案形式從您的電腦取得內容](#importing-content-from-a-file):按一下 **[!UICONTROL Upload]** 按鈕。
   * [來自現有URL的內容](#importing-content-from-a-url) （僅適用於電子郵件）:按一下 **[!UICONTROL Import from URL]** 按鈕。

   ![](assets/des_loading_2.png)

1. 載入內容。 選取的內容會取代目前的內容。

   匯入後，即可編輯和個人化內容。

   >[!NOTE]
   >
   >[電子郵件設計工具](../../designing/using/designing-content-in-adobe-campaign.md)使用特定標籤。 上傳至Campaign的標準HTML內容必須符合預期的標籤，才能完全相容並可從電子郵件設計工具編輯。 若不相符，則會以[相容模式](#compatibility-mode)上傳您的內容。 要使現有內容相容，請參閱[本節](#editing-existing-contents-with-the-email-designer)。

**相關主題：**

* [建立電子郵件](../../channels/using/creating-an-email.md)
* [管理登錄頁面](../../channels/using/getting-started-with-landing-pages.md)

## 使用電子郵件設計工具編輯現有內容{#editing-existing-contents-with-the-email-designer}

要充分利用[電子郵件設計工具](../../designing/using/designing-content-in-adobe-campaign.md)的版本可能性，您上傳的HTML必須包含特定標籤，使其與WYSIWYG編輯器相容。

如果HTML的全部或部分沒有此標籤，則內容會以「 [相容模式](#compatibility-mode)」載入。

若要讓電子郵件設計工具中的現有外部內容完全可編輯，請參閱「使用現有內容設計電子郵件」小節[。](../../designing/using/using-existing-content.md)

## 匯入現有的電子郵件內容 {#importing}

### 從檔案匯入內容 {#importing-content-from-a-file}

從電子郵件設計工具首頁，按一下&#x200B;**[!UICONTROL Upload]**&#x200B;按鈕從電腦上傳檔案，然後確認。

zip檔案結構沒有限制。 不過，參考HTML檔案必須是相對的，並且會遵循zip資料夾的樹狀結構。

匯入支援下列格式：

* 包含合併樣式表的HTML檔案
* 包含HTML檔案、樣式表(.CSS)和影像的.zip資料夾

>[!NOTE]
>
>對於電子郵件內容，建議您匯入單一HTML檔案，並整合樣式表。

#### 從URL匯入內容 {#importing-content-from-a-url}

從URL匯入內容之前，請確定它遵循下列要求：

* 內容必須可透過此URL公開使用。
* 基於安全理由，僅允許以&#x200B;**[!UICONTROL https]**&#x200B;開頭的URL。
* 請確定所有資源（影像、CSS）都是在絕對連結和HTTPS中設定。 否則，傳送電子郵件後，將會顯示沒有其資源的鏡像頁面。 以下是絕對連結定義的範例：

   ```
   <a href="https://www.mywebsite.com/images/myimage.png">
   ```

>[!NOTE]
>
>從URL載入內容僅適用於電子郵件通道。

若要從URL擷取現有內容，請遵循下列步驟：

1. 從電子郵件設計工具首頁中，選擇&#x200B;**[!UICONTROL Import from URL]**&#x200B;按鈕。

   ![](assets/email_designer_importfromurl.png)

1. 定義要從中擷取內容的URL。
1. 按一下&#x200B;**[!UICONTROL Confirm]**。

在影片中探索此功能.

>[!VIDEO](https://video.tv.adobe.com/v/25926?quality=12)

其他Campaign Standard操作說明影片可在[此處](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=zh-Hant)取得。

### 準備時自動從URL擷取內容 {#retrieving-content-from-a-url-automatically-at-preparation-time}

在郵件準備期間從URL匯入內容，可讓您在每次準備電子郵件時擷取最新的HTML內容。 這樣，循環電子郵件的內容在傳送時一律為最新。 此功能也可讓您建立排程在特定日期的訊息，即使內容尚未就緒亦然。

若要在準備時擷取內容，請遵循下列步驟：

1. 選擇&#x200B;**[!UICONTROL Content imported during preparation]**&#x200B;選項。

   ![](assets/email_designer_importfromurl2.png)

1. URL內容在編輯器中顯示為唯讀。

   >[!CAUTION]
   >
   >在此步驟中，不應考慮內容編輯器中顯示的HTML。 會在準備階段擷取。

1. 若要預覽已擷取的URL內容，請在建立訊息後開啟訊息，然後按一下&#x200B;**[!UICONTROL Preview]**&#x200B;按鈕。

您可以個人化將從中擷取內容的遠端URL。 要執行此操作，請遵循下列步驟：

1. 按一下螢幕頂端的電子郵件標籤，以存取「電子郵件設計工具」 **[!UICONTROL Properties]**&#x200B;標籤。
1. 查找&#x200B;**[!UICONTROL Remote URL]**&#x200B;欄位。

   ![](assets/email_designer_importfromurl4.png)

1. 插入所需的個人化欄位、內容區塊或動態文字。

   例如，**[!UICONTROL Current date - YYYYMMDD]**&#x200B;內容區塊可讓您插入當天的日期。

   >[!NOTE]
   >
   >可用的個人化欄位僅連結至&#x200B;**傳送**&#x200B;屬性（電子郵件建立日期、狀態、促銷活動標籤……）。

### 相容性模式 {#compatibility-mode}

上傳內容時，必須包含特定標籤，才能與電子郵件設計工具的WYSIWYG編輯器完全相容且可編輯。

如果上傳的HTML的全部或部分不符合預期的標籤，則內容會以「相容模式」載入，這會限制透過UI進行版本的可能性。

以相容模式載入內容時，您仍可透過介面執行下列修改（隱藏不可用的動作）:

* 變更文字或變更影像
* 插入連結和個人化欄位
* 在選取的HTML區塊上編輯一些樣式選項
* 定義條件式內容

![](assets/email_designer_compatibility.png)

其他修改（例如新增區段至您的電子郵件或進階樣式）必須透過HTML模式，直接在電子郵件的原始碼中完成。

如需將現有電子郵件轉換為與電子郵件設計工具相容的電子郵件的詳細資訊，請參閱[此區段](../../designing/using/using-existing-content.md)。

**相關主題**：

* [建立電子郵件](../../channels/using/creating-an-email.md)
* [電子郵件設計工具簡介影片](../../designing/using/designing-content-in-adobe-campaign.md#video)
* [從草稿開始設計電子郵件內容](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)

## 轉換HTML內容 {#converting-an-html-content}

如果您想要建立模組化範本和片段的架構，可結合以在多封電子郵件中重複使用，您應考慮將電子郵件HTML轉換為電子郵件設計工具範本。

此使用案例提供將HTML電子郵件轉換為電子郵件設計工具元件的快速方式。

>[!CAUTION]
>
>本節適用於熟悉HTML程式碼的進階使用者。

>[!NOTE]
>
>與相容性模式一樣，HTML元件也是可編輯的，有限的選項有：您只能執行就地版本。

在電子郵件設計工具外，請確定原始HTML分為可重複使用的區段。

若非如此，請從HTML中剪下不同的區塊。 例如：

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

識別所有區塊後，在電子郵件設計工具中，對現有電子郵件的每個區段重複下列程式：

1. 開啟「電子郵件設計工具」以建立空白的電子郵件內容。
1. 設定內文層級屬性：背景顏色、寬度等。 如需詳細資訊，請參閱[編輯電子郵件樣式](../../designing/using/styles.md)。
1. 新增結構元件。 如需詳細資訊，請參閱「[編輯電子郵件結構](../../designing/using/designing-from-scratch.md#defining-the-email-structure)」。
1. 新增HTML元件。 如需詳細資訊，請參閱「[新增片段及元件](../../designing/using/designing-from-scratch.md#defining-the-email-structure)」。
1. 將HTML複製並貼到該元件中。
1. 切換至行動檢視。 如需詳細資訊，請參閱[本節](../../designing/using/plain-text-html-modes.md#switching-to-mobile-view)。

   回應式檢視因您的CSS遺失而中斷。

1. 若要修正此問題，請切換至原始碼模式，並將樣式區段複製並貼到新樣式區段中。 例如：

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
   >請務必在另一個自訂樣式標籤中，於此之後新增您的樣式。
   >
   >請勿修改電子郵件設計工具產生的CSS:
   >
   >* `<style data-name="default" type="text/css">(##)</style>`
   >* `<style data-name="supportIOS10" type="text/css">(##)</style>`
   >* `<style data-name="mediaIOS8" type="text/css">(##)</style>`
   >* `<style data-name="media-default-max-width-500px" type="text/css">(##)</style>`
   >* `<style data-name="media-default--webkit-min-device-pixel-ratio-0" type="text/css">(##)</style>`


1. 返回行動檢視，檢查您的內容是否正確顯示並儲存您的變更。
