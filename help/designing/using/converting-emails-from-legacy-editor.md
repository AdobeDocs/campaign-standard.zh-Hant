---
title: 將舊版編輯器電子郵件轉換為電子郵件設計器
description: 瞭解如何使用在舊版編輯器電子郵件中建立的電子郵件到電子郵件設計器。
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: User
level: Intermediate
exl-id: 2b024052-ed42-44f3-9990-be7425cc79d7
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 8%

---

# 轉換舊版編輯器電子郵件內容 {#converting-an-html-content}

開始使用電子郵件設計器，並從舊版編輯器中建立的電子郵件HTML中構建可重用的模板和片段。

此使用例允許您使用HTML電子郵件並將其劃分為電子郵件設計器中的HTML元件，從而建立電子郵件設計器模板。

>[!NOTE]
>
>與相容性模式一樣，HTML元件可編輯，其選項有限：只能執行就地版。

>[!IMPORTANT]
>
>此部分適用於熟悉HTML代碼的高級用戶。

## 準備電子郵件內容

1. 選擇HTML電子郵件。
1. 標識要分隔HTML電子郵件的部分。
1. 從你的HTML上切出不同的區塊。

## 建立電子郵件結構

1. 開啟 **[!UICONTROL Email Designer]**  建立空電子郵件內容。
1. 設定正文級屬性：背景顏色、寬度等。 如需詳細資訊，請參閱[編輯電子郵件樣式](../../designing/using/styles.md)。
1. 添加的結構元件數與截面數相同。 如需詳細資訊，請參閱「[編輯電子郵件結構](../../designing/using/designing-from-scratch.md#defining-the-email-structure)」。

## 添加HTML內容

1. 將HTML元件添加到每個結構元件。 如需詳細資訊，請參閱「[新增片段及元件](../../designing/using/designing-from-scratch.md#defining-the-email-structure)」。
1. 將HTML複製貼上到每個元件中。

## 管理電子郵件的樣式 {#manage-the-style-of-your-email}

1. 切換到 **[!UICONTROL Mobile view]**。 如需詳細資訊，請參閱[本節](../../designing/using/plain-text-html-modes.md#switching-to-mobile-view)。

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

## 使用案例

讓我們嘗試將在舊版編輯器中建立的此電子郵件轉換為 **[!UICONTROL Email Designer]** 的下界。

### 確定電子郵件的部分

我們可以在此電子郵件中識別11個部分。

![](assets/html-dce-view-mail.png)

要標識HTML的哪個部分是元素，可以選擇它。

![](assets/breadcrumbs.png)

要查看電子郵件的HTML版本，請按一下 **[!UICONTROL Show source]**。

### 建立電子郵件模板及其結構

1. 拖放 **[!UICONTROL Structure components]**  反映了我們電子郵件的佈局。

1. 根據需要重複多次。 我們需要創造11個結構部件。

   ![](assets/structure-components-migration.png)

### 插入HTML內容元件

1. 插入 **[!UICONTROL HTML component]**  每 **[!UICONTROL Structure component]** 。

   ![](assets/html-components.png)

1. 對於每個節，按一下 **[!UICONTROL Show source code]** 。

   ![](assets/show-source-code.png)

1. 插入HTML部分。

1. 按一下&#x200B;**[!UICONTROL Save]**。

您現在可以檢查電子郵件的呈現。

![](assets/migrated-email-result.png)

### 管理樣式以適應移動視圖

1. 插入CSS元素，確保電子郵件適合移動視圖。

1. 切換到原始碼，然後將樣式節複製貼上到新樣式節。

有關此內容的詳細資訊，請參閱 [管理電子郵件的樣式](#manage-the-style-of-your-email)。

您的舊式電子郵件現在可在電子郵件設計器中使用。
