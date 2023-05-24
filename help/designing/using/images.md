---
title: 使用影像
description: 瞭解如何使用電子郵件設計器管理電子郵件中的影像。
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

您可以在電子郵件和登錄頁中插入影像。

根據您的配置，可以使用以下類型的映像：

* 本地影像
* 從Adobe Experience Cloud共用的映像 — 請參閱[使用市場活動和資產核心服務](../../integrating/using/working-with-campaign-and-assets-core-service.md) /按需資產
* 來自Adobe Target的動態映像 — 請參閱[使用市場活動和目標](../../integrating/using/about-campaign-target-integration.md)

>[!CAUTION]
>
>如果您選擇通過編輯電子郵件的HTML版本直接添加影像，則不得在HTML頁的&lt;script>標籤&#x200B;**中調用**&#x200B;外部檔案。這些檔案不會導入到Adobe Campaign伺服器上。

### 在電子郵件中插入影像 {#inserting-images-in-an-email}

1. 添加結構元件。如需詳細資訊，請參閱「[編輯電子郵件結構](../../designing/using/designing-from-scratch.md#defining-the-email-structure)」。
1. 在此結構元件內，添加&#x200B;**[!UICONTROL Image]**&#x200B;內容元件。

   ![](assets/des_insert_images_1.png)

1. 按一下 **[!UICONTROL Browse]**。拖放影像或按一下以從電腦中選擇檔案。

   ![](assets/des_insert_images_2.png)

1. 選擇剛添加的內容元件。
1. 檢查影像屬性並根據需要調整它們。

   ![](assets/des_insert_images_3.png)

## 設定影像屬性{#setting-up-image-properties}

選擇包含影像的塊時，調色板中提供以下屬性：

* ****&#x200B;請參閱[個性化影像源](../../designing/using/personalization.md#personalizing-an-image-source)。
* **影像標題**&#x200B;允許您為影像定義標題。
* **Alt文本**（電子郵件）或&#x200B;**標題**（登錄頁）允許您定義連結到影像的標題(與&#x200B;**alt** HTML屬性對應)。
* 編輯電子郵件時，**樣式**&#x200B;允許您指定影像大小、背景和邊框。
* 編輯登錄頁時，**Dimension**&#x200B;允許您以像素為單位指定影像大小。

編輯器允許您使用格式與瀏覽器相容的&#x200B;**所有影像類型**。要與編輯器相容， **&quot;Flash&quot;類型動畫** 必須按如下方式插入HTML頁：

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
