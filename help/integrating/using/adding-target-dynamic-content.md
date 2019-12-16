---
title: 新增 Target 動態內容
description: 瞭解如何將Adobe target動態內容新增至您的Adobe Campaign傳遞內容。
page-status-flag: never-activated
uuid: b3cc045f-7924-480e-8c61-8246510f3adb
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-target
discoiquuid: 45ddf7b7-98f7-4fdd-bb4a-49ec8490e877
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 594b2d3c3dcc1ec13ab06ca6219ad59fe1a267d8

---


# 新增 Target 動態內容{#adding-target-dynamic-content}

透過Adobe target整合，動態影像可以新增至傳送中，以根據體驗個人化您的內容。

在編輯電子郵件時，您可以插入Adobe Target的動態影像，該動態影像會視收件者而有所變更。

在Adobe Campaign中存取影像之前，必須先在Adobe target中執行下列工作：

* 建立一或多個 [重新導向選件](https://docs.adobe.com/content/help/en/target/using/experiences/offers/offer-redirect.html)，您必須在其中指定要使用的影像URL。
* 建立一或多個 [觀眾](https://docs.adobe.com/content/help/en/target/using/audiences/create-audiences/audiences.html)，以定義您活動的目標。
* 建立 [表單式體驗撰寫器活動](https://docs.adobe.com/content/help/en/target/using/experiences/form-experience-composer.html) ，您必須在其中選取rawbox並指定數個體驗，視所建立的重新導向選件數目而定。 您必須針對每個體驗選取其中一個已建立的重新導向選件。
* 使用Adobe Campaign的資訊建立群體，以指定體驗。 若要在選件的選擇規則中使用Adobe Campaign的資料，您必須在Adobe Target的rawbox中指定資料。

1. 建立電子郵件傳送。
1. 編輯電子郵件或著陸頁面的內容時，請移至影像區塊，然後透過內容相 **[!UICONTROL Dynamic image from Adobe Target]** 關選單選擇。

   ![](assets/tar_insert_dynamic_image.png)

1. 選取預設會出現在電子郵件中的影像。 您可以直接指定影像URL或選取透過資產共用的 [影像](../../integrating/using/working-with-campaign-and-assets-core-service.md)。

   整合僅支援靜態影像。 其他內容無法自訂。

1. 輸入在Adobe Target中指定之rawbox的名稱。
1. 如果您在Adobe target的設定中使用「企業版」權限，請在此欄位中新增對應的屬性。 在此頁面中進一步瞭解Target Enterprise [權限](https://marketing.adobe.com/resources/help/en_US/target/target/properties-overview.html)。 如果您未在Target中使用「企業版」權限，此欄位是選用欄位，而非必要欄位。
1. 在 **[!UICONTROL Additional decision parameters]**&#x200B;中，指定Adobe target區段中定義的欄位與Adobe Campaign欄位之間的對應。

   使用的Adobe Campaign欄位必須已在rawbox中指定。 在此，我們將根據受助者的性別定義不同的體驗。

   ![](assets/tar_additional_decisionning_parameters.png)

1. 預覽您的電子郵件，以查看選取不同的描述檔時，影像插入的變更是否取決於在Adobe Target活動和Adobe Campaign中指定的參數。

現在可以傳送包含動態影像的傳送內容。 其結果可在Adobe Target中找到。

**相關主題：**

* [Adobe Target Portal](https://marketing.adobe.com/resources/help/en_US/target/a4t/c_campaign_and_target.html)
* [關於電子郵件內容設計](../../designing/using/designing-content-in-adobe-campaign.md)
* [在即時視訊中個人化電子郵件影像](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html)

