---
solution: Campaign Standard
product: campaign
title: 關於 Campaign-Experience Manager 整合
description: 透過Adobe Experience Manager整合，您可以直接在AEM中建立內容，並稍後在Adobe Campaign中使用。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: 觸發因子
role: Data Architect
level: Intermediate
exl-id: ff94f69b-3036-4103-a841-6b85feb0eb7e
source-git-commit: f6e94cf98662e708730be672149d836ef0e56522
workflow-type: tm+mt
source-wordcount: '632'
ht-degree: 1%

---

# 關於 Campaign-Experience Manager 整合{#integrating-with-experience-manager}

Adobe Campaign Standard與Adobe Experience Manager的這項整合可讓您在Adobe Campaign電子郵件中使用Adobe Experience Manager中建立的內容。

因此，您可以充分運用Adobe Experience Manager內容編輯功能，以及Adobe Campaign的傳遞和資料管理功能。 請注意，您無法對從Adobe Experience Manager匯入的內容執行A/B測試。

Adobe Campaign Standard與Adobe Experience Manager 6.1、6.2、6.3、6.4和6.5相容。以下幾節概述您可執行的動作。 如需詳細資訊，請參閱整合的[configuration](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignstandard.html)和[use](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/aem-adobe-campaign/campaign.html)專屬區段。

>[!NOTE]
>
> Adobe Experience Manager 6.5不再提供Adobe Campaign Standard範本。

## 如何使用Campaign-Experience Manager整合的提示{#tips-aem}

* **了解要與整合搭配使用的範本**

   由於電子郵件範本可在Adobe Experience Manager中編輯，因此在Adobe Experience Manager中編輯任何範本看起來可能會更輕鬆。 但是，某些模板並不容易被容納。 此整合不建議針對單一客戶個別編輯範本，應直接在Adobe Campaign Standard中編輯。

   如需範本的詳細資訊，請參閱此[page](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/templates/templates.html)。

* **確認實施期間已設定Externalizer**

   為Adobe Campaign Standard實作Experience Manager時設定Externalizer ，可將資源路徑轉換為URL。 這可讓您讓影像顯示在頁面上。 如果Externalizer未正確設定，則您的電子郵件將包含損毀的影像。

   要了解如何配置Externalizer，請參閱此[page](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/externalizer.html)。

* **組織您的電子郵件範本，以避免誤用。**

   讓範本保持組織，可確保適當的範本位於適當的資料夾中，並避免錯誤選擇錯誤的範本。 實作期間，應建立路徑以將範本儲存在正確的位置。

   如需範本的詳細資訊，請參閱此[page](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/templates/templates.html#template-availability)。

* **快速開始使用現成可用的元件。**

   Adobe Experience Manager for Adobe Campaign Standard中的現成可用元件可協助您在範本不複雜時快速上手。
Experience Manager中有七個現成可用的元件，您可以開始使用：

   * 標題
   * 影像
   * 連結
   * Scene7影像範本
   * 目標參考
   * 文字與影像
   * 文字與個人化

* **電子郵件的HTML與網頁的HTML不同**

   請務必了解，您無法將網頁內容中使用的相同元件用於電子郵件範本。 使用現成可用的元件可確保您的元件與電子郵件相容。

* **將內容與範本取消連結，然後反複使用。**

   在「Campaign Standard」中設定電子郵件並選取Experience Manager範本時，您只能選擇尚未連結至其他促銷活動的電子郵件。 否則，如果您變更Adobe Experience Manager中某個促銷活動的內容並重新整理，可能會無意中影響另一個促銷活動的內容。
若要避免此問題，一旦您使用完範本，就可以取消連結以再次使用。 您只需選取範本，然後按一下**[!UICONTROL Delete the link with Adobe Experience Manager content]**&#x200B;即可。

* **使用Adobe Experience Manager建立Adobe Campaign Standard的電子郵件變數。**

   此整合可讓您透過細分輕鬆將一封電子郵件轉換為數個版本。
若要了解如何在Adobe Experience Manager中設定區段以及如何建立具有目標內容的電子郵件，請參閱此[page](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/aem-adobe-campaign/target-adobe-campaign.html#setting-up-segmentation-in-aem)。

* **若要成功同步，Experience Manager中的區段名稱必須與促銷活動中的區段名稱完全相符。**
