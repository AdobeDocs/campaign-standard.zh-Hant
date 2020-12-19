---
solution: Campaign Standard
product: campaign
title: 使用影像
description: 瞭解如何使用電子郵件設計工具管理電子郵件中的影像。
audience: designing
content-type: reference
topic-tags: editing-email-content
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 3%

---


# 使用影像{#images}

## 插入影像{#inserting-images}

您可以在電子郵件和登陸頁面中插入影像。

根據您的設定，可使用下列影像類型：

* 本機影像
* 從Adobe Experience Cloud共用的影像——請參閱[使用促銷活動和資產核心服務](../../integrating/using/working-with-campaign-and-assets-core-service.md) /隨選資產
* 來自Adobe Target的動態影像——請參閱[使用促銷活動和Target](../../integrating/using/about-campaign-target-integration.md)

>[!CAUTION]
>
>如果您選擇編輯電子郵件的HTML版本以直接新增影像，則不得在HTML頁面的&lt;script>標籤&#x200B;**中呼叫**&#x200B;外部檔案。 這些檔案不會匯入至Adobe Campaign伺服器。

### 在電子郵件{#inserting-images-in-an-email}中插入影像

1. 添加結構元件。 如需詳細資訊，請參閱「[編輯電子郵件結構](../../designing/using/designing-from-scratch.md#defining-the-email-structure)」。
1. 在此結構元件中，新增&#x200B;**[!UICONTROL Image]**&#x200B;內容元件。

   ![](assets/des_insert_images_1.png)

1. 按一下 **[!UICONTROL Browse]**。拖放影像，或按一下以從您的電腦選取檔案。

   ![](assets/des_insert_images_2.png)

1. 選取您剛新增的內容元件。
1. 檢查影像屬性並視需要調整。

   ![](assets/des_insert_images_3.png)

## 設定影像屬性{#setting-up-image-properties}

當您選取包含影像的區塊時，浮動視窗中會提供下列屬性：

* **啟用** 個人化可讓您自訂影像來源。請參閱[個人化影像來源](../../designing/using/personalization.md#personalizing-an-image-source)。
* **影像** 標題可讓您定義影像的標題。
* **Alt text** (email)或 **Caption** (landing page)可讓您定義連結至影像的標題(與 **** altHTML屬性相對應)。
* 編輯電子郵件時，**Style**&#x200B;可讓您指定影像大小、背景和邊框。
* 編輯著陸頁面時，**Dimensions**&#x200B;可讓您以像素指定影像大小。

編輯器允許您使用與瀏覽器相容的格式&#x200B;**的所有影像類型**。 為與編輯器相容，**&quot;Flash&quot;類型的動畫**&#x200B;必須插入HTML頁面，如下所示：

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