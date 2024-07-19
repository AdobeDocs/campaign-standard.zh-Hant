---
title: 將舊版編輯器電子郵件轉換為電子郵件Designer
description: 探索如何在舊版編輯器電子郵件中建立的電子郵件用於電子郵件Designer。
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: User
level: Intermediate
exl-id: 2b024052-ed42-44f3-9990-be7425cc79d7
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 8%

---

# 轉換舊版編輯器電子郵件內容 {#converting-an-html-content}

開始使用電子郵件Designer，並從在舊版編輯器中建立的電子郵件HTML中建立可重複使用的範本和片段。

此使用案例可讓您使用HTML電子郵件，並將其分割為電子郵件Designer中的HTML元件，以建立電子郵件Designer範本。

>[!NOTE]
>
>如同相容性模式，HTML元件可使用有限的選項進行編輯：您只能執行就地編輯。

>[!IMPORTANT]
>
>本節適用於熟悉HTML程式碼的進階使用者。

## 準備您的電子郵件內容

1. 選取HTML電子郵件。
1. 識別區段以劃分HTML電子郵件。
1. 從HTML中剪下不同的區塊。

## 建立您的電子郵件結構

1. 開啟&#x200B;**[!UICONTROL Email Designer]**&#x200B;以建立空的電子郵件內容。
1. 設定內文層級屬性：背景顏色、寬度等。 如需詳細資訊，請參閱[編輯電子郵件樣式](../../designing/using/styles.md)。
1. 新增任意數量的結構元件。 如需詳細資訊，請參閱「[編輯電子郵件結構](../../designing/using/designing-from-scratch.md#defining-the-email-structure)」。

## 新增HTML內容

1. 將HTML元件新增至每個結構元件。 如需詳細資訊，請參閱「[新增片段及元件](../../designing/using/designing-from-scratch.md#defining-the-email-structure)」。
1. 將HTML複製並貼到每個元件中。

## 管理電子郵件的風格 {#manage-the-style-of-your-email}

1. 切換至&#x200B;**[!UICONTROL Mobile view]**。 如需詳細資訊，請參閱[本節](../../designing/using/plain-text-html-modes.md#switching-to-mobile-view)。

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
   >請勿修改電子郵件Designer產生的CSS：
   >
   >* `<style data-name="default" type="text/css">(##)</style>`
   >* `<style data-name="supportIOS10" type="text/css">(##)</style>`
   >* `<style data-name="mediaIOS8" type="text/css">(##)</style>`
   >* `<style data-name="media-default-max-width-500px" type="text/css">(##)</style>`
   >* `<style data-name="media-default--webkit-min-device-pixel-ratio-0" type="text/css">(##)</style>`

1. 返回行動檢視以檢查您的內容是否正確顯示並儲存變更。

## 使用案例

讓我們嘗試將此在舊版編輯器中建立的電子郵件轉換為&#x200B;**[!UICONTROL Email Designer]**&#x200B;範本。

### 識別電子郵件的區段

我們可以識別此電子郵件中的11個區段。

![](assets/html-dce-view-mail.png)

若要識別哪個元素是HTML的哪個區段，您可以選取它。

![](assets/breadcrumbs.png)

若要檢視電子郵件的HTML版本，請按一下&#x200B;**[!UICONTROL Show source]**。

### 建立電子郵件範本及其結構

1. 拖放&#x200B;**[!UICONTROL Structure components]**&#x200B;以反映我們電子郵件的版面配置。

1. 視需要重複多次。 我們需要建立11個結構元件。

   ![](assets/structure-components-migration.png)

### 插入HTML內容元件

1. 在每個&#x200B;**[!UICONTROL Structure component]**&#x200B;中插入&#x200B;**[!UICONTROL HTML component]**。

   ![](assets/html-components.png)

1. 對於每個區段，按一下「**[!UICONTROL Show source code]**」。

   ![](assets/show-source-code.png)

1. 插入HTML區段。

1. 按一下&#x200B;**[!UICONTROL Save]**。

您現在可以檢查電子郵件的呈現。

![](assets/migrated-email-result.png)

### 管理樣式以符合行動檢視

1. 插入CSS元素，確保您的電子郵件適合行動裝置檢視。

1. 切換至原始程式碼，並將您的樣式區段複製貼到新的樣式區段中。

如需詳細資訊，請參閱[管理您的電子郵件樣式](#manage-the-style-of-your-email)。

您的舊版電子郵件現在可在「電子郵件Designer」中使用。
