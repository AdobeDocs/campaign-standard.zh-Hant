---
solution: Campaign Standard
product: campaign
title: 關於 Audience Destinations 服務
description: 進一步瞭解觀眾目標服務。
audience: audiences
content-type: reference
topic-tags: managing-audiences
context-tags: audience,wizard;audience,overview;delivery,audience,back
translation-type: tm+mt
source-git-commit: 2a92600df01fd3c78a2b35c8034a2ce347e5c1d8
workflow-type: tm+mt
source-wordcount: '384'
ht-degree: 7%

---


# 關於 Audience Destinations 服務 {#about-audiences}

>[!IMPORTANT]
>
>觀眾目標服務目前為測試版，可能會經常更新，恕不另行通知。 客戶必須在Azure上代管（目前僅限北美地區測試版）才能存取這些功能。 如果您想要存取，請聯絡Adobe客戶服務。

運用[Adobe Experience Platform](https://docs.adobe.com/content/help/en/experience-platform/landing/home.html)建立以大型複雜資料集為基礎的高針對性受眾，讓您的消費者體驗更臻完美。 Adobe Experience Platform整合了線上和線下來源（包括Adobe Analytics）的個人檔案、行為和多實體資料，協助您建立360度全方位的客戶視圖，讓您有效管理客戶體驗。

然後，Adobe Campaign Standard將使用&#x200B;**觀眾目標**&#x200B;服務，從Adobe Experience Platform擷取描述檔集合（稱為&#x200B;**觀眾**），以用於多步驟和／或跨通道促銷活動。

**Audience** 是先建立區段來建立 **的**，這實際上是一組規則，基於來自Adobe Experience Platform的客戶描述檔中幾乎任何變數（例如，描述檔、事件、多實體資料），以建立多維度目標。這些專屬檔案中參考了即時客戶個人檔案與細分服務的全域概念：

* [即時客戶個人檔案總覽](https://docs.adobe.com/content/help/zh-Hant/experience-platform/profile/home.html)
* [區段服務概觀](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html)

在建立區段後，您就可以將其啟動為[促銷活動標準工作流程](../../automating/using/aep-targeting-audiences.md)中的對象，以進行傳送。 此外，您也可以使用Adobe Experience Platform中的內容相關資料，將[個人化](../../automating/using/aep-personalizing-campaigns.md)並新增動態內容至您的促銷活動。

![](assets/do-not-localize/how-to-video.png) 本節也提供操作說 [明影片](https://docs.adobe.com/content/help/zh-Hant/campaign-standard-learn/tutorials/profiles-and-audiences/audience-destinations/audience-destinations-overview.translate.html)。

這些章節中使用的詞語：

* **設定檔**:描述檔是Experience Platform標準資料模型，用來定義消費者屬性。描述檔也可以是與人員和裝置相關的事件資料和屬性的匯總。

   範例：「無名氏是一名55歲的男性。」

* **區段**:一組規則，它使用屬性和事件資料定義資料庫中配置檔案的子集。

   範例：&quot;男性>50歲&quot;

* **觀眾**:符合區段規則的描述檔集合。

   範例：資料庫中所有年齡超過50歲男性的相應描述檔清單。
