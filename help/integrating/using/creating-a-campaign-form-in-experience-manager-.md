---
title: '在Experience Manager中建立促銷活動表單 '
seo-title: '在Experience Manager中建立促銷活動表單 '
description: '在Experience Manager中建立促銷活動表單 '
seo-description: 透過Adobe Experience Manager整合，您可以直接在AEM中建立表單，以建立和更新描述檔或管理訂閱。
page-status-flag: 從未啓動
uuid: 43057f81-d47 d-4b96-b150-214c289 cd608
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 整合
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
discoiquuid: 4a8b5807-87dd-4db4-bd67-890f0 adae932
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Creating a Campaign form in Experience Manager {#creating-a-campaign-form-in-experience-manager}

您可以在AEM網站上建立「表單」，並將表單中的欄位對應至Adobe Campaign資料庫中的欄位。這可讓您建立和更新描述檔，或管理服務訂閱。

若要在您的AEM網站上建立Adobe Campaign表單：

1. 在您的AEM網站中，根據** Adobe Campaign Profile**範本建立新頁面。

   ![](assets/aem_content_forms.png)

1. In the page properties, select the **[!UICONTROL Cloud Service]** corresponding to your Adobe Campaign instance.

   ![](assets/aem_content_forms_2.png)

1. Select the form type from the **[!UICONTROL Form Start]** component:

   * **Adobe Campaign：儲存描述檔**
   * **Adobe Campaign：訂閱服務**
   * **Adobe Campaign：取消訂閱服務**

1. 新增可對應至Adobe Campaign資料庫欄位的不同欄位和元件，以編輯表單內容。
1. 測試並發佈表單，以便在您的AEM網站上存取。

For more information, refer to the [detailed documentation](https://docs.adobe.com/docs/en/aem/6-2/author/personalization/adobe-campaign/adobe-campaign-forms.html).
