---
title: 使用現有內容設計電子郵件
description: 瞭解如何使用電子郵件設計器中的現有內容電子郵件內容設計電子郵件。
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: User
level: Intermediate
exl-id: 3bda4227-2a6e-4813-a288-93a4388a9787
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '1280'
ht-degree: 5%

---

# 使用現有內容設計 {#designing-using-existing-content}

## 選擇現有內容{#selecting-an-existing-content}

Adobe Campaign提供了一組預定義的內容，幫助您開始使用。 您可以使用其中一種，或者，如果您需要發送的郵件的內容是在Adobe Campaign之外準備的，則可以從您的電腦或URL導入它。

建立電子郵件或登錄頁時，您可以選擇從其他源載入現有內容。

>[!NOTE]
>
>下圖顯示了如何使用 [電子郵件設計器](../../designing/using/designing-content-in-adobe-campaign.md)。

1. 建立電子郵件或登錄頁後，開啟其內容。
1. 按一下「首頁」表徵圖訪問 **[!UICONTROL Email Designer]** 的子菜單。

   ![](assets/des_loading_1.png)

1. 選擇要載入的內容的源：

   * [內容模板](../../designing/using/using-reusable-content.md#content-templates):按一下 **[!UICONTROL Templates]** 頁籤。
   * [從頭開始的內容](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)，開始刷新：按一下 **[!UICONTROL Create]** 按鈕
   * [作為ZIP或HTML檔案從您的電腦中發送的內容](#importing-content-from-a-file):按一下 **[!UICONTROL Upload]** 按鈕
   * [來自現有URL的內容](#importing-content-from-a-url) （僅用於電子郵件）:按一下 **[!UICONTROL Import from URL]** 按鈕

   ![](assets/des_loading_2.png)

1. 載入內容。 所選內容將替換當前內容。

   導入後，內容可以編輯和個性化。

   >[!NOTE]
   >
   >的 [電子郵件設計器](../../designing/using/designing-content-in-adobe-campaign.md) 使用特定標籤。 上載到「市場活動」的標準HTML內容必須與預期的標籤相匹配，才能從電子郵件設計器中完全相容和可編輯。 如果不匹配，則將在 [相容模式](#compatibility-mode)。 要使現有內容相容，請參見 [此部分](#editing-existing-contents-with-the-email-designer)。

**相關主題：**

* [建立電子郵件](../../channels/using/creating-an-email.md)
* [管理登錄頁](../../channels/using/getting-started-with-landing-pages.md)

## 使用電子郵件設計器編輯現有內容{#editing-existing-contents-with-the-email-designer}

充分利用 [電子郵件設計器](../../designing/using/designing-content-in-adobe-campaign.md)，上載的HTML必須包含使其符合WYSIWYG編輯器的特定標籤。

如果HTML的全部或部分沒有此標籤，則內容將載入到「 」中 [相容模式](#compatibility-mode)「 」。

要使現有外部內容在電子郵件設計器中完全可編輯，請參見 [使用現有內容設計電子郵件](../../designing/using/using-existing-content.md) 的子菜單。

## 導入現有電子郵件內容 {#importing}

### 從檔案導入內容 {#importing-content-from-a-file}

在「電子郵件設計器」首頁中，按一下 **[!UICONTROL Upload]** 按鈕從電腦上載檔案，然後確認。

zip檔案結構沒有約束。 但是，引用HTML檔案必須是相對的，並且要考慮zip資料夾的樹結構。

導入支援以下格式：

* 具有合併樣式表的HTML檔案
* 包含HTML檔案、樣式表(.CSS)和影像的.zip資料夾

>[!NOTE]
>
>對於電子郵件內容，我們建議您導入具有合併樣式表的單個HTML檔案。

#### 從URL導入內容 {#importing-content-from-a-url}

在從URL導入內容之前，請確保它遵循以下要求：

* 內容需要通過此URL公開。
* 出於安全原因，僅URL以開頭 **[!UICONTROL https]** 的子菜單。
* 確保在絕對連結和HTTPS中設定所有資源（影像、CSS）。 否則，在發送電子郵件後，將在沒有其資源的情況下顯示鏡像頁面。 下面是絕對連結定義的示例：

   ```
   <a href="https://www.mywebsite.com/images/myimage.png">
   ```

>[!NOTE]
>
>從URL載入內容僅可用於電子郵件通道。

要從URL中檢索現有內容，請執行以下步驟：

1. 從「電子郵件設計器」首頁中，選擇 **[!UICONTROL Import from URL]** 按鈕

   ![](assets/email_designer_importfromurl.png)

1. 定義從中檢索內容的URL。
1. 按一下&#x200B;**[!UICONTROL Confirm]**。

在影片中探索此功能.

>[!VIDEO](https://video.tv.adobe.com/v/25926?quality=12)

可提供其他Campaign Standard操作視頻 [這裡](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=zh-Hant)。

### 在準備時自動從URL檢索內容 {#retrieving-content-from-a-url-automatically-at-preparation-time}

在準備郵件期間從URL導入內容，使您能夠在每次準備電子郵件時檢索最新的HTML內容。 這樣，循環電子郵件的內容在發送時始終是最新的。 此功能還允許您建立在特定日期計畫的消息，即使內容尚未準備好。

要在準備時檢索內容，請執行以下步驟：

1. 選擇 **[!UICONTROL Content imported during preparation]** 的雙曲餘切值。

   ![](assets/email_designer_importfromurl2.png)

1. URL內容在編輯器中顯示為只讀。

   >[!CAUTION]
   >
   >在此步驟中，不應考慮內容編輯器中的HTML顯示。 將在準備階段檢索。

1. 要預覽已檢索的URL內容，請在建立消息後開啟該消息，然後按一下 **[!UICONTROL Preview]** 按鈕

可以個性化將從中檢索內容的遠程URL。 要執行此操作，請遵循下列步驟：

1. 按一下螢幕頂部的電子郵件標籤以訪問電子郵件設計器 **[!UICONTROL Properties]** 頁籤。
1. 查找 **[!UICONTROL Remote URL]** 的子菜單。

   ![](assets/email_designer_importfromurl4.png)

1. 插入所需的個性化欄位、內容塊或動態文本。

   的 **[!UICONTROL Current date - YYYYMMDD]** 例如，內容塊允許您插入日期。

   >[!NOTE]
   >
   >可用的個性化欄位連結到 **交貨** 僅屬性（電子郵件建立日期、狀態、市場活動標籤……）。

如果內容下載在第一次嘗試時失敗，可以重試兩次：

1. 第二次嘗試在第一次嘗試後50毫秒開始。
1. 第三次嘗試在第二次嘗試後100毫秒開始。

這些重試在以下情況下非常有用：

* 遠程伺服器上的短時服務故障
* 群集上的伺服器故障，在這種情況下，由於對工作伺服器進行負載平衡，重試更有可能成功

### 相容模式 {#compatibility-mode}

上載內容時，它必須包含特定標籤才能與電子郵件設計器的WYSIWYG編輯器完全相容和可編輯。

如果上載HTML的全部或部分與預期的標籤不相容，則內容將以「相容模式」載入，這會限制通過UI的編輯可能性。

在相容模式下載入內容時，您仍可以通過介面執行以下修改（不可用的操作被隱藏）:

* 更改文本或更改影像
* 插入連結和個性化欄位
* 編輯所選HTML塊上的某些樣式選項
* 定義條件內容

![](assets/email_designer_compatibility.png)

其他修改（如在電子郵件中添加新節或高級樣式）必須通過HTML模式直接在電子郵件的原始碼中進行。

有關將現有電子郵件轉換為與電子郵件設計器相容的電子郵件的詳細資訊，請參見 [此部分](../../designing/using/using-existing-content.md)。

**相關主題**：

* [建立電子郵件](../../channels/using/creating-an-email.md)
* [電子郵件設計器簡介視頻](../../designing/using/designing-content-in-adobe-campaign.md#video)
* [從頭設計電子郵件內容](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)

## 轉換HTML內容 {#converting-an-html-content}

如果要構建一個模組化模板和片段框架，這些模板和片段可以組合起來以在多個電子郵件中重複使用，您應考慮將電子郵件HTML轉換為電子郵件設計器模板。

此使用案例提供了將HTML電子郵件轉換為電子郵件設計器元件的快速方法。

>[!CAUTION]
>
>此部分適用於熟悉HTML代碼的高級用戶。

>[!NOTE]
>
>與相容性模式一樣，HTML元件可編輯，其選項有限：只能執行就地版。

在電子郵件設計器外，確保將原始HTML分為可重複使用的部分。

如果情況不是這樣，則從HTML上切出不同的塊。 例如：

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

確定所有塊後，在電子郵件設計器中，對現有電子郵件的每個部分重複以下步驟：

1. 開啟電子郵件設計器以建立空的電子郵件內容。
1. 設定正文級屬性：背景顏色、寬度等。 如需詳細資訊，請參閱[編輯電子郵件樣式](../../designing/using/styles.md)。
1. 添加結構元件。 如需詳細資訊，請參閱「[編輯電子郵件結構](../../designing/using/designing-from-scratch.md#defining-the-email-structure)」。
1. 添加HTML元件。 如需詳細資訊，請參閱「[新增片段及元件](../../designing/using/designing-from-scratch.md#defining-the-email-structure)」。
1. 將HTML複製貼上到該元件中。
1. 切換到行動檢視. 如需詳細資訊，請參閱[本節](../../designing/using/plain-text-html-modes.md#switching-to-mobile-view)。

   響應視圖已斷開，因為缺少CSS。

1. 要解決此問題，請切換到原始碼模式，並將樣式節複製貼上到新樣式節中。 例如：

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
   >確保在此之後在另一個自定義樣式標籤中添加樣式。
   >
   >不要修改電子郵件設計器生成的CSS:
   >
   >* `<style data-name="default" type="text/css">(##)</style>`
   >* `<style data-name="supportIOS10" type="text/css">(##)</style>`
   >* `<style data-name="mediaIOS8" type="text/css">(##)</style>`
   >* `<style data-name="media-default-max-width-500px" type="text/css">(##)</style>`
   >* `<style data-name="media-default--webkit-min-device-pixel-ratio-0" type="text/css">(##)</style>`


1. 返回到移動視圖，檢查內容是否正確顯示並保存更改。
