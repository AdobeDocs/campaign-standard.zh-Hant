---
title: 關於 Campaign-Experience Manager 整合
description: 透過Adobe Experience Manager整合，您可以直接在AEM中建立內容，並稍後在Adobe Campaign中使用。
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 37e86c6143c52841e69d610fa9db35dff70a3587

---


# 關於 Campaign-Experience Manager 整合{#integrating-with-experience-manager}

Adobe Campaign Standard與Adobe Experience Manager的整合可讓您在Adobe Campaign電子郵件中使用在Adobe Experience Manager中建立的內容。

因此，您可以充份運用Adobe Experience Manager內容編輯功能以及Adobe Campaign的傳送和資料管理功能。 請注意，您無法對從Adobe Experience Manager匯入的內容執行A/B測試。

Adobe Campaign Standard與Adobe Experience Manager 6.1、6.2、6.3、6.4和6.5相容。以下各節概述了您可以執行的操作。 如需詳細資訊，請參閱專用於 [設定](https://docs.adobe.com/content/help/en/experience-manager-65/administering/integration/campaignstandard.html)[與整合使用](https://docs.adobe.com/content/help/en/experience-manager-65/authoring/aem-adobe-campaign/campaign.html) 的章節。

>[!NOTE]
>
> Adobe Experience Manager 6.5不再提供Adobe Campaign Standard範本。

## 如何使用Campaign-Experience Manager整合的秘訣 {#tips-aem}

* **瞭解要與整合搭配使用的範本**

   由於電子郵件範本可在Adobe Experience Manager中編輯，因此在Adobe Experience Manager中編輯任何範本看起來都會更輕鬆。 但某些範本並不容易調整。 此整合不建議針對一位客戶的個人化範本，而應直接在Adobe Campaign Standard中編輯。

   有關模板的詳細資訊，請參閱本 [頁](https://docs.adobe.com/content/help/en/experience-manager-65/developing/platform/templates/templates.html)。

* **請確定在實作期間已設定Externalizer**

   在實作Adobe Campaign Standard的Experience Manager時設定Externalizer，可將資源路徑轉換為URL。 這可讓您在頁面上顯示影像。 如果Externalizer未正確設定，您的電子郵件將包含中斷的影像。

   要瞭解如何配置Externalizer，請參閱本 [頁](https://docs.adobe.com/content/help/en/experience-manager-65/developing/platform/externalizer.html)。

* **組織您的電子郵件範本，以避免誤用。**

   讓範本保持條理，可確保適當的範本位於適當的檔案夾中，而不會誤選錯誤的範本。 在實作期間，應建立路徑以將範本儲存在正確的位置。

   有關模板的詳細資訊，請參閱本 [頁](https://docs.adobe.com/content/help/en/experience-manager-65/developing/platform/templates/templates.html#template-availability)。

* **立即開始使用現成可用的元件。**

   Adobe Experience Manager for Adobe Campaign Standard中的現成可用元件可協助您在範本不複雜時快速上手。
Experience Manager中有7種現成可用的元件，您可以開始使用：

   * 標題
   * 影像
   * 連結
   * Scene7影像範本
   * 定位參考
   * 文字與影像
   * 文字與個人化

* **電子郵件的HTML與網頁的HTML不同**

   請務必瞭解，您無法針對電子郵件範本使用網頁內容中使用的相同元件。 使用現成可用的元件可確保您的元件與電子郵件相容。

* **將內容與範本取消連結，然後一次又一次地重複使用。**

   在「促銷活動標準」中設定電子郵件並選取Experience Manager範本時，您只能選擇尚未連結至其他促銷活動的範本。 否則，如果您變更Adobe Experience Manager中某個促銷活動的內容並重新整理，可能會無意中影響另一個促銷活動的內容。
為避免此問題，當您使用完範本後，可以將範本取消連結以再次使用。 您只需選取範本並按一下即可 **[!UICONTROL Delete the link with Adobe Experience Manager content]**。

* **使用Adobe Experience Manager為Adobe Campaign Standard建立各種電子郵件。**

   此項整合可讓您輕鬆將一封電子郵件轉換成多個版本，並進行分段。
如要瞭解如何在Adobe Experience Manager中設定區段，以及如何建立包含目標內容的電子郵件，請參閱本 [頁](https://docs.adobe.com/help/en/experience-manager-65/authoring/aem-adobe-campaign/target-adobe-campaign.html#setting-up-segmentation-in-aem)。

* **若要成功同步，Experience Manager中的區段名稱必須完全符合促銷活動中的區段名稱。**