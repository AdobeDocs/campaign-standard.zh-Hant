---
title: '將舊版編輯器電子郵件轉換為電子郵件設計人員 '
description: 瞭解如何使用舊版編輯器電子郵件中建立的電子郵件給電子郵件設計人員。
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
source-git-commit: 1de0f5362f3c77fec4b66e330a2d2723f4a0f212

---


# 轉換舊版編輯器電子郵件內容 {#converting-an-html-content}

開始使用電子郵件設計工具，並從舊版編輯器中建立的電子郵件HTML中建立可重複使用的範本和片段。

此使用案例可讓您使用HTML電子郵件，並將其分為「電子郵件設計器」中的HTML元件，以建立「電子郵件設計器」範本。

>[!CAUTION]
>
>本節適用於熟悉HTML程式碼的進階使用者。

>[!NOTE]
>
>和相容性模式一樣，HTML元件也可編輯，但選項有限：您只能執行就地版本。

## 準備您的電子郵件內容

1. 選擇HTML電子郵件。
1. 識別要劃分HTML電子郵件的區段。
1. 從HTML中剪下不同的區塊。

## 建立您的電子郵件結構

1. 開啟以 **[!UICONTROL Email Designer]** 建立空的電子郵件內容。
1. 設定主體級別屬性：背景顏色、寬度等。 如需詳細資訊，請參閱「編輯 [電子郵件樣式](../../designing/using/styles.md)」。
1. 添加任意數量的結構元件（如有章節）。 如需詳細資訊，請參閱「 [編輯電子郵件結構」](../../designing/using/designing-from-scratch.md#defining-the-email-structure)。

## 新增HTML內容

1. 將HTML元件新增至每個結構元件。 如需詳細資訊，請參 [閱新增片段和元件](../../designing/using/designing-from-scratch.md#defining-the-email-structure)。
1. 將HTML複製並貼至每個元件。

## 管理電子郵件的樣式 {#manage-the-style-of-your-email}

1. 切換至 **[!UICONTROL Mobile view]**。 For more on this, see [this section](../../designing/using/plain-text-html-modes.md#switching-to-mobile-view).

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

## 使用案例

讓我們嘗試將這封在舊版編輯器中建立的電子郵件轉換為范 **[!UICONTROL Email Designer]** 本。

## 識別您電子郵件的章節

我們可以識別此電子郵件中的11個章節。

![](assets/html-dce-view-mail.png)

若要識別HTML的哪個區段是哪個元素，您可以選取它。

![](assets/breadcrumbs.png)

若要查看電子郵件的HTML版本，請按一下 **[!UICONTROL Show source]**。

### 建立電子郵件範本及其結構

1. 拖放以反 **[!UICONTROL Structure Components]** 映我們電子郵件的版面配置。

我們需要建立11個結構元件。

![](assets/structure-components-migration.png)

### 插入HTML內容元件

1. 在每 **[!UICONTROL HTML component]** 個中插入 **[!UICONTROL structure component]** 。

![](assets/html-components.png)

1. 針對每個區段，按一下 **[!UICONTROL Show source code]** 。

![](assets/show-source-code.png)

1. 插入HTML區段。

1. 按一下 **[!UICONTROL Save]**.

您現在可以檢查電子郵件的轉換。

![](assets/migrated-email-result.png)

### 管理樣式以符合行動裝置檢視

插入CSS元素，以確保您的電子郵件適合行動裝置檢視。

1. 切換至原始碼，並將樣式區段複製貼至新的樣式區段。

如需詳細資訊，請參 [閱「管理電子郵件樣式」](#manage-the-style-of-your-email)。

您的舊式電子郵件現在可從電子郵件設計工具取得。