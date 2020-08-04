---
title: 共用登錄頁面
description: 瞭解如何測試和發佈 Adobe Campaign 中的登錄頁面。
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
translation-type: ht
source-git-commit: 54612511de07edc3e6f3eea34ef095c26b35f4af
workflow-type: ht
source-wordcount: '383'
ht-degree: 100%

---


# 測試和發佈登錄頁面{#testing-publishing--landing-page}

## 關於登錄頁面範本 {#about-landing-page-publication}

發佈登錄頁面之前，您必須執行測試：驗證執行、設定存取權限並設定登錄頁面生命週期結束。這些步驟是先決條件，必須小心執行。

## 測試登錄頁面 {#testing-the-landing-page-}

由於登錄頁面會影響您的平台和資料，因此您需要小心地測試其執行。操作步驟：

1. 按一下登錄頁面動作列中的 **[!UICONTROL Test]** 按鈕。
1. 從測試畫面選取測試設定檔，以及測試服務（如果登錄頁面是要管理訂閱）。

   ![](assets/lp_test_2.png)

1. 在欄位中輸入資料，並選取選項。
1. 提交登錄頁面並檢查資料庫中的更新。

   >[!IMPORTANT]
   >
   >提交表單時，會更新使用的服務和設定檔。

1. 對各種設定檔和資料重複執行此步驟。

   您也可以從此畫面產生登錄頁面縮圖。

>[!NOTE]
>
>若要在促銷活動使用者介面中顯示登錄頁面預覽，應用程式伺服器　URL　必須是安全的。在該情況下，在設定您的品牌時，請使用　https://（而非http://）[設定此 URL](../../administration/using/branding.md#configuring-and-using-brands)。

## 設定有效性參數 {#setting-up-validity-parameters}

基於安全理由和平台效能，我們強烈建議您先在登錄頁面屬性中設定到期日，然後再發佈。在選取的日期時，登錄頁面會自動取消發佈。操作步驟：

1. 編輯透過登錄頁面控制面板中的 ![](assets/edit_darkgrey-24px.png) 按鈕存取的登錄頁面屬性。

   ![](assets/lp_edit_properties_button.png)

1. 在 **[!UICONTROL Publication]** 區段中設定到期日及時間：登錄頁面在指定日期將自動取消發佈，因此將無法使用。

   您可以選取要針對此日期及時間列入考量的時區。

1. 定義重新導向 URL，以便在嘗試存取非作用的登錄頁面時重新導向訪客。

   ![](assets/lp_settings_general.png)

>[!IMPORTANT]
>
>您也可以定義部署日期及時間：之後，登錄頁面就會在指定的日期自動發佈。

## 設定登錄頁面 {#publishing-a-landing-page}

當您發佈登錄頁面時，此頁面就會連線，而且可供您的訪客存取。

您可以隨時透過 **[!UICONTROL Publish]** 按鈕取消發佈或更新並重新發佈登錄頁面。不過，如果重新發佈失敗，而且您尚未取消發佈登錄頁面，第一個版本將會維持連線。
