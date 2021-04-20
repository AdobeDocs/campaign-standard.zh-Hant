---
solution: Campaign Standard
product: campaign
title: 設定雙重加入程序
description: 請依照下列步驟，使用 Adobe Campaign 中的登錄頁面來設定雙重選取加入程式。
audience: channels
content-type: reference
topic-tags: landing-pages
feature: Landing Pages
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '1155'
ht-degree: 90%

---


# 設定雙重加入程序{#setting-up-a-double-opt-in-process}

## 關於雙重選取加入 {#about-double-opt-in}

傳送電子郵件時，最佳作法是雙重加入機制。它可保護平台免受錯誤或無效的電子郵件地址、垃圾郵件機器人，並防止可能的垃圾郵件投訴。

原則是先傳送電子郵件確認訪客的同意，再將其儲存為「設定檔」至您的促銷活動資料庫：訪客填寫線上登錄頁面，接著收到電子郵件，必須按一下確認連結才能完成訂閱。

![](assets/optin_mechanism.png)

若要設定此設定，您必須：

1. 建立並發佈登錄頁面，讓訪客可以註冊並訂閱。此登錄頁面可從網站取得。填寫並提交此著陸頁面的訪客會儲存在資料庫中，但會新增至登入清單，以便在最終驗證之前不會收到任何通訊（請參閱Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)中的「登入清單管理」）。[
1. 使用確認連結自動建立及傳送選取加入的電子郵件。此電子郵件將定位提交登錄頁面的訪客。它將以電子郵件範本為基礎，可以定位「選取退出」設定檔。
1. 重新導向至確認登錄頁面。此最終登錄頁面將建議一個確認按鈕：訪客必須按一下它。您可以設計歡迎電子郵件，在確認完成時傳送，例如在電子郵件中為新收件者新增特殊優惠。

這些步驟必須以特定順序在 Adobe Campaign 中設定，才能正確啟用所有參數。

## 步驟　1：建立確認登錄頁面 {#step-1--create-the-confirmation-landing-page}

設定雙重選取加入機制的程式，從建立確認登錄頁面開始：當訪客點按確認電子郵件以進行註冊時，會顯示此頁面。

若要建立及設定此登錄頁面，您必須：

1. 根據 **[!UICONTROL Profile acquisition (acquisition)]** 範本，設計[新登錄頁面](../../channels/using/getting-started-with-landing-pages.md)。輸入標籤　&#39;**CONFIRMATION**&#39;。

   如果您需要使用[服務](../../audiences/using/about-subscriptions.md)，也可以使用 **[!UICONTROL Subscription (sub)]** 範本。

1. 編輯登錄頁面屬性，並在 **[!UICONTROL Access and loading]** 區段下方取消選取　**[!UICONTROL Authorize unidentified visitors]**　選項，選取　**[!UICONTROL Preload visitor data]**（此選項非必要）。

   ![](assets/optin_confirmlp_param.png)

1. 在　**[!UICONTROL Job]** > **[!UICONTROL Additional data]**　區段中，按一下　**[!UICONTROL Add an element]**　並輸入下列內容路徑：

   /context/profile/blackList

   將值設為 **false**，然後按一下　**[!UICONTROL Add]**。

   ![](assets/optin_confirmlp_newelement.png)

   此內容會移除「登入清單」欄位，以便能夠傳送電子郵件。 我們稍後會看到，第一個登錄頁面在確認前將此欄位設為 **true**，以防止傳送電子郵件至未確認的設定檔。如需詳細資訊，請參閱 [步驟 3：建立贏取登錄頁面](#step-3--create-the-acquisition-landing-page)。

1. 自訂登錄頁面的內容：例如，您可以顯示個人化資料，並將確認按鈕的標籤變更為「按一下此處確認我的訂閱」。

   ![](assets/optin_confirmlp_design.png)

1. 調整確認頁面的內容，通知您的訂閱者他們已註冊。

   ![](assets/optin_confimlp_page2.png)

1. [測試和發佈](../../channels/using/testing-publishing-landing-page.md)登錄頁面

## 步驟2：建立確認電子郵件 {#step-2--create-the-confirmation-email}

建立確認登錄頁面後，您就可以設計確認電子郵件：此電子郵件會自動傳送給驗證贏取登錄頁面的每位訪客。此驗證會視為事件，而電子郵件則是交易式訊息，連結至特定的類型規則，以定位選取退出母體。

建立這些元素的步驟如下所述。在建立贏取登錄頁面之前，您必須先追蹤這些範本，因為此電子郵件範本將會在其中參照。

### 建立事件 {#create-the-event}

確認電子郵件是[交易式訊息](../../channels/using/getting-started-with-transactional-msg.md)，當它回應事件時：表單的驗證。您必須先建立事件，然後建立交易式訊息的範本。

1. 從 **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Event configuration]** 建立可從 Adobe Campaign 標誌存取的事件，然後輸入標籤 &#39;**CONFIRM**&#39;。
1. 選取 **[!UICONTROL Profile]** 目標維度，然後按一下 **[!UICONTROL Create]**。

   ![](assets/optin_eventcreate.png)

1. 在 **[!UICONTROL Fields]** 區段中，按一下 **[!UICONTROL Create element]** 並新增資料結構中的 **[!UICONTROL email]** 以啟用協調。
1. 在 **[!UICONTROL Enrichment]** 區段中，按一下 **[!UICONTROL Create element]** 並選取 **[!UICONTROL Profile]** 目標資源。之後，您可以根據自己的需求，對應 **[!UICONTROL Join definition]** 區段中的 **[!UICONTROL email]** 欄位或任何其他複合調解金鑰。

   ![](assets/optin_eventcreate_join.png)

   如果您需要使用服務，請在 **[!UICONTROL serviceName]** 欄位上新增 **[!UICONTROL Service]** 目標資源和對應。如需詳細資訊，請參閱。

1. 選取 **[!UICONTROL Profile]** 作為下拉式清單中 **[!UICONTROL Targeting enrichment]**。
1. 按一下 **[!UICONTROL Publish]** 以發佈事件。

活動已就緒。您現在可以設計電子郵件範本。此範本必須包含先前建立之 **CONFIRMATION** 登錄頁面的連結。有關詳細資訊，請參閱[設計確認訊息](#design-the-confirmation-message)。

### 建立類型 {#create-the-typology-rule}

您需要建立特定[類型](../../sending/using/about-typology-rules.md)，方法是複製現成可用的類型。分類法將允許傳送訊息給尚未確認同意且仍在密文名單中的個人檔案。 依預設，排除選擇退出（亦即登入清單）描述檔的類型。 若要建立此類型，請依照下列步驟進行：

1. 從 Adobe Campaign 標誌中，選取&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Typologies]** 並按一下 **[!UICONTROL Typologies]**。
1. 複製現成可用的類型 **[!UICONTROL Transactional message on profile (mcTypologyProfile)]**。
1. 複製確認後，請編輯新的類型，並輸入標籤 **TYPOLOGY_PROFILE**。
1. 刪除denylist **上的**&#x200B;地址規則。
1. 按一下 **[!UICONTROL Save]**。

此類型現在可與確認電子郵件關聯。

### 設計確認訊息 {#design-the-confirmation-message}

確認電子郵件是根據先前建立的事件進行交易的訊息。請依照下列步驟建立此訊息：

1. 從 Adobe Campaign 標誌中，選取 **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** 並按一下 **[!UICONTROL Transactional messages]**。
1. 編輯 **CONFIRM** 電子郵件範本並加以個人化。您可以上傳現有內容或使用現成範本。
1. 新增連結至 **CONFIRMATION** 登錄頁面，然後按一下 **[!UICONTROL Confirm]** 以儲存修改。

   ![](assets/optin_email_selectlp.png)

1. 編輯電子郵件範本屬性。在 **[!UICONTROL Advanced parameters]** > **[!UICONTROL Preparation]** 區段中，選取以前建立的 **TYPOLOGY_PROFILE** 類型。
1. 儲存並發佈交易式訊息。

## 步驟3：建立贏取登錄頁面 {#step-3--create-the-acquisition-landing-page}

您必須建立初始贏取登錄頁面：此選取加入表格將會發佈在您的網站上。

若要建立及設定此登錄頁面，您必須：

1. 根據 **[!UICONTROL Profile acquisition (acquisition)]** 範本，設計[新登錄頁面](../../channels/using/getting-started-with-landing-pages.md)。輸入標籤 &#39;**ACQUISITION**&#39;。
1. 編輯登錄頁面屬性：在&#x200B;**[!UICONTROL Job]** > **[!UICONTROL Additional data]** 區段中，按一下 **[!UICONTROL Add an element]** 並輸入下列內容路徑：

   /context/profile/blackList

   並將值設為 **true**。

   這是強制新增至登入清單，並避免傳送訊息給未確認其同意的訪客的強制性。 驗證 CONFIRMATION 登錄頁面後，會在確認後將此欄位設 為 **false**。如需詳細資訊，請參閱[步驟 1：建立確認登錄頁面](#step-1--create-the-confirmation-landing-page)。

1. 在 **[!UICONTROL Job]** > **[!UICONTROL Specific actions]** 區段中，選取 **[!UICONTROL Start sending messages]** 選項。
1. 在相關聯的下拉式清單中，選取您建立的 **CONFIRM** 交易式訊息範本。

   ![](assets/optin_acquisition_startoption.png)

1. 根據您的品牌和您需要取得的資料，自訂登錄頁面的內容。例如，您可以顯示個人化資料，並將確認按鈕的標籤變更為&#x200B;**確認我的訂閱**。

   ![](assets/optin_acquisition_page1.png)

1. 自訂確認頁面，通知新訂閱者他需要驗證訂閱。

   ![](assets/optin_acquisition_page2.png)

1. [測試和發佈](../../channels/using/testing-publishing-landing-page.md)登錄頁面

現在已設定雙重加入機制。您可以從此 **[!UICONTROL ACQUISITION]** 登錄頁面的公用 URL 開始，從頭到尾執行並測試程序。此 URL 會顯示在登錄頁面控制面板中。
