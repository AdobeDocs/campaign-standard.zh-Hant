---
title: 關於 Adobe Experience Platform 資料連接器
description: 管理XDM結構描述，讓您的Campaign Standard資料可在Adobe Experience Platform上使用。
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: f4fcf256-e030-4d7b-b4b7-2448acc2ae1c
hide: true
hidefromtoc: true
source-git-commit: 26394f3f6fd9b67996c30924c376533380e8f4d6
workflow-type: tm+mt
source-wordcount: '771'
ht-degree: 4%

---

# 關於 Adobe Experience Platform 資料連接器 {#about-aep-data-connector}

>[!IMPORTANT]
>
>Adobe Experience Platform Data Connector目前為測試版，可能會經常更新，恕不另行通知。 客戶必須在Azure上託管（目前僅北美地區適用Beta版）才能存取這些功能。 如果您想要存取許可權，請聯絡Adobe客戶服務。

Adobe Experience Platform Data Connector可協助現有客戶，將XTK資料（在Campaign中擷取的資料）對應至Adobe Experience Platform上的Experience Data Model (XDM)資料，以便在Adobe Experience Platform上提供其資料。

請注意，聯結器是 **單向** 和會將資料從Adobe Campaign Standard傳送至Adobe Experience Platform。 資料絕不會從Adobe Experience Platform傳送至Adobe Campaign Standard。

Adobe Experience Platform Data Connector **資料工程師** 瞭解Adobe Campaign Standard自訂資源，以及客戶整體資料結構描述應如何存在於Adobe Experience Platform中的人員。

以下小節說明在Campaign Standard和Adobe Experience Platform之間執行資料對應的關鍵步驟。 首先建立XDM結構描述和資料集。

![](assets/do-not-localize/how-to-video.png) [在影片中探索此功能](#video)

>[!NOTE]
>設定Adobe Experience Platform Data Connector並將資料成功擷取到Adobe Experience Platform後，您需要啟用資料集，才能將資料包含在即時客戶設定檔中。
>
>您可以透過API或Adobe Experience Platform介面執行此動作。 如需詳細資訊，請參閱專屬檔案：
>
>* [啟用即時客戶個人檔案的資料集](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/datasets/dataset.html)
>* [使用API設定即時客戶個人檔案和身分服務的資料集](https://experienceleague.adobe.com/docs/experience-platform/catalog/api/getting-started.html)


## 重要概念 {#key-concepts}

* 「現成對應」僅適用於預設以Campaign Standard提供的欄位。 若要擷取所有自訂欄位和資源，每個客戶都需要定義自己的對應。

* Adobe Experience Platform Data Connector會定期將設定檔資料推送至平台&#x200B;。 間隔持續時間為15分鐘。 此值可使用以下方式修改： [ADOBE EXPERIENCE PLATFORM API](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html).

* 資料工程師可以發佈、修改和暫停從Campaign到Adobe Experience Platform的對應。

* 任何目標維度都可以對應。 建議為單一目標維度中的所有欄位建立一個單一對應。

* 所有設定檔更新（包括頻道加入/退出）都是批次更新的一部分。

* 任何Adobe Campaign Standard或XDM結構描述變更都需要手動重新對應&#x200B;。

* 追蹤記錄檔和Broadlog資料會自動擷取至Adobe Experience Platform做為體驗事件。 此內嵌會即時串流至Adobe Experience Platform。

* Experience CloudID服務(ECID)是裝置識別碼，預設會隨Experience Events傳送。

   這是指派給訪客的不重複永久性ID，可供Platform Identity服務用來識別不同Experience Cloud解決方案中的相同訪客及其資料。 如需詳細資訊，請參閱 [Experience Cloud身分識別服務說明](https://experienceleague.adobe.com/docs/id-service/using/home.html).

   >[!NOTE]
   >
   >請注意，如果兩個或多個設定檔共用同一部裝置，則Unified Identity服務中這兩個設定檔的ECID會相同。

## 限制 {#limitations}

* 不支援立即可用的訂閱事件傳輸。 若要轉移訂閱事件，您可以在Adobe Experience Platform上建立對應的XDM和資料集，然後為這些資料設定自訂資料對應。

* 關於隱私權請求（存取和刪除動作），客戶需要透過 [隱私權核心服務](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html#how-to-use-privacy-service-to-manage-privacy-job-requests)：一個用於Campaign，一個用於Adobe Experience Platform。 如需詳細資訊，請參閱 [關於隱私權請求](https://experienceleague.adobe.com/docs/campaign-standard/using/getting-started/privacy/privacy-requests.html?lang=zh-Hant#getting-started) 和 [管理隱私權請求](https://helpx.adobe.com/tw/campaign/kb/acs-privacy.html#ManagingPrivacyRequests) （在Campaign）。

* 對於每個XDM欄位，DULE標籤必須在Adobe Experience Platform中完成。 客戶有責任套用DULE標籤。

* 只有在Adobe Experience Platform中套用DULE標籤後，行銷動作的限制才會適用。 在此之前，所有資料都可用於所有型別的行銷動作。

* 每隔15分鐘，批次工作就會執行，並識別自最新批次以來已變更的記錄。 如果所有記錄都在相同的時間戳記上變更，則管理所有設定檔的擷取可能會出現效能瓶頸

## 教學課程影片 {#video}

這部影片會概略介紹Adobe Experience Platform Data Connector。

>[!VIDEO](https://video.tv.adobe.com/v/27304?quality=12&captions=eng)

提供與Adobe Experience Platform Data Connector相關的其他影片 [此處](https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/administrating/adobe-experience-platform-data-connector/understanding-the-adobe-experience-platform-data-connector.html).
