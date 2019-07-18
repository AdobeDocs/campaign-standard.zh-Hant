---
title: 關於Adobe Experience Cloud觸發器
seo-title: 關於Adobe Experience Cloud觸發器
description: 關於Adobe Experience Cloud觸發器
seo-description: 透過Adobe Analytics追蹤客戶的特定行為，您現在可以在Adobe Campaign中傳送個人化電子郵件給客戶。
page-status-flag: 從未啓動
uuid: 0aa4bd6e-1bb5-4d0b-913b-ea93 f050 acd
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 整合
content-type: reference
topic-tags: 使用促銷活動與觸發器
discoiquuid: e526b205-2d01-4a8b-9685-ba1 d9 a1 f459 f
context-tags: 觸發器，概觀；觸發器，主要
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: cb6396228e42f99f7e184a82e6c894b09a164cd9

---


# About Adobe Experience Cloud Triggers{#about-adobe-experience-cloud-triggers}

Integration between the Experience Cloud Activation core service **[!UICONTROL Triggers]** and Adobe Campaign allows you to send personalized emails to your customers as a reaction to specific behaviors that are tracked on your website by Adobe Analytics (within 15 minutes).

在Adobe Experience Cloud中，您定義了不同的觸發因素，也就是說，您要監視的客戶行為，例如所有放棄您網站造訪的客戶、在您的網站上進行搜尋但未進行購買的客戶，或是其作業過期的客戶。建立觸發器時，您會定義觸發的條件和將在事件(plad)中傳送的資料(pload)。

在Adobe Campaign中，您會選取先前建立的觸發器，您會利用資料資料資料豐富事件資料，並定義連結到該觸發器的交易訊息範本。例如，當用戶端放棄您的網站上的瀏覽時，會傳送事件給Adobe Campaign，該事件接著會透過在15分鐘內傳送給用戶端的重新行銷電子郵件利用該事件。

**相關主題：**

* Learn about the different types of triggers: [Adobe Experience Cloud documentation](https://marketing.adobe.com/resources/help/en_US/mcloud/triggers.html).
* Watch the [Trigger Remarketing Messages based on Site Activity](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html#step-two) video.
* Discover our two [Abandonment Triggers use cases](../../integrating/using/abandonment-triggers-use-cases.md).

## Triggers user process {#triggers-user-process}

>[!CAUTION]
>
>在執行主要使用者步驟之前，必須先設定功能。For more on this refer to [Activating the functionality](../../integrating/using/configuring-triggers-in-experience-cloud.md#activating-the-functionality), [Configuring solutions and services](../../integrating/using/configuring-triggers-in-experience-cloud.md#configuring-solutions-and-services) and [Creating a mapped trigger in Campaign](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign).

在Adobe Campaign中，使用者程序的主要步驟為：

1. 建立連結至現有Adobe Experience Cloud觸發器的觸發事件。
1. 發佈觸發事件。
1. 定義交易訊息範本的內容。
1. 測試範本(建立測試描述檔並傳送校樣)。
1. 發佈交易訊息範本。

Complete use cases are described in [this section](../../integrating/using/abandonment-triggers-use-cases.md).

## Important notes {#important-notes}

以下是在使用觸發器之前應考量的重要附註-促銷活動整合：

* 觸發器不支援推播通知。僅支援電子郵件和簡訊。
* 您可以利用透過Analytics擷取的中繼資料(例如電子郵件ID、頁面名稱等)豐富觸發器。
* 您可以將觸發器與儲存在Campaign Standard中的設定檔協調，並使用描述檔的欄位個人化訊息。
* 在收到觸發器時，會處理並協調並傳送。根據收到的觸發項目量，範本中使用的個人化欄位數需要大約到15分鐘。

>[!NOTE]
>
>For more on best practices and technical limitations, refer to [Triggers best practices and limitations](../../integrating/using/configuring-triggers-in-experience-cloud.md#triggers-best-practices-and-limitations).

