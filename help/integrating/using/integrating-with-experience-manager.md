---
title: 關於 Campaign-Experience Manager 整合
description: 通過Adobe Experience Manager整合，您可以直接在中創AEM建內容，稍後在Adobe Campaign使用。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: ff94f69b-3036-4103-a841-6b85feb0eb7e
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '631'
ht-degree: 1%

---

# 關於 Campaign-Experience Manager 整合{#integrating-with-experience-manager}

Adobe Campaign Standard和Adobe Experience Manager之間的這種整合允許您在您的Adobe Campaign電子郵件中使用在Adobe Experience Manager建立的內容。

因此，您可以充分利用Adobe Experience Manager內容編輯功能以及Adobe Campaign的交付和資料管理功能。 請注意，您無法對從Adobe Experience Manager導入的內容執行A/Btest。

Adobe Campaign Standard相容Adobe Experience Manager6.1、6.2、6.3、6.4和6.5。以下各節概述了可以執行的操作。 有關詳細資訊，請參閱專門用於 [配置](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignstandard.html) 和 [使用](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/aem-adobe-campaign/campaign.html) 融合。

>[!NOTE]
>
> Adobe Campaign Standard6.5不再提供Adobe Experience Manager模板。

## 有關如何使用市場活動 — Experience Manager整合的提示 {#tips-aem}

* **瞭解與整合一起使用的模板**

   由於電子郵件模板在Adobe Experience Manager內是可編輯的，因此在Adobe Experience Manager編輯任何模板看起來都會更容易。 但某些模板並不容易被接受。 不建議為此整合而專門針對一個客戶的個性化模板，應直接在Adobe Campaign Standard編輯。

   有關模板的詳細資訊，請參閱 [頁](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/templates/templates.html)。

* **確保在實施過程中配置了外部化程式**

   在為Adobe Campaign Standard實施Experience Manager時配置外部化程式，可以將資源路徑轉換為URL。 這允許您使影像在頁面上可見。 如果未正確配置外部化程式，則您的電子郵件將包含損壞的影像。

   要瞭解如何配置外部化器，請參閱 [頁](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/externalizer.html)。

* **組織您的電子郵件模板以避免誤用。**

   保持模板的有序性可確保適當的模板位於適當的資料夾中，並且不會因錯誤而選擇錯誤的模板。 在實施過程中，應建立路徑以將模板保存在正確的位置。

   有關模板的詳細資訊，請參閱 [頁](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/templates/templates.html#template-availability)。

* **快速開始使用現成元件。**

   Adobe Experience ManagerAdobe Campaign Standard的現成元件可幫助您在模板不複雜時快速啟動。
Experience Manager中有七個現成的元件，您可以開始使用：

   * 標題
   * 影像
   * 連結
   * Scene7影像模板
   * 目標引用
   * 文本和影像
   * 文本和個性化

* **電子郵件的HTML與Web的HTML不同**

   瞭解您不能將Web內容中使用的相同元件用於電子郵件模板這一點非常重要。 使用現成元件可確保您的元件與電子郵件相容。

* **將內容與模板斷開連結，並反複使用它們。**

   在Campaign Standard中設定電子郵件並選擇Experience Manager模板時，您只能選擇尚未連結到其他市場活動的電子郵件。 否則，如果您更改了Adobe Experience Manager某個市場活動的內容並進行更新，則可能會無意中影響其他市場活動的內容。
為避免這種情況，一旦您使用完模板，您就可以取消連結以再次使用模板。 您只需選擇模板並按一下 **[!UICONTROL Delete the link with Adobe Experience Manager content]**。

* **使用Adobe Experience Manager為Adobe Campaign Standard建立各種電子郵件。**

   通過此整合，您可以輕鬆地將一封電子郵件轉換為多個版本，並進行分段。
要瞭解如何在Adobe Experience Manager設定分段以及如何建立具有目標內容的電子郵件，請參閱此 [頁](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/aem-adobe-campaign/target-adobe-campaign.html#setting-up-segmentation-in-aem)。

* **要成功同步，Experience Manager中的段名稱必須與市場活動中的段名稱完全匹配。**
