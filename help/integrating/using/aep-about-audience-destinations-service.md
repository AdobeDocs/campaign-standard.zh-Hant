---
title: 關於 Audience Destinations 服務
description: 深入瞭解Audience Destinations服務。
audience: audiences
content-type: reference
topic-tags: managing-audiences
context-tags: audience,wizard;audience,overview;delivery,audience,back
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: 34235749-d056-4d4c-9939-7dc52f980a76
hide: true
hidefromtoc: true
source-git-commit: 376f00576ca1d0dfb536b29dbf25d88f7c93b9a8
workflow-type: tm+mt
source-wordcount: '335'
ht-degree: 2%

---

# 關於 Audience Destinations 服務 {#about-audiences}

>[!IMPORTANT]
>
>Audience Destinations服務現已棄用。 已棄用的功能仍可使用，但不會進一步增強或支援。 在此頁面[&#128279;](../../rn/using/deprecated-features.md)瞭解更多

運用[Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/landing/home.html?lang=zh-Hant)，根據大型複雜資料集建立具有高度針對性的受眾，強化您的消費者體驗。 Adobe Experience Platform整合線上和離線來源中的設定檔、行為和多實體資料，包括Adobe Analytics，協助您建立客戶的360度檢視，讓您能夠有效地管理客戶體驗。

然後Adobe Campaign Standard將使用&#x200B;**對象目標**&#x200B;服務從Adobe Experience Platform中擷取一組設定檔（稱為&#x200B;**對象**），以用於多步驟和/或跨頻道行銷活動方案。

**對象**&#x200B;是透過先建置&#x200B;**區段**&#x200B;所建立，這些區段基本上是一組規則，根據的是Adobe Experience Platform中客戶設定檔內的幾乎任何變數（例如，設定檔、事件、多實體資料），以建立多維度目標。 即時客戶個人資料和細分服務的全球概念可在以下專用檔案中參照：

* [即時客戶個人檔案總覽](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=zh-Hant)
* [分段服務總覽](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=zh-Hant)

建立區段後，您就可以將其啟用為[Campaign Standard工作流程](../../integrating/using/aep-targeting-audiences.md)中傳遞的對象。 此外，您也可以使用來自Adobe Experience Platform的內容相關資料來[個人化](../../integrating/using/aep-personalizing-campaigns.md)，並將動態內容新增至行銷活動。

![](assets/do-not-localize/how-to-video.png)在[本節](https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/audience-destinations/audience-destinations-overview.html?lang=zh-Hant)中也有操作說明影片。

這些小節中使用的辭彙：

* **設定檔**：設定檔是用於定義消費者屬性的Experience Platform標準資料模型。 設定檔也可以是與個人或裝置相關的事件資料和屬性的彙總。

  範例：「John Doe是55歲的男性。」

* **區段**：定義資料庫中設定檔子集的一組規則，使用屬性和事件資料。

  範例：「男性> 50歲。」

* **對象**：符合區段規則的設定檔集合。

  範例：與資料庫中年齡超過50歲的所有男性對應的設定檔清單。
