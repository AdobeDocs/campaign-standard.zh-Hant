---
solution: Campaign Standard
product: campaign
title: 關於 Adobe Experience Cloud 觸發程式
description: 透過 Adobe Analytics 追蹤客戶的特定行為，您現在可以在 Adobe Campaign 中傳送個人化電子郵件給客戶。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-triggers
context-tags: trigger,overview;trigger,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 100%

---


# 關於 Adobe Experience Cloud 觸發程式{#about-adobe-experience-cloud-triggers}

Experience Cloud 啟動核心服務 **[!UICONTROL Triggers]** 與 Adobe Campaign 的整合可讓您傳送個人化電子郵件給客戶，以回應 Adobe Analytics 在您網站上追蹤的特定行為（15 分鐘內）。

在 Adobe Experience Cloud 中，您定義了不同的觸發因素，即您要監視的客戶行為，例如所有放棄在您網站上瀏覽的客戶、在您的網站上進行搜尋，但並未進行購買，或甚至是工作階段過期的客戶。建立觸發器時，您會定義觸發器的條件，以及在事件（上傳）中傳送至 Adobe Campaign 的資料。

在 Adobe Campaign 中，您選取先前建立的觸發器，您會以資料圖資料豐富事件資料，並定義連結至該觸發器的異動訊息範本。例如，當用戶端放棄在您的網站上瀏覽時，會將事件傳送至 Adobe Campaign，然後 Adobe Campaign 會在 15 分鐘內傳送給用戶的再行銷電子郵件來運用此事件。

下圖詳細說明此整合的運作方式。

![](assets/triggers_diagram.png)

**相關主題：**

* 瞭解不同類型的觸發器：[Adobe Experience Cloud 文件](https://docs.adobe.com/content/help/zh-Hant/core-services/interface/activation/triggers.html)。
* 觀看「[根據網站活動觸發再行銷訊息](https://helpx.adobe.com/tw/marketing-cloud/how-to/email-marketing.html#step-two)」影片。
* 瞭解我們的兩個[放棄觸發器使用案例](../../integrating/using/abandonment-triggers-use-cases.md)。

## 觸發使用者流程 {#triggers-user-process}

>[!CAUTION]
>
>在執行主使用者步驟之前，需要配置功能。如需詳細資訊，請參閱「[啟用功能](../../integrating/using/configuring-triggers-in-experience-cloud.md#activating-the-functionality)」、「[設定解決方案與服務](../../integrating/using/configuring-triggers-in-experience-cloud.md#configuring-solutions-and-services)」以及「[在 Campaign 中建立對應觸發器](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign)」。

在 Adobe Campaign 中，使用者流程的主要步驟為：

1. 建立連結至現有 Adobe Experience Cloud 觸發器的觸發器事件。
1. 發佈觸發器事件。
1. 定義異動訊息範本的內容。
1. 測試範本（建立測試設定檔並傳送證明）。
1. 發佈異動訊息範本。

[本節](../../integrating/using/abandonment-triggers-use-cases.md)將說明完整的使用案例。

## 重要附註 {#important-notes}

以下是使用「觸發程式 – 促銷活動」整合之前要考慮的一些重要附註：

* 觸發器不支援推播通知。僅支援電子郵件和簡訊。
* 您可以透過 Analytics 擷取的中繼資料（例如電子郵件 ID、頁面名稱等）豐富觸發器。
* 您可以將觸發器調解至儲存在 Campaign Standard 中的設定檔，並使用設定檔的欄位來進行訊息個人化。
* 一旦收到觸發器，就會處理並調解觸發器並送出。視收到的觸發器數量、範本中使用的個人化欄位數，大約需要 5 到 15 分鐘。

>[!NOTE]
>
>如需最佳實務與技術限制的詳細資訊，請參閱[觸發器最佳實務與限制](../../integrating/using/configuring-triggers-in-experience-cloud.md#triggers-best-practices-and-limitations)。

