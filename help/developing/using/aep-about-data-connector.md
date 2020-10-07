---
title: 關於 Adobe Experience Platform Data Connector
description: 管理XDM結構，讓您的Campaign Standard資料可在Adobe Experience Platform上使用。
page-status-flag: never-activated
uuid: 867b1c4b-4c79-4c52-9d0a-ef71993e50a2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: configuring-channels
discoiquuid: 406c955a-b2d2-4099-9918-95f5fa966067
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 關於 Adobe Experience Platform Data Connector {#about-aep-data-connector}

>[!IMPORTANT]
>
>Adobe Experience Platform Data Connector目前正在測試中，可能會在不另行通知的情況下頻繁更新。 客戶必須在Azure上代管（目前僅限北美地區測試版）才能存取這些功能。 如果您想要存取，請聯絡Adobe客戶服務。

Adobe Experience Platform Data Connector將XTK資料（在Campaign中收錄的資料）對應至Adobe Experience Platform上的Experience Data Model(XDM)資料，協助現有客戶在Adobe Experience Platform上提供其資料。

請注意，此連 **接器是單向的** ，會將資料從Adobe Campaign Standard傳送至Adobe Experience Platform。 這些資料從未從Adobe Experience Platform傳送至Adobe Campaign Standard。

Adobe Experience Platform Data Connector是專為瞭解Adobe Campaign Standard自訂資源並瞭解客戶整體資料架構應如何位於Adobe Experience Platform內的資料工程師而設計。 ****

以下各節將說明在Campaign Standard和Adobe Experience Platform之間執行資料對應的關鍵步驟。 這從建立XDM架構和資料集開始。

本頁也提供操作 [影片](https://docs.adobe.com/content/help/zh-Hant/campaign-standard-learn/tutorials/administrating/adobe-experience-platform-data-connector/understanding-the-adobe-experience-platform-data-connector.translate.html)。

>[!NOTE]
>一旦設定Adobe Experience Platform Data Connector並成功將資料匯入Adobe Experience Platform後，您就必須啟用資料集，讓資料能包含在即時客戶個人檔案中。
>
>這可透過API或Adobe Experience Platform介面來執行。 如需詳細資訊，請參閱專屬檔案：
>
>* [為即時客戶個人檔案啟用資料集](https://docs.adobe.com/content/help/en/experience-platform/rtcdp/datasets/dataset.html)
>* [使用API為即時客戶個人檔案和身分服務設定資料集](https://docs.adobe.com/content/help/en/experience-platform/catalog/api/getting-started.html)


## 重要概念 {#key-concepts}

* 預設情況下，「開箱對應」僅適用於「促銷活動標準」中提供的欄位。 若要吸收所有自訂欄位和資源，每位客戶都需要定義自己的對應。

* Adobe Experience Platform Data Connector會定期在平台上推送描述檔資料&#x200B;。 間隔時間為15mn。 此值可使用 [Adobe Experience Platform API來修改](https://docs.adobe.com/content/help/en/experience-platform/ingestion/home.html)。

* 資料工程師可以發佈、修改及暫停從Campaign到Adobe Experience Platform的對應。

* 任何定位維度皆可映射。 建議是對單一定位維度中的所有欄位有一個單一對應。

* 所有描述檔更新（包括渠道選擇加入／選擇退出）都是批次更新的一部分。

* 任何Adobe Campaign Standard或XDM架構變更都需手動重新對應&#x200B;。

* 追蹤記錄檔和Broadlog資料會自動擷取至Adobe Experience Platform作為「體驗事件」。 這個擷取問題會即時串流至Adobe Experience Platform。

* Experience Cloud ID服務(ECID)是裝置識別碼，預設會與Experience Events一起傳送。

   此ID是指派給訪客的唯一且永續性ID，平台身分服務可用來識別不同Experience Cloud解決方案中的相同訪客及其資料。 如需詳細資訊，請參閱 [Experience Cloud Identity Service說明](https://docs.adobe.com/content/help/en/id-service/using/home.html)。

   >[!NOTE]
   >
   >請注意，如果兩個或兩個以上配置式共用同一設備，則統一身份服務中這兩個配置式的ECID將相同。

## 限制 {#limitations}

* 不支援立即可用的訂閱事件傳輸。 若要傳輸訂閱事件，您可以在Adobe Experience Platform上建立對應的XDM和資料集，然後為這些資料設定自訂資料對應。

* 關於隱私權要求（存取和刪除動作），客戶需要透過隱私權核心服務提出個 [別要求](https://docs.adobe.com/content/help/en/experience-platform/privacy/home.html#how-to-use-privacy-service-to-manage-privacy-job-requests):一個用於Campaign，另一個用於Adobe Experience Platform。 如需詳細資訊，請參 [閱關於促銷活動](https://helpx.adobe.com/campaign/kb/acs-privacy.html#righttoaccess)[中的隱私權要求](https://helpx.adobe.com/tw/campaign/kb/acs-privacy.html#ManagingPrivacyRequests) 。

* 對於每個XDM欄位，DULE標籤必須在Adobe Experience Platform中完成。 這是客戶應對應用DULE標籤的責任。

* 只有在Adobe Experience Platform中套用DULE標籤後，才能適用行銷動作的限制。 在此之前，所有資料都可用於所有類型的行銷動作。

* 每15分鐘，批處理作業就會運行一次，並標識自最新批處理以來更改的記錄。 如果所有記錄在同一時間戳記下發生更改，則可能出現效能瓶頸以管理所有配置檔案的提取
