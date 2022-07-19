---
title: 關於 Adobe Experience Platform 資料連接器
description: 管理XDM架構，使您的Campaign Standard資料在Adobe Experience Platform上可用。
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
>Adobe Experience Platform資料連接器目前處於測試版，可能需要頻繁更新，恕不另行通知。 客戶需要在Azure上托管（目前僅在北美試用版）才能訪問這些功能。 如果您想訪問，請聯繫Adobe客戶服務。

Adobe Experience Platform資料連接器通過將XTK資料（在活動中攝取的資料）映射到Adobe Experience Platform的經驗資料模型(XDM)資料，幫助現有客戶提供其Adobe Experience Platform資料。

注意，連接器 **單向** 把資料從Adobe Campaign Standard傳到Adobe Experience Platform。 資料從未從Adobe Experience Platform發送到Adobe Campaign Standard。

Adobe Experience Platform資料連接器 **資料工程師** 他們瞭解Adobe Campaign Standard定制資源，並瞭解客戶的總體資料架構應如何位於Adobe Experience Platform。

以下各節介紹在Campaign Standard和Adobe Experience Platform之間執行資料映射的關鍵步驟。 這從建立XDM架構和資料集開始。

![](assets/do-not-localize/how-to-video.png) [在影片中探索此功能](#video)

>[!NOTE]
>一旦配置了Adobe Experience Platform資料連接器並將資料成功地接入Adobe Experience Platform，您需要啟用該資料集，以便資料包含在即時客戶配置檔案中。
>
>這可以通過API或Adobe Experience Platform介面執行。 有關詳細資訊，請參閱專用文檔：
>
>* [為即時客戶配置檔案啟用資料集](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/datasets/dataset.html)
>* [使用API為Real-time Customer Profile和Identity Service配置資料集](https://experienceleague.adobe.com/docs/experience-platform/catalog/api/getting-started.html)


## 重要概念 {#key-concepts}

* 「框外映射」僅適用於預設情況下在Campaign Standard中提供的欄位。 要接收所有自定義欄位和資源，每個客戶需要定義自己的映射。

* Adobe Experience Platform資料連接器將定期在平台中推送配置檔案數&#x200B;據。 時間間隔為15分鐘。 可以使用 [Adobe Experience PlatformAPI](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html)。

* 資料工程師可以發佈、修改和暫停從市場活動到Adobe Experience Platform的映射。

* 可以映射任何目標維。 建議對單個目標維中的所有欄位進行一個單一映射。

* 所有配置檔案更新（包括通道選擇加入/選擇退出）都是批更新的一部分。

* 任何Adobe Campaign Standard或XDM架構更改都需要手動重新映射&#x200B;。

* 跟蹤日誌和Broadlog資料作為體驗事件自動被接收到Adobe Experience Platform。 這個攝入問題被即時傳到Adobe Experience Platform。

* Experience CloudID服務(ECID)是預設使用體驗事件發送的設備標識符。

   它是分配給訪問者的唯一且持久的ID，平台標識服務可以使用它來識別不同Experience Cloud解決方案中的同一訪問者及其資料。 有關詳細資訊，請參閱 [Experience CloudIdentity Service幫助](https://experienceleague.adobe.com/docs/id-service/using/home.html)。

   >[!NOTE]
   >
   >請注意，如果兩個或多個配置檔案共用同一設備，則統一身份服務中這兩個配置檔案的ECID將相同。

## 限制 {#limitations}

* 不支援訂閱事件的現成傳輸。 要傳輸訂閱事件，可以在Adobe Experience Platform建立相應的XDM和資料集，然後為這些資料配置自定義資料映射。

* 關於隱私請求（訪問和刪除操作），客戶需要通過 [隱私核心服務](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html#how-to-use-privacy-service-to-manage-privacy-job-requests):一個給競選，一個給Adobe Experience Platform。 有關此的詳細資訊，請參閱 [關於隱私請求](https://experienceleague.adobe.com/docs/campaign-standard/using/getting-started/privacy/privacy-requests.html?lang=zh-Hant#getting-started) 和 [管理隱私請求](https://helpx.adobe.com/tw/campaign/kb/acs-privacy.html#ManagingPrivacyRequests) 在競選中。

* 對於每個XDM欄位，DULE標籤需要在Adobe Experience Platform完成。 這是應用DULE標籤的客戶責任。

* 只有在DULE標籤在Adobe Experience Platform應用後，才能適用對市場營銷操作的限制。 在此之前，所有資料都可用於所有類型的市場營銷操作。

* 每15分鐘，批處理作業將運行一次，它標識自最新批處理以來已更改的記錄。 如果所有記錄在同一時間戳下發生更改，則可能會出現效能瓶頸以管理所有配置檔案的接收

## 教程視頻 {#video}

此視頻概述了Adobe Experience Platform資料連接器。

>[!VIDEO](https://video.tv.adobe.com/v/27304?quality=12&captions=eng)

提供了與Adobe Experience Platform資料連接器相關的其他視頻 [這裡](https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/administrating/adobe-experience-platform-data-connector/understanding-the-adobe-experience-platform-data-connector.html)。
