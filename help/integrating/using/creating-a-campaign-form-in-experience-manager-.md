---
title: '在 Experience Manager 中建立 Campaign 表單 '
description: 透過Adobe Experience Manager整合，您可以直接在AEM中建立表單，以建立和更新個人檔案或管理訂閱。
page-status-flag: never-activated
uuid: 43057f81-d47d-4b96-b150-217c289cd608
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
discoiquuid: 4a8b5807-87dd-4db4-bd67-890f0adae932
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 在 Experience Manager 中建立 Campaign 表單 {#creating-a-campaign-form-in-experience-manager}

您可以在AEM網站上建立「表單」，並將表單中的欄位對應至Adobe Campaign資料庫中的欄位。 這可讓您建立和更新描述檔，或管理服務的訂閱。

若要在您的AEM網站上建立Adobe Campaign表單：

1. 在您的AEM網站中，根據 **Adobe Campaign設定檔範本建立新頁面** 。

   ![](assets/aem_content_forms.png)

1. 在頁面屬性中，選取與 **[!UICONTROL Cloud Service]** 您的Adobe Campaign例項對應的。

   ![](assets/aem_content_forms_2.png)

1. 從元件中選擇表單 **[!UICONTROL Form Start]** 類型：

   * **Adobe Campaign:儲存設定檔**
   * **Adobe Campaign:訂閱服務**
   * **Adobe Campaign:取消訂閱服務**

1. 新增可對應至Adobe Campaign資料庫欄位的不同欄位和元件，以編輯表單的內容。
1. 測試並發佈表單，讓表單可在您的AEM網站上存取。

如需詳細資訊，請參閱[相關的文件](https://docs.adobe.com/content/help/en/experience-manager-65/authoring/aem-adobe-campaign/adobe-campaign-forms.html)，以瞭解詳情。
