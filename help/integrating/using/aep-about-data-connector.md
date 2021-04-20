---
solution: Campaign Standard
product: campaign
title: 關於 Adobe Experience Platform Data Connector
description: 管理XDM結構，使您的Campaign Standard資料在Adobe Experience Platform可用。
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '789'
ht-degree: 5%

---


# 關於 Adobe Experience Platform Data Connector {#about-aep-data-connector}

>[!IMPORTANT]
>
>Adobe Experience Platform資料連接器目前正在測試中，可能會在不另行通知的情況下頻繁更新。 客戶必須在Azure上代管（目前僅限北美地區測試版）才能存取這些功能。 如果您想要存取，請聯絡Adobe客戶服務。

Adobe Experience Platform資料連接器將XTK資料（收錄於促銷活動的資料）對應至Adobe Experience Platform的體驗資料模型(XDM)資料，協助現有客戶在Adobe Experience Platform提供其資料。

請注意，連接器為&#x200B;**單向**，並將資料從Adobe Campaign Standard發送到Adobe Experience Platform。 這些資料從未從Adobe Experience Platform發送到Adobe Campaign Standard。

Adobe Experience Platform資料連接器適用於&#x200B;**瞭解Adobe Campaign Standard自訂資源並瞭解客戶整體資料架構在Adobe Experience Platform內部的**&#x200B;資料工程師。

以下各節介紹在Campaign Standard和Adobe Experience Platform之間執行資料映射的關鍵步驟。 這從建立XDM架構和資料集開始。

![](assets/do-not-localize/how-to-video.png) [在影片中探索此功能](#video)

>[!NOTE]
>一旦配置了Adobe Experience Platform資料連接器並成功將資料接收到Adobe Experience Platform後，您需要啟用資料集，以便將資料包含在即時客戶配置檔案中。
>
>這可透過API或Adobe Experience Platform介面來執行。 如需詳細資訊，請參閱專屬檔案：
>
>* [為即時客戶個人檔案啟用資料集](https://docs.adobe.com/content/help/en/experience-platform/rtcdp/datasets/dataset.html)
>* [使用API為即時客戶個人檔案和身分服務設定資料集](https://docs.adobe.com/content/help/en/experience-platform/catalog/api/getting-started.html)


## 重要概念{#key-concepts}

* 「出廠設定映射」僅適用於預設以Campaign Standard形式提供的欄位。 若要吸收所有自訂欄位和資源，每位客戶都需要定義自己的對應。

* Adobe Experience Platform資料連接器將定期推送描述檔資料至平台&#x200B;。 時間間隔為15分鐘。 此值可使用[Adobe Experience PlatformAPI](https://docs.adobe.com/content/help/en/experience-platform/ingestion/home.html)進行修改。

* 資料工程師可以發佈、修改及暫停從Campaign到Adobe Experience Platform的對應。

* 任何定位維度皆可映射。 建議是對單一定位維度中的所有欄位有一個單一對應。

* 所有描述檔更新（包括渠道選擇加入／選擇退出）都是批次更新的一部分。

* 任何Adobe Campaign Standard或XDM模式更改都需要手動重新映射&#x200B;。

* 追蹤記錄檔和Broadlog資料會自動擷取至Adobe Experience Platform做為體驗事件。 這個攝取的內容即時串流到Adobe Experience Platform。

* Experience CloudID服務(ECID)是裝置識別碼，預設會與體驗事件一起傳送。

   此ID是指派給訪客的唯一且永續性ID，平台身分服務可用來識別不同Experience Cloud解決方案中的相同訪客及其資料。 有關詳細資訊，請參閱[Experience Cloud身份服務幫助](https://docs.adobe.com/content/help/en/id-service/using/home.html)。

   >[!NOTE]
   >
   >請注意，如果兩個或兩個以上配置式共用同一設備，則統一身份服務中這兩個配置式的ECID將相同。

## 限制 {#limitations}

* 不支援立即可用的訂閱事件傳輸。 若要傳輸訂閱事件，您可以在Adobe Experience Platform建立對應的XDM和資料集，然後為這些資料設定自訂資料對應。

* 關於隱私權要求（存取和刪除動作），客戶需要透過[隱私權核心服務](https://docs.adobe.com/content/help/en/experience-platform/privacy/home.html#how-to-use-privacy-service-to-manage-privacy-job-requests)提出個別要求：一個代表競選，一個代表Adobe Experience Platform。 如需詳細資訊，請參閱促銷活動中的[關於隱私權要求](https://experienceleague.adobe.com/docs/campaign-standard/using/getting-started/privacy/privacy-requests.html?lang=zh-Hant#getting-started)和[管理隱私權要求](https://helpx.adobe.com/tw/campaign/kb/acs-privacy.html#ManagingPrivacyRequests)。

* 對於每個XDM欄位，DULE標籤需要在Adobe Experience Platform完成。 這是客戶應對應用DULE標籤的責任。

* 只有在Adobe Experience Platform套用DULE標籤後，行銷動作的限制才能適用。 在此之前，所有資料都可用於所有類型的行銷動作。

* 每15分鐘，批處理作業就會運行一次，並標識自最新批處理以來更改的記錄。 如果所有記錄在同一時間戳記下發生更改，則可能出現效能瓶頸以管理所有配置檔案的提取

## 教學課程影片{#video}

此視訊提供Adobe Experience Platform資料連接器的概觀。

>[!VIDEO](https://video.tv.adobe.com/v/27304?quality=12&captions=eng)

有關「Adobe Experience Platform資料連接器」的其他視頻可在[此處](https://docs.adobe.com/content/help/zh-Hant/campaign-standard-learn/tutorials/administrating/adobe-experience-platform-data-connector/understanding-the-adobe-experience-platform-data-connector.translate.html)獲得。
