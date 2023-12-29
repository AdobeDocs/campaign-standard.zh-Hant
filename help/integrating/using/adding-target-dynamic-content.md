---
title: 新增 Target 動態內容
description: 瞭解如何在其中一個Adobe Target傳遞中新增Adobe Campaign動態內容。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-target
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: 7dfbd89f-877e-4598-bfe3-d743bb31ae9e
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '406'
ht-degree: 3%

---

# 新增 Target 動態內容{#adding-target-dynamic-content}

透過Adobe Target整合，可將動態影像新增到傳送中，以根據體驗個人化您的內容。

編輯電子郵件時，您可以從Adobe Target插入動態影像，此影像會依收件者而變更。

在Adobe Campaign中存取影像之前，必須先在Adobe Target中執行以下工作：

* 建立一或多個 [重新導向選件](https://experienceleague.adobe.com/docs/target/using/experiences/offers/offer-redirect.html)，您必須在該處指定將使用之影像的URL。
* 建立一或多個 [對象](https://experienceleague.adobe.com/docs/target/using/audiences/create-audiences/audiences.html)，以定義活動的目標。
* 建立 [表單式體驗撰寫器](https://experienceleague.adobe.com/docs/target/using/experiences/form-experience-composer.html) 活動，您必須在其中選取rawbox並指定數個體驗，視建立的重新導向選件數量而定。 您必須針對每個體驗選取其中一個已建立的重新導向選件。
* 使用Adobe Campaign中的資訊建立區段以指定體驗。 若要在選件的選取規則中使用來自Adobe Campaign的資料，您必須在Adobe Target的rawbox中指定資料。

1. 建立電子郵件傳遞。
1. 編輯電子郵件或登入頁面的內容時，請前往影像區塊，然後選取「 」 **[!UICONTROL Dynamic image from Adobe Target]** 透過內容功能表。

   ![](assets/tar_insert_dynamic_image.png)

1. 選取預設顯示在電子郵件中的影像。 您可以直接指定影像URL，或選取透過共用的影像 [資產](../../integrating/using/working-with-campaign-and-assets-core-service.md).

   整合僅支援靜態影像。 其餘內容無法自訂。

1. 輸入Adobe Target中指定的rawbox名稱。
1. 如果您在Adobe Target的設定中使用企業許可權，請在此欄位中新增對應的屬性。 前往進一步瞭解Target企業許可權： [此頁面](https://experienceleague.adobe.com/docs/target/using/administer/manage-users/enterprise/properties-overview.html). 如果您未在Target中使用企業許可權，此欄位是選用欄位，且不是必要欄位。
1. 在 **[!UICONTROL Additional decision parameters]**，指定Adobe Target區段中所定義欄位與Adobe Campaign欄位之間的對應。

   使用的Adobe Campaign欄位必須在rawbox中指定。 在此範例中，會根據收件者的性別定義不同的體驗。

   ![](assets/tar_additional_decisionning_parameters.png)

1. 預覽您的電子郵件，檢視在選取不同設定檔時，插入的影像是否根據Adobe Target活動和Adobe Campaign中指定的引數而變更。

現在可以傳送包含動態影像的傳遞。 其結果可以在Adobe Target中找到。

**相關主題：**

* [Adobe Target入口網站](https://experienceleague.adobe.com/docs/target/using/integrate/campaign-and-target.html)
* [關於電子郵件內容設計](../../designing/using/designing-content-in-adobe-campaign.md)
* [即時個人化電子郵件影像](https://helpx.adobe.com/tw/marketing-cloud/how-to/email-marketing.html) 視訊
