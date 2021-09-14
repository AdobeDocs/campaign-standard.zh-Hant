---
title: 關於 Campaign-Points of Interest 資料整合
description: 從行動應用程式的訂閱者收集地標資料，透過Adobe Campaign中的整合，傳送位置型行銷訊息給訂閱者。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics-for-mobile
feature: Audiences
role: Data Architect
level: Intermediate
exl-id: 358194f9-34ce-4dd5-b9b2-1a7d541879ab
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 6%

---

# 關於 Campaign-Points of Interest 資料整合{#about-campaign-points-of-interest-data-integration}

除了追蹤客戶的線上存在外，您還可以利用客戶的實際位置。 透過與Adobe Analytics for Mobile的整合，您可以使用Adobe Campaign，傳送位置型行銷訊息給行動應用程式的訂閱者。

地標包含緯度、經度和與標籤相關聯的半徑。 它們定義於[AdobeMobile Services](https://experienceleague.adobe.com/docs/mobile-services/using/home.html)介面中。

訂閱者開啟行動應用程式時，如果位置符合地標，Adobe Campaign會透過Experience Cloud行動SDK擷取資料。 您可以使用此資訊根據使用者位置傳送個人化訊息（例如電子郵件、推播通知、簡訊）。

例如，您可以向使用您的應用程式，並在過去兩週內造訪您在波士頓的其中一家商店的客戶傳送10%的折扣優惠。

[使用興趣點資料個人化Campaign訊息](../../integrating/using/personalizing-campaign-messages-with-point-of-interest-data.md)區段中會顯示使用案例。
