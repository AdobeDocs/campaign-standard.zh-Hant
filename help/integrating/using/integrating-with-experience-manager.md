---
title: 關於 Campaign-Experience Manager 整合
description: 透過Adobe Experience Manager整合，您可以直接在AEM中建立內容，並稍後在Adobe Campaign中使用。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: Triggers
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: ff94f69b-3036-4103-a841-6b85feb0eb7e
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '597'
ht-degree: 1%

---

# 關於 Campaign-Experience Manager 整合{#integrating-with-experience-manager}

Adobe Campaign Standard與Adobe Experience Manager之間的這項整合可讓您在Adobe Campaign電子郵件中使用Adobe Experience Manager中建立的內容。

因此，您可以充分利用Adobe Experience Manager內容編輯功能，以及Adobe Campaign的交付和資料管理功能。 請注意，您無法對從Adobe Experience Manager匯入的內容執行A/B測試。

Adobe Campaign Standard與Adobe Experience Manager 6.1、6.2、6.3、6.4和6.5相容。以下小節提供您可以執行的動作概觀。 如需詳細資訊，請參閱專屬於[組態](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignstandard.html)和整合的[使用](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/aem-adobe-campaign/campaign.html)的章節。

>[!NOTE]
>
> Adobe Experience Manager 6.5不再提供Adobe Campaign Standard範本。

## 如何使用Campaign-Experience Manager整合的提示 {#tips-aem}

* **瞭解要與整合搭配使用的範本**

  由於電子郵件範本可在Adobe Experience Manager內編輯，因此在Adobe Experience Manager中編輯任何範本似乎較為容易。 但某些範本並不容易調整。 不建議對此整合使用專屬於單一客戶的個人化範本，而應直接在Adobe Campaign Standard中編輯。

  如需範本的詳細資訊，請參閱此[頁面](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/templates/templates.html)。

* **確定已在實作期間設定Externalizer**

  在實作Experience Manager for Adobe Campaign Standard時設定Externalizer可將資源路徑轉換為URL。 這可讓您在頁面上顯示影像。 如果未正確設定Externalizer，您的電子郵件將會包含損毀的影像。

  若要瞭解如何設定外部化程式，請參閱此[頁面](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/externalizer.html)。

* **組織您的電子郵件範本以避免誤用。**

  讓範本保持井然有序，可確保適當的範本位於適當的資料夾中，並且不會錯誤地選擇錯誤的範本。 實施期間應建立路徑，以將範本儲存在正確位置。

  如需範本的詳細資訊，請參閱此[頁面](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/templates/templates.html#template-availability)。

* **使用現成可用的元件快速入門。**

  如果範本不複雜，適用於Adobe Campaign Standard的Adobe Experience Manager中的現成元件可協助您快速入門。
Experience Manager中有7個現成可用的元件，您可以開始使用：

   * 標題
   * 影像
   * 連結
   * Scene7影像範本
   * 目標引用
   * 文字與影像
   * 文字和Personalization

* 電子郵件的&#x200B;**HTML與網頁的HTML不同**

  請務必瞭解，您無法將網頁內容中使用的相同元件用於電子郵件範本。 使用現成可用的元件可確保您的元件能與電子郵件相容。

* **取消內容與範本的連結，並一再重複使用。**

  在Campaign Standard中設定電子郵件並選取Experience Manager範本時，您只能選擇尚未連結至其他行銷活動的範本。 否則，如果您在Adobe Experience Manager中變更某個促銷活動的內容並重新整理，可能會無意中影響另一個促銷活動的內容。
為避免此問題，當您完成使用範本後，可以取消連結以再次使用。 您只需要選取範本並按一下**[!UICONTROL Delete the link with Adobe Experience Manager content]**。

* **使用Adobe Experience Manager為Adobe Campaign Standard建立各種不同的電子郵件。**

  此整合可讓您透過分段輕鬆地將一封電子郵件轉換為多個版本。
若要瞭解如何在Adobe Experience Manager中設定細分，以及如何建立包含目標內容的電子郵件，請參閱此[頁面](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/aem-adobe-campaign/target-adobe-campaign.html#setting-up-segmentation-in-aem)。

* **若要成功同步，Experience Manager中的區段名稱必須與Campaign中的區段名稱完全相符。**
