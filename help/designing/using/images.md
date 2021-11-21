---
title: 使用影像
description: 了解如何使用電子郵件設計工具管理電子郵件中的影像。
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: User
level: Intermediate
exl-id: b58a378d-18da-4c0f-b4e7-5d0a02aab4c2
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 3%

---

# 使用影像 {#images}

## 插入影像{#inserting-images}

您可以在電子郵件和登錄頁面中插入影像。

根據您的配置，可使用下列類型的影像：

* 本機影像
* 從Adobe Experience Cloud共用的影像 — 請參閱 [協作使用Campaign與Assets核心服務](../../integrating/using/working-with-campaign-and-assets-core-service.md) /隨選資產
* 來自Adobe Target的動態影像 — 請參閱 [協作使用Campaign與Target](../../integrating/using/about-campaign-target-integration.md)

>[!CAUTION]
>
>If you choose to add an image directly by editing the HTML version of the email, you must not call up **external files in a &lt;script> tag** of the HTML page. 這些檔案將不會匯入Adobe Campaign伺服器。

### 在電子郵件中插入影像 {#inserting-images-in-an-email}

1. 新增結構元件。 如需詳細資訊，請參閱「[編輯電子郵件結構](../../designing/using/designing-from-scratch.md#defining-the-email-structure)」。
1. 在此結構元件內，新增 **[!UICONTROL Image]** 內容元件。

   ![](assets/des_insert_images_1.png)

1. 按一下 **[!UICONTROL Browse]**。拖放影像，或按一下以從電腦選取檔案。

   ![](assets/des_insert_images_2.png)

1. 選取您剛新增的內容元件。
1. 檢查影像屬性，並視需要進行調整。

   ![](assets/des_insert_images_3.png)

## 設定影像屬性{#setting-up-image-properties}

選取包含影像的區塊時，浮動視窗中會提供下列屬性：

* **啟用個人化** 可讓您自訂影像來源。 請參閱 [個人化影像來源](../../designing/using/personalization.md#personalizing-an-image-source).
* **影像標題** 可讓您定義影像的標題。
* **替代文字** （電子郵件）或 **註解** （登陸頁面）可讓您定義連結至影像的註解(與 **alt** HTML屬性)。
* 編輯電子郵件時， **樣式** 可讓您指定影像大小、背景和邊框。
* 編輯登錄頁面時， **Dimension** 可讓您以像素指定影像大小。

編輯器可讓您使用 **所有影像類型** 其格式與瀏覽器相容。 若要與編輯器相容， **&quot;Flash&quot;類型動畫** 必須依照下列方式插入HTML頁面：

```
<object type="application/x-shockwave-flash" data="http://www.mydomain.com/flash/your_animation.swf" width="200" height="400">
 <param name="movie" value="http://www.mydomain.com/flash/your_animation.swf" />
 <param name="quality" value="high" />
 <param name="play" value="true"/>
 <param name="loop" value="true"/> 
</object>
```

<!--
## Modifying images with the Adobe Creative SDK{#modifying-images-with-the-adobe-creative-sdk}

You can edit images and use a complete set of features powered by the Adobe Creative SDK to enhance your images directly in the content editor when editing emails or landing pages.

The image editor offers a powerful, full-featured image editing UI component that allows you to edit images and apply effects and frames, original high-quality stickers, beautiful overlays, fun features like tilt shift and color splash, pro-level adjustments and more.

To modify an image with the Adobe Creative SDK:

1. Select the image.
1. In the toolbar, click the Creative Cloud icon.

   ![](assets/des_creative_sdk_icon.png)

1. Select the tool you want to use through the icons on the top of the window to modify the image.

   ![](assets/email_designer_ccsdktoolbar.png)

1. Click **[!UICONTROL Save]** when modifications are done. The updated image is saved on Adobe Campaign server and ready to be used.

>[!NOTE]
>
>Tools offered in the image editor cannot be customized.
-->
