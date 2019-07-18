---
title: 插入影像
seo-title: 插入影像
description: 插入影像
seo-description: 瞭解如何新增影像至您的內容。
page-status-flag: 從未啓動
uuid: ac42b1d3-50ad-4323-b474-1e50 e468901 f
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: design
content-type: reference
topic-tags: 使用影像
discoiquuid: ede832ac-96e5-41e1-8390-6669ba30d4d8
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a12df43de55dedf388a397fbf4670d99e3ea7f3d

---


# Inserting images{#inserting-images}

您可以在電子郵件和登陸頁面中插入影像。

視您的組態而定，可使用下列類型的影像：

* 局部影像
* Images shared from Adobe Experience Cloud - refer to [Working with Campaign and Assets Core Service](../../integrating/using/working-with-campaign-and-assets-core-service.md) / Assets On Demand
* Dynamic images from Adobe Target - refer to [Working with Campaign and Target](../../integrating/using/about-campaign-target-integration.md)

如果已啓用，您可以使用Adobe Creative SDK修改影像。See [Modifying images with the Adobe Creative SDK](../../designing/using/modifying-images-with-the-adobe-creative-sdk.md).

>[!CAUTION]
>
>If you choose to add an image directly by editing the HTML version of the email, you must not call up **external files in a &lt;script&gt; tag** of the HTML page. 這些檔案不會匯入Adobe Campaign伺服器。

## Inserting images in an email {#inserting-images-in-an-email}

1. 新增結構元件。For more on this, see [Editing the email structure](../../designing/using/defining-the-email-structure.md#editing-the-email-structure).
1. Inside this structure component, add an **[!UICONTROL Image]** content component.

   ![](assets/des_insert_images_1.png)

1. Click **[!UICONTROL Browse]**. 拖放影像，或按一下即可從電腦選取檔案。

   ![](assets/des_insert_images_2.png)

1. 選取您剛新增的內容元件。
1. 檢查影像屬性並視需要調整影像屬性。

   ![](assets/des_insert_images_3.png)

## Inserting images in a landing page {#inserting-images-in-a-landing-page}

1. 在著陸頁面內容中，選取包含影像的區塊。
1. Select the **[!UICONTROL Insert]** button.

   ![](assets/des_insert_images_lp_1.png)

1. Choose **[!UICONTROL Local image]** from the contextual toolbar.

   ![](assets/des_insert_images_lp_2.png)

1. 選取檔案。

   ![](assets/des_insert_images_lp_3.png)

1. 視需要調整影像屬性。

   ![](assets/des_insert_images_lp_4.png)

