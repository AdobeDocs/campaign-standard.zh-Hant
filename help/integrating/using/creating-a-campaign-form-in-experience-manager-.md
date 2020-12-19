---
solution: Campaign Standard
product: campaign
title: '在 Experience Manager 中建立 Campaign 表單 '
description: 透過Adobe Experience Manager整合，您可以直接在AEM中建立表單，以建立和更新個人檔案或管理訂閱。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 12%

---


# 在 Experience Manager 中建立 Campaign 表單 {#creating-a-campaign-form-in-experience-manager}

您可以在AEM網站上建立「表單」，並將表單中的欄位對應至Adobe Campaign資料庫中的欄位。 這可讓您建立和更新描述檔，或管理服務的訂閱。

若要在您的AEM網站上建立Adobe Campaign表單：

1. 在您的AEM網站中，根據&#x200B;**Adobe Campaign Profile**&#x200B;範本建立新頁面。

   ![](assets/aem_content_forms.png)

1. 在頁面屬性中，選取與您的Adobe Campaign例項對應的&#x200B;**[!UICONTROL Cloud Service]**。

   ![](assets/aem_content_forms_2.png)

1. 從&#x200B;**[!UICONTROL Form Start]**&#x200B;元件中選擇表單類型：

   * **Adobe Campaign:儲存設定檔**
   * **Adobe Campaign:訂閱服務**
   * **Adobe Campaign:取消訂閱服務**

1. 新增可對應至Adobe Campaign資料庫欄位的不同欄位和元件，以編輯表單的內容。
1. 測試並發佈表單，讓表單可在您的AEM網站上存取。

如需詳細資訊，請參閱[相關的文件](https://docs.adobe.com/content/help/en/experience-manager-65/authoring/aem-adobe-campaign/adobe-campaign-forms.html)，以瞭解詳情。
