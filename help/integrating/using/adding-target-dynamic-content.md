---
solution: Campaign Standard
product: campaign
title: 新增 Target 動態內容
description: 了解如何在您的其中一項Adobe Campaign傳遞中新增Adobe Target動態內容。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-target
feature: 觸發因子
role: Data Architect
level: Intermediate
exl-id: 7dfbd89f-877e-4598-bfe3-d743bb31ae9e
source-git-commit: 92365fe416fced72e7ad5818da0dbed5d8f52f15
workflow-type: tm+mt
source-wordcount: '445'
ht-degree: 4%

---

# 新增 Target 動態內容{#adding-target-dynamic-content}

透過Adobe Target整合，動態影像可新增至傳遞中，以根據體驗個人化您的內容。

編輯電子郵件時，您可以插入來自Adobe Target的動態影像，該影像會隨收件者而變更。

在Adobe Campaign中存取影像之前，必須先在Adobe Target中執行下列工作：

* 建立一或多個[重新導向選件](https://experienceleague.adobe.com/docs/target/using/experiences/offers/offer-redirect.html)，您必須在其中指定要使用之影像的URL。
* 建立一或多個[對象](https://experienceleague.adobe.com/docs/target/using/audiences/create-audiences/audiences.html)，以定義活動的目標。
* 建立[表單式體驗撰寫器](https://experienceleague.adobe.com/docs/target/using/experiences/form-experience-composer.html)活動，您必須在其中選取rawbox並指定數個體驗，視建立的重新導向選件數量而定。 您必須針對每個體驗選取其中一個已建立的重新導向選件。
* 使用Adobe Campaign中的資訊建立區段以指定體驗。 若要在選件的選取規則中使用來自Adobe Campaign的資料，您必須在Adobe Target的rawbox中指定資料。

1. 建立電子郵件傳遞.
1. 編輯電子郵件或登錄頁面的內容時，前往影像區塊，然後透過內容功能表選取&#x200B;**[!UICONTROL Dynamic image from Adobe Target]**。

   ![](assets/tar_insert_dynamic_image.png)

1. 選取預設會出現在電子郵件中的影像。 您可以直接指定影像URL或選取透過[Assets](../../integrating/using/working-with-campaign-and-assets-core-service.md)共用的影像。

   整合僅支援靜態影像。 其餘內容無法自訂。

1. 輸入Adobe Target中指定之rawbox的名稱。
1. 如果您在Adobe Target的設定中使用企業權限，請在此欄位中新增對應的屬性。 在[本頁面](https://experienceleague.adobe.com/docs/target/using/administer/manage-users/enterprise/properties-overview.html)中深入了解Target企業權限。 如果您未在Target中使用企業權限，此欄位為選用欄位，非必要欄位。
1. 在&#x200B;**[!UICONTROL Additional decision parameters]**&#x200B;中，指定Adobe Target區段中定義的欄位與Adobe Campaign欄位之間的對應。

   使用的Adobe Campaign欄位必須已在rawbox中指定。 在此，我們將根據收件者的性別來定義不同的體驗。

   ![](assets/tar_additional_decisionning_parameters.png)

1. 預覽您的電子郵件，查看選取不同的設定檔時，插入的影像是否會根據Adobe Target活動和Adobe Campaign中指定的參數而變更。

您現在可以傳送包含動態影像的傳送。 結果可在Adobe Target找到。

**相關主題：**

* [Adobe Target入口網站](https://experienceleague.adobe.com/docs/target/using/integrate/campaign-and-target.html)
* [關於電子郵件內容設計](../../designing/using/designing-content-in-adobe-campaign.md)
* [在即時影片中個人化電子郵件影](https://helpx.adobe.com/tw/marketing-cloud/how-to/email-marketing.html) 像
