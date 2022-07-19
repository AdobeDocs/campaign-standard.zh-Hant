---
title: 關於 Audience Destinations 服務
description: 瞭解有關「受眾目標」服務的詳細資訊。
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
>受眾目標服務當前處於測試版，可能需要頻繁更新，恕不另行通知。 客戶需要在Azure上托管（目前僅在北美試用版）才能訪問這些功能。 如果您想訪問，請聯繫Adobe客戶服務。

通過利用 [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/landing/home.html) 構建基於大型、複雜資料集的高度針對性受眾。 Adobe Experience Platform整合了包括Adobe Analytics在內的線上和離線來源中的配置檔案、行為和多實體資料，以幫助您構建客戶的360度視圖，使您能夠有效管理客戶體驗。

Adobe Campaign Standard會利用 **受眾目標** 用於檢索配置檔案集合的服務，稱為 **觀眾**&#x200B;來自Adobe Experience Platform的跨步驟和/或跨渠道活動計畫。

**觀眾** 由第一個建築建立 **段**，它實質上是一組基於客戶配置檔案中來自Adobe Experience Platform的幾乎任何變數（例如，配置檔案、事件、多實體資料）的規則，以建立多維目標。 以下專用文檔參考了即時客戶配置檔案和細分服務的全球概念：

* [即時客戶概要資訊概述](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html)
* [分段服務概述](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html)

建立段後，您可以將其作為受眾激活，以便在 [Campaign Standard工作流](../../integrating/using/aep-targeting-audiences.md)。 此外，您還可以使用從Adobe Experience Platform到 [個性化](../../integrating/using/aep-personalizing-campaigns.md) 並將動態內容添加到您的市場活動中。

![](assets/do-not-localize/how-to-video.png) How-to視頻也可在 [此部分](https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/audience-destinations/audience-destinations-overview.html)。

以下各節使用的術語：

* **配置檔案**:配置檔案是用於定義使用者屬性的Experience Platform標準資料模型。 配置檔案也可以是與個人和設備相關的事件資料和屬性的集合。

   示例：「無名氏是55歲的男性。」

* **段**:一組規則，它使用屬性和事件資料從資料庫中定義配置檔案的子集。

   示例：&quot;男性50歲以上&quot;

* **觀眾**:滿足段規則的配置檔案的集合。

   示例：資料庫中與所有50歲以上男性對應的配置檔案清單。
