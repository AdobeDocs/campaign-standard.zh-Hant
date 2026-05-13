---
title: 在 Experience Manager 中建立 Campaign 表單
description: 透過Adobe Experience Manager整合，您可以直接在AEM中建立表單，以建立和更新設定檔或管理訂閱。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: Triggers
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 61683639-3f71-4652-a138-acfc0e91e868
TQID: https://experienceleague.adobe.com/5wklRtwZ6Wubvyo-yu2ogEHufoqYBh6cvaJEoBC-Lkk
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 187
ht-degree: 11%

---

# 在 Experience Manager 中建立 Campaign 表單 {#creating-a-campaign-form-in-experience-manager}

您可以在您的AEM網站上建立「表單」，並將表單中的欄位對應至Adobe Campaign資料庫中的欄位。 這可讓您建立和更新設定檔，或管理服務的訂閱。

若要在您的AEM網站上建立Adobe Campaign表單：

1. 在您的AEM網站中，根據&#x200B;**Adobe Campaign設定檔**&#x200B;範本建立新頁面。

   ![](assets/aem_content_forms.png)

1. 在頁面屬性中，選取與您的Adobe Campaign執行個體相對應的&#x200B;**[!UICONTROL Cloud Service]**。

   ![](assets/aem_content_forms_2.png)

1. 從&#x200B;**[!UICONTROL Form Start]**&#x200B;元件中選取表單型別：

   * **Adobe Campaign：儲存設定檔**
   * **Adobe Campaign：訂閱服務**
   * **Adobe Campaign：取消訂閱服務**

1. 新增可對應至Adobe Campaign資料庫欄位的不同欄位和元件，以編輯表單內容。
1. 測試並發佈表單，使其可在您的AEM網站上存取。

如需詳細資訊，請參閱[詳細文件](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/aem-adobe-campaign/adobe-campaign-forms.html?lang=zh-Hant)以瞭解詳情。
