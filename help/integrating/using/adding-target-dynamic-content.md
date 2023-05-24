---
title: 新增 Target 動態內容
description: 瞭解如何將Adobe Target動態內容添加到您的Adobe Campaign交付內容之一。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-target
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: 7dfbd89f-877e-4598-bfe3-d743bb31ae9e
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '444'
ht-degree: 5%

---

# 新增 Target 動態內容{#adding-target-dynamic-content}

通過Adobe Target整合，可以將動態映像添加到交付中，以根據您的體驗對您的內容進行個性化。

編輯電子郵件時，可以插入來自Adobe Target的動態影像，該影像會根據收件人的不同而發生更改。

在訪問Adobe Campaign的映像之前，必須先在Adobe Target執行以下任務：

* 建立一個或多個 [重定向服務](https://experienceleague.adobe.com/docs/target/using/experiences/offers/offer-redirect.html)，您必須在其中指定要使用的影像的URL。
* 建立一個或多個 [觀眾](https://experienceleague.adobe.com/docs/target/using/audiences/create-audiences/audiences.html)，以定義活動的目標。
* 建立 [基於表單的體驗作曲家](https://experienceleague.adobe.com/docs/target/using/experiences/form-experience-composer.html) 活動，您必須在其中選擇一個rawbox並指定多個體驗，具體取決於建立的重定向服務的數量。 對於每種體驗，必須選擇建立的重定向服務之一。
* 使用Adobe Campaign的資訊建立段以指定經驗。 要在要約的選擇規則中使用來自Adobe Campaign的資料，必須在Adobe Target的「原始」框中指定資料。

1. 建立電子郵件傳遞.
1. 編輯電子郵件或登錄頁的內容時，轉到影像塊，然後選擇 **[!UICONTROL Dynamic image from Adobe Target]** 按鈕。

   ![](assets/tar_insert_dynamic_image.png)

1. 選擇預設情況下在電子郵件中顯示的影像。 可以直接指定影像URL或選擇通過 [資產](../../integrating/using/working-with-campaign-and-assets-core-service.md)。

   整合僅支援靜態映像。 其餘內容不可定製。

1. 輸入在Adobe Target中指定的Rawbox的名稱。
1. 如果在Adobe Target的設定中使用企業權限，請在此欄位中添加相應的屬性。 瞭解有關中目標企業權限的詳細資訊 [此頁](https://experienceleague.adobe.com/docs/target/using/administer/manage-users/enterprise/properties-overview.html)。 此欄位為可選欄位，如果您未在目標中使用企業權限，則不需要此欄位。
1. 在 **[!UICONTROL Additional decision parameters]**，指定在Adobe Target段中定義的欄位和Adobe Campaign欄位之間的映射。

   使用的Adobe Campaign欄位必須已在原框中指定。 在本例中，根據受助者的性別定義不同的經驗。

   ![](assets/tar_additional_decisionning_parameters.png)

1. 預覽電子郵件，查看在選擇不同的配置檔案時，影像插入的更改是否取決於在Adobe Target活動和Adobe Campaign中指定的參數。

現在可以發送包含動態映像的傳送。 結果可在Adobe Target找到。

**相關主題：**

* [Adobe Target門戶](https://experienceleague.adobe.com/docs/target/using/integrate/campaign-and-target.html)
* [關於電子郵件內容設計](../../designing/using/designing-content-in-adobe-campaign.md)
* [即時個性化電子郵件影像](https://helpx.adobe.com/tw/marketing-cloud/how-to/email-marketing.html) 視頻
