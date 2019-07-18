---
title: 共用登陸頁面
seo-title: 共用登陸頁面
description: 共用登陸頁面
seo-description: 瞭解如何在Adobe Campaign中測試和發佈著陸頁面。
page-status-flag: 從未啓動
uuid: fb7b087a-3292-496c-bc41-2e3012 badf59
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 頻道
content-type: reference
topic-tags: 登陸頁面
discoiquuid: f7d4bb71-f957-4f86-97c7-8ac0 a0030026
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Sharing a landing page{#sharing-a-landing-page}

## About landing page publication {#about-landing-page-publication}

發佈著陸頁面之前，您必須執行測試：驗證執行、設定存取權並設定著陸頁面生命週期。這些步驟是必要的，必須小心執行。

## Testing the landing page {#testing-the-landing-page-}

著陸頁面會影響您的平台和資料，因此您需要仔細測試它的執行。若要這麼做：

1. Click the **[!UICONTROL Test]** button in the action bar of the landing page.
1. 在測試畫面中，選取測試設定檔，以及如果著陸頁面是用來管理訂閱，則測試服務。

   ![](assets/lp_test_2.png)

1. 在欄位中輸入資料，然後選擇選項。
1. 提交登陸頁面並檢查資料庫中的更新。

   >[!CAUTION]
   >
   >表單提交時，會更新使用的服務和描述檔。

1. 重復使用各種描述檔和資料。

   您也可以從此畫面產生著陸頁面縮圖。

## Setting up validity parameters {#setting-up-validity-parameters}

在發佈之前，基於安全性原因和平台效能，我們強烈建議您在著陸頁面屬性中設定到期日。在選取的日期上，著陸頁面會自動解除發佈。若要這麼做：

1. Edit the landing page properties accessed via the ![](assets/edit_darkgrey-24px.png) button in the landing page dashboard.

   ![](assets/lp_edit_properties_button.png)

1. Set up expiration date and time in the **[!UICONTROL Publication]** section: the landing page will automatically be unpublished on the specified date and therefore no longer be available.

   您可以選取要計入此日期和時間的時區。

1. 定義重新導向URL，以便在嘗試存取非作用中著陸頁面時重新導向訪客。

   ![](assets/lp_settings_general.png)

>[!CAUTION]
>
>您也可以定義部署日期和時間：著陸頁面將會自動發佈在指定的日期上。

## Publishing a landing page {#publishing-a-landing-page}

當您發佈著陸頁面時，它會上線，並可供訪客存取。

You can unpublish or update and republish your landing page at any time, via the **[!UICONTROL Publish]** button. 不過，如果重新發佈失敗，而且您尚未解除發佈著陸頁面，第一個版本將維持在線上狀態。
