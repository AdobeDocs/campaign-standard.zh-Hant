---
title: 設定影像屬性
seo-title: 設定影像屬性
description: 設定影像屬性
seo-description: 瞭解如何管理內容中包含的影像屬性。
page-status-flag: 從未啓動
uuid: 1a439105-d9 aa-4b30-a00 d-bcf731 a04 e08
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: design
content-type: reference
topic-tags: 使用影像
discoiquuid: 80c9c1a5-6050-443d-810a-6bb755dca
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Setting up image properties{#setting-up-image-properties}

當您選取包含影像的區塊時，浮動視窗中提供下列屬性：

* **啓用個人化** 可讓您自訂影像來源。See [Personalizing an image source](../../designing/using/personalizing-an-image-source.md).
* **影像標題** 可讓您定義影像的標題。
* **Alt文字** (電子郵件)或 **標題** (登陸頁面)可讓您定義連結至影像的標題(對應 **至alt** HTML屬性)。
* When editing an email, **Style** lets you specify the image size, background, and border.
* When editing a landing page, **Dimensions** lets you specify the image size in pixels.

The editor allows you to work with **all image types** whose formats are compatible with browsers. To be compatible with the editor, the **"Flash" type animations** have to be inserted in an HTML page as follows:

```
<object type="application/x-shockwave-flash" data="http://www.mydomain.com/flash/your_animation.swf" width="200" height="400">
 <param name="movie" value="http://www.mydomain.com/flash/your_animation.swf" />
 <param name="quality" value="high" />
 <param name="play" value="true"/>
 <param name="loop" value="true"/> 
</object>
```

