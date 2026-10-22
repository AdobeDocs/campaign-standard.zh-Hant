---
title: 關於 Campaign-Points of Interest 資料整合
description: 從行動應用程式的訂閱者收集Points of Interest資料，並透過Adobe Campaign中的整合傳送位置型行銷訊息給訂閱者。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics-for-mobile
feature: Audiences
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 358194f9-34ce-4dd5-b9b2-1a7d541879ab
TQID: 'https://experienceleague.adobe.com/NMHm-sHLhsjMqprniSnxca27zpoxGEhRGKlt1IJXfVg'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: afa4204e-6d08-4e29-bc35-26aafb656d48
    internal-label: Profiles and audiences
subfeature_v2:
  - id: d6330382-c886-4f7a-a4f7-74e3f36c0d9c
    internal-label: Audiences
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
topic_v2:
  - id: df401a2a-327d-468c-a5e4-b7b7ccd071a0
    internal-label: Data integration
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 6%
---
# 關於 Campaign-Points of Interest 資料整合{#about-campaign-points-of-interest-data-integration}

除了追蹤客戶的線上狀態外，您也可以利用客戶的實體位置。 透過與適用於行動裝置的Adobe Analytics整合，您可以使用Adobe Campaign傳送位置型行銷訊息給行動應用程式的訂閱者。

地標是由緯度、經度以及與標籤相關聯的半徑所組成。 已在[Adobe Mobile Services](https://experienceleague.adobe.com/docs/mobile-services/using/home.html)介面中定義。

訂閱者開啟您的行動應用程式時，如果位置符合Point of Interest，Adobe Campaign會透過Experience Cloud Mobile SDK擷取資料。 您可以使用此資訊，根據使用者的位置傳送個人化訊息（例如電子郵件、推播通知、簡訊訊息）。

例如，您可以傳送10%折扣優惠給使用您的應用程式，並在過去兩週內造訪您位於波士頓的店舖的客戶。

在[個人化Campaign訊息與Point of Interest資料](../../integrating/using/personalizing-campaign-messages-with-point-of-interest-data.md)區段中呈現使用案例。
