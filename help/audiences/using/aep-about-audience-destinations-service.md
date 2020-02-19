---
title: 關於 Audience Destinations 服務
description: 進一步瞭解觀眾目標服務。
page-status-flag: never-activated
uuid: b3996642-96ec-489e-b146-c8c2cb52aa32
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-audiences
discoiquuid: 750ecd8d-67a5-4180-bfec-2a8e3098c812
context-tags: audience,wizard;audience,overview;delivery,audience,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 77ceb5e5ca05fc3ee350d8e50fe0c957dec6ea26

---


# 關於 Audience Destinations 服務 {#about-audiences}

>[!IMPORTANT]
>
>觀眾目標服務目前為測試版，可能會經常更新，恕不另行通知。 客戶必須在Azure上代管（目前僅限北美地區測試版）才能存取這些功能。 如果您想要存取，請聯絡Adobe客戶服務。

運用 [Adobe Experience Platform](https://www.adobe.io/apis/experienceplatform/home.html) ，根據大型、複雜的資料集建立高針對性的受眾，讓您的消費者體驗更臻完美。 Adobe Experience platform整合了線上和線下來源（包括Adobe Analytics）的個人檔案、行為和多實體資料，協助您建立360度全方位的客戶視圖，讓您有效管理客戶體驗。

然後，Adobe Campaign Standard將會使用 **Audience Destinations** 服務，從Adobe Experience platform擷取多步驟和／或跨通道促銷活動計畫的描述檔集合，稱為 **Audiences**。

**觀眾** 是先建立區段來建立 **的**，這些區段實際上是一組規則，基於來自Adobe Experience Platform的客戶描述檔中幾乎任何變數（例如，描述檔、事件、多實體資料），以建立多維目標。 這些專屬檔案中參考了統一描述檔與區段服務 [的全域概念](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation.html)。

在建立區段後，您就可以將其啟動為觀眾，以便在 [Campaign Standard工作流程中進行傳送](../../automating/using/aep-targeting-audiences.md)。 此外，您也可以使用Adobe Experience platform的情境式資料，將動 [態內容](../../automating/using/aep-personalizing-campaigns.md) 個人化並新增至宣傳活動。

本節也提供操作說 [明影片](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/audience-destinations/audience-destinations-overview.html)。

這些章節中使用的詞語：

* **設定檔**:描述檔是Experience platform標準資料模型，用來定義消費者屬性。 描述檔也可以是與人員和裝置相關的事件資料和屬性的匯總。

   範例：「無名氏是一名55歲的男性。」

* **區段**:一組規則，它使用屬性和事件資料定義資料庫中配置檔案的子集。

   範例：&quot;男性>50歲&quot;

* **觀眾**:符合區段規則的描述檔集合。

   範例：資料庫中所有年齡超過50歲男性的相應描述檔清單。
