---
solution: Campaign Standard
product: campaign
title: 關於 Adobe Experience Platform Data Connector
description: 管理XDM結構，讓您的Campaign Standard資料可在Adobe Experience Platform上使用。
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Microsoft CRM整合
role: Data Architect
level: Experienced
exl-id: f4fcf256-e030-4d7b-b4b7-2448acc2ae1c
source-git-commit: 92365fe416fced72e7ad5818da0dbed5d8f52f15
workflow-type: tm+mt
source-wordcount: '774'
ht-degree: 4%

---

# 關於 Adobe Experience Platform Data Connector {#about-aep-data-connector}

>[!IMPORTANT]
>
>Adobe Experience Platform Data Connector目前為測試版，可能會經常更新，恕不另行通知。 客戶必須在Azure上托管（目前測試版僅供北美使用），才能存取這些功能。 如果您想要存取權限，請聯絡Adobe客戶服務。

Adobe Experience Platform Data Connector可將XTK資料（在Campaign中擷取的資料）對應至Adobe Experience Platform上的Experience Data Model(XDM)資料，以協助現有客戶將其資料在Adobe Experience Platform上可用。

請注意，連接器為&#x200B;**單向**，並將資料從Adobe Campaign Standard傳送至Adobe Experience Platform。 資料從不會從Adobe Experience Platform傳送至Adobe Campaign Standard。

Adobe Experience Platform Data Connector適用於了解Adobe Campaign Standard自訂資源且了解客戶整體資料結構應如何位於Adobe Experience Platform內的資料工程師&#x200B;**。**

以下各節將說明在Campaign Standard與Adobe Experience Platform之間執行資料對應的關鍵步驟。 這會從建立XDM結構和資料集開始。

![](assets/do-not-localize/how-to-video.png) [在影片中探索此功能](#video)

>[!NOTE]
>設定Adobe Experience Platform Data Connector並成功將資料擷取至Adobe Experience Platform後，您必須啟用資料集，將資料納入即時客戶個人檔案中。
>
>這可透過API或Adobe Experience Platform介面執行。 如需詳細資訊，請參閱專屬檔案：
>
>* [為「即時客戶個人檔案」啟用資料集](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/datasets/dataset.html)
>* [使用API為即時客戶個人檔案和身分服務設定資料集](https://experienceleague.adobe.com/docs/experience-platform/catalog/api/getting-started.html)


## 重要概念{#key-concepts}

* 「現成可用對應」僅適用於預設以Campaign Standard提供的欄位。 若要擷取所有自訂欄位和資源，每個客戶都需要定義自己的對應。

* Adobe Experience Platform Data Connector會定期在平台中推送設定檔資料&#x200B;。 時間間隔為15分鐘。 此值可使用[Adobe Experience Platform API](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html)來修改。

* 資料工程師可以發佈、修改及暫停從Campaign到Adobe Experience Platform的對應。

* 任何目標維度皆可對應。 建議在單一目標維度中的所有欄位有一個單一對應。

* 所有設定檔更新（包括通道選擇加入/選擇退出）都是批次更新的一部分。

* 任何Adobe Campaign Standard或XDM架構變更都需手動重新對應&#x200B;。

* 追蹤記錄和Broadlog資料會自動以Experience Events的形式擷取至Adobe Experience Platform。 此擷取會即時串流至Adobe Experience Platform。

* Experience CloudID服務(ECID)是裝置識別碼，預設會與體驗事件一併傳送。

   這是指派給訪客的不重複且永續的ID，可由Platform Identity Service用來識別不同Experience Cloud解決方案中的相同訪客及其資料。 有關詳細資訊，請參閱[Experience Cloud身份服務幫助](https://experienceleague.adobe.com/docs/id-service/using/home.html)。

   >[!NOTE]
   >
   >請注意，如果兩個或多個設定檔共用同一部裝置，統一身分服務中這兩個設定檔的ECID將相同。

## 限制 {#limitations}

* 不支援立即可用的訂閱事件傳輸。 若要傳輸訂閱事件，您可以在Adobe Experience Platform上建立對應的XDM和資料集，然後為這些資料設定自訂資料對應。

* 針對隱私權要求（存取和刪除動作），客戶需透過[隱私權核心服務](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html#how-to-use-privacy-service-to-manage-privacy-job-requests)提出個別要求：一個用於Campaign，一個用於Adobe Experience Platform。 如需詳細資訊，請參閱Campaign中的[關於隱私權要求](https://experienceleague.adobe.com/docs/campaign-standard/using/getting-started/privacy/privacy-requests.html?lang=zh-Hant#getting-started)及[管理隱私權要求](https://helpx.adobe.com/tw/campaign/kb/acs-privacy.html#ManagingPrivacyRequests)。

* 對於每個XDM欄位，DULE標籤必須在Adobe Experience Platform中完成。 這是客戶套用DULE標籤的責任。

* 行銷動作限制僅在DULE標籤套用至Adobe Experience Platform後才適用。 在此之前，所有資料都可用於所有類型的行銷動作。

* 每15分鐘，批處理作業就會運行一次，它將標識自最新批處理後更改的記錄。 如果所有記錄在相同時間戳記下變更，則可能會出現效能瓶頸以管理所有設定檔的擷取

## 教學課程影片 {#video}

本影片提供Adobe Experience Platform Data Connector的概觀。

>[!VIDEO](https://video.tv.adobe.com/v/27304?quality=12&captions=eng)

[此處](https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/administrating/adobe-experience-platform-data-connector/understanding-the-adobe-experience-platform-data-connector.html)提供與Adobe Experience Platform Data Connector相關的其他影片。
