---
title: 關於 Audience Destinations 服務
description: 進一步瞭解Audience Destinations服務。
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
source-git-commit: 26394f3f6fd9b67996c30924c376533380e8f4d6
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 2%

---

# 關於 Audience Destinations 服務 {#about-audiences}

>[!IMPORTANT]
>
>Audience Destinations服務目前為測試版，可能會經常更新，恕不另行通知。 客戶必須在Azure上託管（目前僅北美地區適用Beta版）才能存取這些功能。 如果您想要存取許可權，請聯絡Adobe客戶服務。

善用您的消費者體驗 [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/landing/home.html) 根據大型複雜資料集建立具有高度針對性的對象。 Adobe Experience Platform整合線上和離線來源中的設定檔、行為和多實體資料，包括Adobe Analytics，以協助您建立客戶的360度檢視，讓您能夠有效地管理客戶體驗。

Adobe Campaign Standard隨後將使用 **對象目的地** 用於擷取設定檔集合的服務，稱為 **受眾**，適用於Adobe Experience Platform的多步驟及/或跨頻道行銷活動方案。

**受眾** 由首次建置所建立 **區段**，基本上是一組規則，根據客戶設定檔中的幾乎任何變數（例如設定檔、事件、多實體資料）從Adobe Experience Platform建立多維度目標。 以下專屬檔案中會提及即時客戶個人資料和細分服務的全域概念：

* [即時客戶設定檔概述](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html)
* [Segmentation Service概述](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html)

建立區段後，您就可以將其啟用為中的傳送對象 [Campaign Standard工作流程](../../integrating/using/aep-targeting-audiences.md). 此外，您也可以將Adobe Experience Platform中的內容資料用於 [個人化](../../integrating/using/aep-personalizing-campaigns.md) 並將動態內容新增至行銷活動。

![](assets/do-not-localize/how-to-video.png) 您也可以參閱操作說明影片 [本節](https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/audience-destinations/audience-destinations-overview.html).

這些區段中使用的辭彙：

* **設定檔**：設定檔是用於定義消費者屬性的Experience Platform標準資料模型。 設定檔也可以是與個人或裝置相關的事件資料和屬性的彙總。

   範例：「John Doe是55歲的男性。」

* **區段**：一組規則，使用屬性和事件資料從資料庫定義設定檔的子集。

   範例：「男性> 50歲。」

* **對象**：符合區段規則的設定檔集合。

   範例：對應至資料庫中所有大於50歲男性的設定檔清單。
