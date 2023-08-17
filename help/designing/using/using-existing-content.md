---
title: 使用現有內容設計電子郵件
description: 探索如何使用電子郵件設計工具中的現有內容電子郵件內容來設計電子郵件。
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

# 使用現有內容進行設計 {#designing-using-existing-content}

## 選取現有內容{#selecting-an-existing-content}

Adobe Campaign隨附一組預先定義的內容，協助您開始使用。 您可以使用其中一個，或者，如果您需要傳送的訊息內容是在Adobe Campaign之外準備，您可以從您的電腦或URL匯入。

建立電子郵件或登入頁面時，您可以選擇從其他來源載入現有內容。

>[!NOTE]
>
>以下影像顯示如何使用載入現有內容 [電子郵件設計工具](../../designing/using/designing-content-in-adobe-campaign.md).

1. 建立電子郵件或登入頁面後，開啟其內容。
1. 按一下首頁圖示以存取 **[!UICONTROL Email Designer]** 首頁。

   ![](assets/des_loading_1.png)

1. 選取您要載入的內容來源：

   * [內容範本](../../designing/using/using-reusable-content.md#content-templates)：按一下 **[!UICONTROL Templates]** 標籤。
   * [從頭開始的內容](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)，以重新開始：按一下 **[!UICONTROL Create]** 按鈕。
   * [ZIP或HTML檔案形式的電腦內容](#importing-content-from-a-file)：按一下 **[!UICONTROL Upload]** 按鈕。
   * [來自現有URL的內容](#importing-content-from-a-url) （僅適用於電子郵件）：按一下 **[!UICONTROL Import from URL]** 按鈕。

   ![](assets/des_loading_2.png)

1. 載入內容。 選取的內容會取代目前的內容。

   匯入內容後，即可編輯內容並加以個人化。

   >[!NOTE]
   >
   >此 [電子郵件設計工具](../../designing/using/designing-content-in-adobe-campaign.md) 使用特定標籤。 上傳至Campaign的標準HTML內容必須符合預期的標籤，才能完全相容並可從電子郵件設計工具編輯。 如果不相符，您的內容將會上傳到 [相容性模式](#compatibility-mode). 若要讓現有內容相容，請參閱 [本節](#editing-existing-contents-with-the-email-designer).

**相關主題：**

* [建立電子郵件](../../channels/using/creating-an-email.md)
* [管理登入頁面](../../channels/using/getting-started-with-landing-pages.md)

## 使用電子郵件設計工具編輯現有內容{#editing-existing-contents-with-the-email-designer}

若要充分利用 [電子郵件設計工具](../../designing/using/designing-content-in-adobe-campaign.md)，您上傳的HTML必須包含特定標籤，以符合WYSIWYG編輯器。

如果全部或部分HTML沒有此標籤，內容則會載入『 [相容性模式](#compatibility-mode)&#39;.

若要在電子郵件設計工具中讓現有的外部內容完全可編輯，請參閱 [使用現有內容設計電子郵件](../../designing/using/using-existing-content.md) 區段。

## 匯入現有的電子郵件內容 {#importing}

### 從檔案匯入內容 {#importing-content-from-a-file}

從電子郵件設計工具首頁，按一下 **[!UICONTROL Upload]** 按鈕從電腦上傳檔案，然後確認。

zip檔案結構沒有限制。 但是，參考HTML檔案必須是相對的，並且遵守zip資料夾的樹狀結構。

匯入支援下列格式：

* 包含內建樣式表的HTML檔案
* 包含HTML檔案、樣式表(.CSS)和影像的.zip資料夾

>[!NOTE]
>
>針對電子郵件內容，建議您匯入具有合併樣式表的單一HTML檔案。

#### 從URL匯入內容 {#importing-content-from-a-url}

從URL匯入內容之前，請確定它遵循以下要求：

* 內容必須透過此URL公開可用。
* 基於安全理由，僅限開頭為的URL **[!UICONTROL https]** 是允許的。
* 請確定所有資源（影像、CSS）都設定在絕對連結和HTTPS中。 否則，在傳送電子郵件後，映象頁面會顯示且沒有其資源。 以下是絕對連結定義的範例：

  ```
  <a href="https://www.mywebsite.com/images/myimage.png">
  ```

>[!NOTE]
>
>從URL載入內容僅適用於電子郵件頻道。

若要從URL擷取現有內容，請遵循下列步驟：

1. 從電子郵件設計工具首頁，選取 **[!UICONTROL Import from URL]** 按鈕。

   ![](assets/email_designer_importfromurl.png)

1. 定義將從中擷取內容的URL。
1. 按一下&#x200B;**[!UICONTROL Confirm]**。

在影片中探索此功能.

>[!VIDEO](https://video.tv.adobe.com/v/25926?quality=12)

提供其他Campaign Standard操作影片 [此處](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=zh-Hant).

### 在準備時從URL自動擷取內容 {#retrieving-content-from-a-url-automatically-at-preparation-time}

在郵件準備期間從URL匯入內容，可讓您在每次準備電子郵件時擷取最新的HTML內容。 如此一來，循環電子郵件的內容在傳送時一定是最新的。 此功能也可讓您建立排程於特定日期的訊息，即使內容尚未準備就緒亦然。

若要在準備時擷取內容，請遵循下列步驟：

1. 選取 **[!UICONTROL Content imported during preparation]** 選項。

   ![](assets/email_designer_importfromurl2.png)

1. URL內容在編輯器中顯示為唯讀。

   >[!CAUTION]
   >
   >在此步驟中，不應將內容編輯器中顯示的HTML納入考量。 它將在準備階段擷取。

1. 若要預覽已擷取的URL內容，請在建立訊息後開啟訊息，然後按一下 **[!UICONTROL Preview]** 按鈕。

您可以個人化遠端URL，以擷取內容。 要執行此操作，請遵循下列步驟：

1. 按一下熒幕頂端的電子郵件標籤以存取電子郵件設計工具 **[!UICONTROL Properties]** 標籤。
1. 尋找 **[!UICONTROL Remote URL]** 欄位。

   ![](assets/email_designer_importfromurl4.png)

1. 插入所需的個人化欄位、內容區塊或動態文字。

   此 **[!UICONTROL Current date - YYYYMMDD]** 例如，內容區塊可讓您插入當天的日期。

   >[!NOTE]
   >
   >可用的個人化欄位已連結至 **傳遞** 僅限屬性（電子郵件建立日期、狀態、行銷活動標籤……）。

如果內容下載在第一次嘗試時失敗，可以重試兩次：

1. 第二次嘗試在第一次嘗試後50毫秒開始。
1. 第三次嘗試於第二次嘗試後100毫秒開始。

這些重試方式對於以下情況很有幫助：

* 遠端伺服器上的短期服務失敗
* 叢集上的伺服器發生失敗，在這種情況下，由於工作伺服器的負載平衡，重試更有可能成功

### 相容性模式 {#compatibility-mode}

上傳內容時，內容必須包含特定標籤，才能與電子郵件設計工具的WYSIWYG編輯器完全相容且可編輯。

如果全部或部分上傳的HTML不符合預期的標籤，內容則會在「相容模式」中載入，這會限制透過UI編輯的可能性。

以相容模式載入內容時，您仍可透過介面執行下列修改（隱藏無法使用的動作）：

* 變更文字或影像
* 插入連結和個人化欄位
* 在選取的HTML區塊上編輯一些樣式選項
* 定義條件式內容

![](assets/email_designer_compatibility.png)

其他修改（例如將新區段新增至您的電子郵件或進階樣式）必須透過HTML模式直接在電子郵件的原始碼中完成。

如需將現有電子郵件轉換為與電子郵件設計工具相容之電子郵件的詳細資訊，請參閱 [本節](../../designing/using/using-existing-content.md).

**相關主題**：

* [建立電子郵件](../../channels/using/creating-an-email.md)
* [電子郵件設計工具的簡介影片](../../designing/using/designing-content-in-adobe-campaign.md#video)
* [從草稿開始設計電子郵件內容](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)

## 轉換HTML內容 {#converting-an-html-content}

如果您想要建立模組化範本和片段的架構，以便合併在多個電子郵件中重複使用，您應考慮將您的電子郵件HTML轉換為電子郵件設計工具範本。

此使用案例提供一種將HTML電子郵件快速轉換為電子郵件設計工具元件的方法。

>[!CAUTION]
>
>本節適用於熟悉HTML程式碼的進階使用者。

>[!NOTE]
>
>如同相容性模式，HTML元件可使用有限的選項進行編輯：您只能執行就地編輯。

在電子郵件設計工具之外，請確定原始HTML被分成可重複使用的區段。

如果不是這種情況，請從您的HTML中剪下不同的區塊。 例如：

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

在識別所有區塊後，在電子郵件設計工具中，針對現有電子郵件的每個區段重複下列程式：

1. 開啟「電子郵件設計工具」以建立空的電子郵件內容。
1. 設定內文層級屬性：背景顏色、寬度等。 如需詳細資訊，請參閱[編輯電子郵件樣式](../../designing/using/styles.md)。
1. 新增結構元件。 如需詳細資訊，請參閱「[編輯電子郵件結構](../../designing/using/designing-from-scratch.md#defining-the-email-structure)」。
1. 新增HTML元件。 如需詳細資訊，請參閱「[新增片段及元件](../../designing/using/designing-from-scratch.md#defining-the-email-structure)」。
1. 將您的HTML複製並貼到該元件中。
1. 切換到行動檢視. 如需詳細資訊，請參閱[本節](../../designing/using/plain-text-html-modes.md#switching-to-mobile-view)。

   回應式檢視中斷，因為您的CSS遺失。

1. 若要修正此問題，請切換到原始程式碼模式，並將您的樣式區段複製貼到新的樣式區段中。 例如：

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
   >請務必將您的樣式新增至另一個自訂樣式標籤中。
   >
   >請勿修改電子郵件設計工具產生的CSS：
   >
   >* `<style data-name="default" type="text/css">(##)</style>`
   >* `<style data-name="supportIOS10" type="text/css">(##)</style>`
   >* `<style data-name="mediaIOS8" type="text/css">(##)</style>`
   >* `<style data-name="media-default-max-width-500px" type="text/css">(##)</style>`
   >* `<style data-name="media-default--webkit-min-device-pixel-ratio-0" type="text/css">(##)</style>`

1. 返回行動檢視以檢查您的內容是否正確顯示並儲存變更。
