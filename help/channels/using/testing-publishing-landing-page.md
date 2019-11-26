---
title: 共用登錄頁面
description: 瞭解如何測試和發佈Adobe Campaign中的登陸頁面。
page-status-flag: never-activated
uuid: fb7b087a-3292-496c-bc41-2e3012bacf59
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: landing-pages
discoiquuid: f7d4bb71-f957-4f86-97c7-8ac0a0030026
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 95e01eb33097fc76caac3f4dd5f5591461b887cf

---


# 測試和發佈著陸頁面{#testing-publishing--landing-page}

## 關於著陸頁面發佈 {#about-landing-page-publication}

發佈著陸頁面之前，您必須執行測試：驗證執行、設定存取權並設定著陸頁面生命週期結束。 這些步驟是先決條件，必須小心執行。

## 測試著陸頁面 {#testing-the-landing-page-}

由於著陸頁面會影響您的平台和資料，因此您需要仔細測試其執行。 操作步驟：

1. 按一下 **[!UICONTROL Test]** 著陸頁面動作列中的按鈕。
1. 從測試畫面中，選取測試描述檔，以及如果著陸頁面是要管理訂閱的測試服務。

   ![](assets/lp_test_2.png)

1. 在欄位中輸入資料，並選取選項。
1. 提交登陸頁面並檢查資料庫中的更新。

   >[!CAUTION]
   >
   >提交表單時，會更新使用的服務和描述檔。

1. 對各種描述檔和資料重複此步驟。

   您也可以從此螢幕產生著陸頁面縮圖。

## 設定有效性參數 {#setting-up-validity-parameters}

在發佈之前，基於安全性原因和平台效能，強烈建議您在登陸頁面屬性中設定到期日。 在選取的日期，著陸頁面會自動取消發佈。 操作步驟：

1. 編輯透過著陸頁面控制面板中 ![](assets/edit_darkgrey-24px.png) 的按鈕存取的著陸頁面屬性。

   ![](assets/lp_edit_properties_button.png)

1. 在區段中設定到期日期和時間 **[!UICONTROL Publication]** :著陸頁面將在指定的日期自動取消發佈，因此不再提供。

   您可以選擇要考慮此日期和時間的時區。

1. 定義重新導向URL，以在嘗試存取非作用中的著陸頁面時重新導向訪客。

   ![](assets/lp_settings_general.png)

>[!CAUTION]
>
>您也可以定義部署日期和時間：然後著陸頁面就會在指定的日期自動發佈。

## 發佈著陸頁面 {#publishing-a-landing-page}

當您發佈著陸頁面時，該頁面會上線，並可供您的訪客存取。

您可以隨時透過按鈕解除發佈或更新並重新發佈著陸 **[!UICONTROL Publish]** 頁面。 不過，如果重新發佈失敗，而您尚未解除發佈著陸頁面，第一個版本將會維持線上上。
