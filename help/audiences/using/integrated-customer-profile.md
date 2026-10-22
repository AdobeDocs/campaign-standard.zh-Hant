---
title: 整合式客戶輪廓
description: 透過單一檢視追蹤每個客戶互動：Adobe Campaign整合式客戶設定檔會在整個客戶生命週期中更新。
audience: audiences
content-type: reference
topic-tags: managing-profiles
context-tags: marketingHistory,main
feature: Profiles
role: User
level: Beginner
exl-id: cf3c6408-7fa0-423a-b34b-f4fee771fb47
TQID: 'https://experienceleague.adobe.com/a-v47cX0DxN6dzLQs-r4e2yMajLD6GHIVXXEX9Ol-lY'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
    internal-label: APIs
  - id: afa4204e-6d08-4e29-bc35-26aafb656d48
    internal-label: Profiles and audiences
subfeature_v2:
  - id: f529d0bd-1401-4c88-9833-43228cc1d40f
    internal-label: Profiles
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: fd2e3797-f2ea-4b36-a9af-52acf5e90513
    internal-label: Customer profiles
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '282'
ht-degree: 41%
---
# 整合式客戶輪廓{#integrated-customer-profile}

資料庫的每個聯絡人都可以使用整合式客戶輪廓。 此行銷記錄將所有與客戶聯絡相關的行銷資訊結合為單一檢視。 之後，您可以在一個集中位置存取所有數位行為、線上和離線交易：聯絡資訊、收到的電子郵件、追蹤記錄、訂閱和取消訂閱等。

若要存取整合式客戶輪廓，請執行以下步驟：

1. 從Adobe Campaign首頁，按一下「**[!UICONTROL Customer profiles]**」卡片或「**設定檔**」標籤，以顯示設定檔清單。

1. 若要根據特定欄位搜尋設定檔，請開啟搜尋窗格，然後選取您要執行搜尋的欄位。


   ![](assets/profile-search.png)

1. 指定要搜尋的值，然後按Enter鍵。

   >[!NOTE]
   >
   >請注意，可以根據電子郵件、名字和姓氏欄位，以及在擴充資源時新增的自訂欄位來執行搜尋。
   >
   >搜尋會區分大小寫，且僅會在首碼上執行。 例如，您將無法使用設定檔的姓氏來查詢設定檔。

1. 選取連絡人以開啟其設定檔。

   ![](assets/mkt_hist_access.png)

之後，您可以存取此連絡人的&#x200B;**行銷記錄**。

此頁面會收集關於輪廓的重要資訊及事件清單。

按一下清單中的事件以開啟它：您可以存取已傳送的訊息或設定檔已訂閱的服務。

![](assets/mkt_hist_view.png)

>[!NOTE]
>
>您也可以使用 Adobe Campaign Standard API 存取行銷記錄。 如需詳細資訊，請參閱[專屬文件](../../api/using/interacting-with-marketing-history.md)。
