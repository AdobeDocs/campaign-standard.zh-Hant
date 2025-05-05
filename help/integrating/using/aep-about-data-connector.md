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
source-git-commit: 376f00576ca1d0dfb536b29dbf25d88f7c93b9a8
workflow-type: tm+mt
source-wordcount: '706'
ht-degree: 3%

---

# 關於 Adobe Experience Platform 資料連接器 {#about-aep-data-connector}

>[!IMPORTANT]
>
>Adobe Experience Platform資料聯結器現已棄用。 已棄用的功能仍可使用，但不會進一步增強或支援。 在此頁面[&#128279;](../../rn/using/deprecated-features.md)瞭解更多

Adobe Experience Platform Data Connector將XTK資料（在Campaign中擷取的資料）對應至Adobe Experience Platform上的Experience Data Model (XDM)資料，協助現有客戶在Adobe Experience Platform上提供其資料。

請注意，聯結器是&#x200B;**單向**，會將資料從Adobe Campaign Standard傳送至Adobe Experience Platform。 資料絕不會從Adobe Experience Platform傳送至Adobe Campaign Standard。

Adobe Experience Platform Data Connector是專為&#x200B;**資料工程師**&#x200B;所設計，他們瞭解Adobe Campaign Standard自訂資源，並瞭解客戶的整體資料結構描述應如何存在於Adobe Experience Platform中。

以下章節說明在Campaign Standard和Adobe Experience Platform之間執行資料對應的關鍵步驟。 首先建立XDM結構描述和資料集。

![](assets/do-not-localize/how-to-video.png) [在影片中探索此功能](#video)

>[!NOTE]
>設定Adobe Experience Platform Data Connector並將資料成功擷取到Adobe Experience Platform後，您需要啟用資料集，以便將資料包含在即時客戶個人檔案中。
>
>這可透過API或Adobe Experience Platform介面執行。 如需詳細資訊，請參閱專屬檔案：
>
>* [啟用即時客戶個人檔案的資料集](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/datasets/dataset.html)
>* [使用API設定Real-time Customer Profile和Identity Service的資料集](https://experienceleague.adobe.com/docs/experience-platform/catalog/api/getting-started.html)

## 重要概念 {#key-concepts}

* 「現成對應」僅適用於預設以Campaign Standard提供的欄位。 為了擷取所有自訂欄位和資源，每個客戶需要定義自己的對應。

* Adobe Experience Platform Data Connector將定期透過平台推送設定檔資料&#x200B;。 間隔持續時間為15分鐘。 此值可以使用[Adobe Experience Platform API](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html)修改。

* 資料工程師可以發佈、修改及暫停從Campaign到Adobe Experience Platform的對應。

* 任何目標維度都可以對應。 建議為單一目標維度中的所有欄位進行單一對應。

* 所有設定檔更新（包括頻道加入/退出）都是批次更新的一部分。

* 任何Adobe Campaign Standard或XDM結構描述變更都需要手動重新對應&#x200B;。

* 追蹤記錄檔和Broadlog資料會自動擷取至Adobe Experience Platform做為體驗事件。 此內嵌專案會即時串流至Adobe Experience Platform。

* Experience CloudID服務(ECID)是裝置識別碼，預設會與Experience Events一併傳送。

  這是指派給訪客的不重複永久性ID，可供Platform Identity Service用於識別不同Experience Cloud解決方案中的相同訪客及其資料。 如需詳細資訊，請參閱[Experience Cloud識別服務說明](https://experienceleague.adobe.com/docs/id-service/using/home.html)。

  >[!NOTE]
  >
  >請注意，如果兩個或多個設定檔共用同一部裝置，則Unified Identity服務中這兩個設定檔的ECID會相同。

## 限制 {#limitations}

* 不支援現成可用的訂閱事件傳輸。 若要傳輸訂閱事件，您可以在Adobe Experience Platform上建立對應的XDM和資料集，然後為這些資料設定自訂資料對應。

* 關於隱私權請求（存取和刪除動作），客戶需要透過[隱私權核心服務](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html#how-to-use-privacy-service-to-manage-privacy-job-requests)提出個別請求：一個適用於Campaign，一個適用於Adobe Experience Platform。 如需詳細資訊，請參閱[關於隱私權要求](https://experienceleague.adobe.com/docs/campaign-standard/using/getting-started/privacy/privacy-requests.html?lang=zh-Hant#getting-started)和[在Campaign中管理隱私權要求](https://helpx.adobe.com/tw/campaign/kb/acs-privacy.html#ManagingPrivacyRequests)。

* 對於每個XDM欄位，DULE標籤需要在Adobe Experience Platform中完成。 客戶有責任套用DULE標籤。

* 只有在Adobe Experience Platform中套用DULE標籤後，行銷動作的限制才會適用。 在此之前，所有資料都可用於所有型別的行銷動作。

* 每隔15分鐘，批次工作就會執行，並識別自最新批次以來已變更的記錄。 如果所有記錄都在相同的時間戳記上變更，則管理所有設定檔的擷取可能會出現效能瓶頸

## 教學課程影片 {#video}

這部影片會概略介紹Adobe Experience Platform Data Connector。

>[!VIDEO](https://video.tv.adobe.com/v/27304?quality=12&captions=eng)

您可在[這裡](https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/administrating/adobe-experience-platform-data-connector/understanding-the-adobe-experience-platform-data-connector.html)找到與Adobe Experience Platform Data Connector相關的其他影片。
