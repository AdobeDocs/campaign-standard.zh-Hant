---
title: 新增Target動態內容
seo-title: 新增Target動態內容
description: 新增Target動態內容
seo-description: 瞭解如何在您的Adobe Campaign傳遞中新增Adobe Target動態內容。
page-status-flag: 從未啓動
uuid: b3cc045f-7924-480e-8c61-8246510f3adb
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 整合
content-type: reference
topic-tags: 使用促銷活動與定位
discoiquuid: 45ddf7b7-98f7-4fdd-bb4 a-49ec8490 e877
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 698466596fdacd005dc4d72b8071208c8c39f77d

---


# Adding Target dynamic content{#adding-target-dynamic-content}

透過Adobe Target整合，可將動態影像加入到傳送中，以根據體驗個人化。

編輯電子郵件時，您可以從Adobe Target插入動態影像，而這會隨著收件者而改變。

在Adobe Campaign中存取影像之前，下列工作必須先在Adobe Target中執行：

* Create one or several [redirect offers](https://marketing.adobe.com/resources/help/en_US/tnt/help/t_Creating_a_Redirect_Offer.html), in which you must specify the URL of the image you will be using.
* Create one or several [audiences](https://marketing.adobe.com/resources/help/en_US/target/ov/c_about_segments.html), to define the target of your activity.
* Create a [Form-based experience composer](https://marketing.adobe.com/resources/help/en_US/target/target/t_form_experience_composer.html) activity, in which you have to select a rawbox and specify several experiences, depending on the number of redirect offers created. 對於每個體驗，您必須選取其中一個重新導向選件。
* 使用Adobe Campaign資訊來建立區段以指定體驗。若要在選件的選取規則中使用Adobe Campaign中的資料，您必須在Adobe Target的rawbox中指定資料。

1. 建立電子郵件傳送。
1. When editing the content of an email or a landing page, go to an image block, then select **[!UICONTROL Dynamic image from Adobe Target]** via the contextual menu.

   ![](assets/tar_insert_dynamic_image.png)

1. 選取電子郵件中預設顯示的影像。You can directly specify the image URL or select an image shared via [Assets](../../integrating/using/working-with-campaign-and-assets-core-service.md).

   此整合僅支援靜態影像。其他內容無法自訂。

1. 輸入Adobe Target中指定的rawbox名稱。
1. 如果您在Adobe Target的設定中使用「企業版」權限，請在此欄位中新增對應的屬性。Learn more about Target Enterprise permissions in [this page](https://marketing.adobe.com/resources/help/en_US/target/target/properties-overview.html). 此欄位為選擇性欄位，如果您不使用Target中的「企業版」權限，則不需要此欄位。
1. In **[!UICONTROL Additional decision parameters]**, specify the mapping between the fields defined in the Adobe Target segments and the Adobe Campaign fields.

   使用的Adobe Campaign欄位必須在rawbox中指定。在此，我們將根據收件者性別定義不同的體驗。

   ![](assets/tar_additional_decisionning_parameters.png)

1. 預覽您的電子郵件，以瞭解在選取不同的描述檔時，插入的影像會根據Adobe Target活動中指定的參數以及Adobe Campaign中指定的參數而變更。

現在可以傳送包含動態影像的傳送。其結果可在Adobe Target中找到。

**相關主題：**

* [Adobe Target Portal](https://marketing.adobe.com/resources/help/en_US/target/a4t/c_campaign_and_target.html)
* [關於電子郵件內容設計](../../designing/using/about-email-content-design.md)
* [在即時](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html) 視訊中個人化電子郵件影像

