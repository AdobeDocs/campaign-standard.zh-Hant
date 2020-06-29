---
title: 查詢示例
description: 此部分在使用查詢活動時顯示使用案例。
page-status-flag: never-activated
uuid: b3c629fa-370e-481c-b347-fcf9f5a5e847
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 8d46ce28-0101-4f13-865a-2208ed6d6139
context-tags: query,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2d994d85f126951215f1227301599c554c1f12c8
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 0%

---


# 查詢示例 {#query-samples}

本節介紹使用活動時的使用 **[!UICONTROL Query]** 案例。 有關如何使用活動的詳 **[!UICONTROL Query]** 細資訊，請參 [閱本節](../../automating/using/query.md)。

## 以簡單描述檔屬性為目標 {#targeting-on-simple-profile-attributes}

下列範例顯示一個查詢活動，其設定是針對居住在倫敦的18至30歲男性。

![](assets/query_sample_1.png)

## 針對電子郵件屬性進行定位 {#targeting-on-email-attributes}

下列範例顯示一個查詢活動，其設定是以電子郵件地址網域「orange.co.uk」定位描述檔。

![](assets/query_sample_emaildomain.png)

下列範例顯示已設定為定位其電子郵件地址之描述檔的查詢活動。

![](assets/query_sample_emailnotempty.png)

## 定位生日為今天的個人檔案 {#targeting-profiles-whose-birthday-is-today}

下列範例顯示設定為定位生日為今天的描述檔的查詢活動。

1. 拖曳查 **[!UICONTROL Birthday]** 詢中的篩選器。

   ![](assets/query_sample_birthday.png)

1. 將設定 **[!UICONTROL Filter type]** 為並 **[!UICONTROL Relative]** 選擇 **[!UICONTROL Today]**。

   ![](assets/query_sample_birthday2.png)

## 鎖定開啟特定傳送的設定檔 {#targeting-profiles-who-opened-a-specific-delivery}

下列範例顯示一個查詢活動，其設定為篩選開啟傳送且標籤為「夏季時間」的描述檔。

1. 拖曳查 **[!UICONTROL Opened]** 詢中的篩選器。

   ![](assets/query_sample_opened.png)

1. 選取傳送，然後按一下 **[!UICONTROL Confirm]**。

   ![](assets/query_sample_opened2.png)

## 針對因特定原因而傳送失敗的設定檔 {#targeting-profiles-for-whom-deliveries-failed-for-a-specific-reason}

下列範例顯示一個查詢活動，其設定是篩選因其郵箱已滿而傳送失敗的描述檔。 此查詢僅適用於具有管理權限且屬於組織單位的用 **[!UICONTROL All (all)]** 戶(請參 [閱本節](../../administration/using/organizational-units.md))。

1. 選擇資 **[!UICONTROL Delivery logs]** 源，以便直接在傳送記錄表中篩選(請參 [閱使用與定位維度不同的資源](../../automating/using/using-resources-different-from-targeting-dimensions.md))。

   ![](assets/query_sample_failure1.png)

1. 拖曳查 **[!UICONTROL Nature of failure]** 詢中的篩選器。

   ![](assets/query_sample_failure2.png)

1. 選擇要定位的失敗類型。 就我們而言 **[!UICONTROL Mailbox full]**。

   ![](assets/query_sample_failure3.png)

## 過去7天未連絡定位設定檔 {#targeting-profiles-not-contacted-during-the-last-7-days}

下列範例顯示一個查詢活動，其設定是用來篩選過去7天未連絡的設定檔。

1. 拖曳查 **[!UICONTROL Delivery logs (logs)]** 詢中的篩選器。

   ![](assets/query_sample_7days.png)

   在下 **[!UICONTROL Does not exist]** 拉式清單中選取，然後拖曳篩 **[!UICONTROL Delivery]** 選器。

   ![](assets/query_sample_7days1.png)

1. 設定篩選如下。

   ![](assets/query_sample_7days2.png)

## 定位按一下特定連結的個人檔案 {#targeting-profiles-who-clicked-a-specific-link-}

1. 拖曳查 **[!UICONTROL Tracking logs (tracking)]** 詢中的篩選器。

   ![](assets/query_sample_trackinglogs.png)

1. 拖曳篩 **[!UICONTROL Label (urlLabel)]** 選器。

   ![](assets/query_sample_trackinglogs2.png)

1. 在欄位 **[!UICONTROL Value]** 中，輸入在傳送中插入連結時所定義的標籤，然後確認。

   ![](assets/query_sample_trackinglogs3.png)
