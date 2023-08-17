---
title: 使用影像
description: 探索如何使用電子郵件設計工具管理電子郵件中的影像。
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

您可以在電子郵件和登入頁面中插入影像。

視您的設定而定，可使用下列影像型別：

* 本機影像
* 從Adobe Experience Cloud共用的影像 — 請參閱 [合作使用Campaign與Assets核心服務](../../integrating/using/working-with-campaign-and-assets-core-service.md) /隨選資產
* 來自Adobe Target的動態影像 — 請參閱 [合作使用Campaign與Target](../../integrating/using/about-campaign-target-integration.md)

>[!CAUTION]
>
>如果您選擇透過編輯電子郵件的HTML版本來直接新增影像，則不得呼叫 **中的外部檔案 &lt;script> 標籤** HTML頁面的。 這些檔案將不會匯入至Adobe Campaign伺服器。

### 在電子郵件中插入影像 {#inserting-images-in-an-email}

1. 新增結構元件。 如需詳細資訊，請參閱「[編輯電子郵件結構](../../designing/using/designing-from-scratch.md#defining-the-email-structure)」。
1. 在此結構元件內，新增 **[!UICONTROL Image]** 內容元件。

   ![](assets/des_insert_images_1.png)

1. 按一下 **[!UICONTROL Browse]**。拖放影像或按一下以從電腦中選取檔案。

   ![](assets/des_insert_images_2.png)

1. 選取您剛才新增的內容元件。
1. 檢查影像屬性，並視需要加以調整。

   ![](assets/des_insert_images_3.png)

## 設定影像屬性{#setting-up-image-properties}

當您選取包含影像的區塊時，浮動視窗中提供下列屬性：

* **啟用個人化** 可讓您自訂影像來源。 另請參閱 [個人化影像來源](../../designing/using/personalization.md#personalizing-an-image-source).
* **影像標題** 可讓您定義影像的標題。
* **替代文字** （電子郵件）或 **註解** （登陸頁面）可讓您定義連結至影像的標題(對應至 **alt** HTML屬性)。
* 編輯電子郵件時， **樣式** 可讓您指定影像大小、背景和邊框。
* 編輯登入頁面時， **Dimension** 可讓您指定影像大小（畫素）。

編輯器可讓您使用 **所有影像型別** 其格式與瀏覽器相容。 要與編輯器相容，請 **「Flash」型別動畫** 必須插入到HTML頁面中，如下所示：

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
