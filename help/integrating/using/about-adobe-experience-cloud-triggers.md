---
title: 關於 Adobe Experience Cloud 觸發程式
description: 透過Adobe Analytics追蹤客戶的特定行為，您現在可以在Adobe Campaign中傳送個人化電子郵件給客戶。
page-status-flag: 從未激活
uuid: 0aa4bd6e-1bb5-4d0b-913b-eca93f050acd
contentOwner: 紹維亞
products: SG_CAMPAIGN/STANDARD
audience: 整合
content-type: 參考
topic-tags: 使用促銷活動和觸發器
discoiquuid: e526b205-2d01-4a8b-9685-ba1d9a1f459f
context-tags: 觸發器，概述；觸發器，主
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 關於 Adobe Experience Cloud 觸發程式{#about-adobe-experience-cloud-triggers}

Experience Cloud啟動核心服務與Adobe Campaign的整合可讓您傳送個人化電子郵件給客戶，以回應Adobe Analytics在您網站上追蹤的特定行為（15分鐘內）。 **[!UICONTROL Triggers]**

在Adobe Experience cloud中，您定義了不同的觸發因素，即您要監控的客戶行為，例如所有放棄在您網站上瀏覽的客戶、在您的網站上進行搜尋，但並未進行購買，或甚至是作業過期的客戶。 建立觸發器時，您會定義觸發器的條件，以及在事件（上傳）中傳送至Adobe Campaign的資料。

 在Adobe Campaign中，您選取先前建立的觸發器，您會以資料圖資料豐富事件資料，並定義連結至該觸發器的交易訊息範本。 例如，當客戶放棄在您網站上的瀏覽時，會將事件傳送至Adobe Campaign，然後Adobe Campaign會透過15分鐘內傳送給客戶的再行銷電子郵件來運用此事件。

**相關主題：**

* 瞭解不同類型的觸發器： [Adobe Experience cloud檔案](https://marketing.adobe.com/resources/help/en_US/mcloud/triggers.html)。
* 觀看「根 [據網站活動觸發重新行銷訊息](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html#step-two) 」影片。
* 瞭解我們的兩個 [放棄觸發器使用案例](../../integrating/using/abandonment-triggers-use-cases.md)。

## 觸發使用者程式 {#triggers-user-process}

>[!CAUTION]
>
>在執行主用戶步驟之前，需要配置功能。 如需詳細資訊，請參 [閱「啟用功能](../../integrating/using/configuring-triggers-in-experience-cloud.md#activating-the-functionality)」、「設 [定解決方案與服務](../../integrating/using/configuring-triggers-in-experience-cloud.md#configuring-solutions-and-services) 」以及「 [在Campaign中建立映射觸發器」](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign)。

在Adobe Campaign中，使用者程式的主要步驟為：

1. 建立連結至現有Adobe Experience cloud觸發器的觸發器事件。
1. 發佈觸發器事件。
1. 定義事務性消息模板的內容。
1. 測試範本（建立測試描述檔並傳送校樣）。
1. 發佈交易式訊息範本。

本節將說明完整的使 [用案例](../../integrating/using/abandonment-triggers-use-cases.md)。

## 重要附註 {#important-notes}

以下是使用「觸發程式——促銷活動」整合之前要考慮的一些重要附註：

* 觸發器不支援推播通知。 僅支援電子郵件和簡訊。
* 您可以透過Analytics擷取的中繼資料（例如電子郵件ID、頁面名稱等）豐富觸發器。
* 您可以將觸發器協調至儲存在Campaign standard中的描述檔，並使用描述檔的欄位來個人化訊息。
* 一旦收到觸發器，就會處理並調節觸發器並送出。 視收到的觸發器數量、範本中使用的個人化欄位數，大約需要5到15分鐘。

>[!NOTE]
>
>如需最佳實務與技術限制的詳細資訊，請參閱 [Triggers最佳實務與限制](../../integrating/using/configuring-triggers-in-experience-cloud.md#triggers-best-practices-and-limitations)。

