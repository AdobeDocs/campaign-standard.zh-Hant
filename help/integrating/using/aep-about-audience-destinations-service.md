---
title: 關於 Audience Destinations 服務
description: 進一步了解Audience Destinations服務。
audience: audiences
content-type: reference
topic-tags: managing-audiences
context-tags: audience,wizard;audience,overview;delivery,audience,back
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: 34235749-d056-4d4c-9939-7dc52f980a76
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 2%

---

# 關於 Audience Destinations 服務 {#about-audiences}

>[!IMPORTANT]
>
>Audience Destinations服務目前為測試版，可能會經常更新，恕不另行通知。 客戶必須在Azure上托管（目前測試版僅供北美使用），才能存取這些功能。 如果您想要存取權限，請聯絡Adobe客戶服務。

運用 [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/landing/home.html) 根據大型複雜資料集建立目標明確的對象。 Adobe Experience Platform整合了線上和離線來源(包括Adobe Analytics)的設定檔、行為和多實體資料，可協助您建立客戶的360度檢視，讓您有效管理客戶體驗。

Adobe Campaign Standard將使用 **對象目標** 擷取設定檔集合的服務，稱為 **對象**，來自Adobe Experience Platform以執行多步驟和/或跨通道行銷活動方案。

**對象** 由第一棟建築建立 **區段**，這基本上是一組規則，其基礎是Adobe Experience Platform客戶設定檔中幾乎任何變數（例如，設定檔、事件、多實體資料），以建立多維度目標。 以下專屬檔案會參考即時客戶個人檔案和區段服務的全域概念：

* [即時客戶個人檔案概觀](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html)
* [區段服務概觀](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html)

建立區段後，您就可以在 [Campaign Standard工作流程](../../integrating/using/aep-targeting-audiences.md). 此外，您也可以使用來自Adobe Experience Platform的內容資料來 [個人化](../../integrating/using/aep-personalizing-campaigns.md) 和新增動態內容至促銷活動。

![](assets/do-not-localize/how-to-video.png) 操作說明影片也可在 [本節](https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/audience-destinations/audience-destinations-overview.html).

這些小節中使用的詞語：

* **設定檔**:設定檔是Experience Platform標準資料模型，用來定義使用者的屬性。 設定檔也可以是與人員和裝置相關的事件資料和屬性的匯總。

   範例：「無名氏是55歲的男性。」

* **區段**:一組規則，可定義資料庫中的設定檔子集，使用屬性和事件資料。

   範例：「男性> 50歲。」

* **對象**:符合區段規則的設定檔集合。

   範例：資料庫中與50歲以上男性對應的設定檔清單。
