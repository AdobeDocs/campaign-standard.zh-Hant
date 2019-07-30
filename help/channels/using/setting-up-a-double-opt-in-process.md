---
title: 設定雙重加入程序
seo-title: 設定雙重加入程序
description: 設定雙重加入程序
seo-description: 請遵循下列步驟，使用Adobe Campaign中的著陸頁面設定兩個選擇加入程序。
page-status-flag: 從未啓動
uuid: 23e6c4-e2-e2 c7-472f-b616-36a95225 ac1 d
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 頻道
content-type: reference
topic-tags: 登陸頁面
discoiquuid: 1a24504e-7f9d-4297-b39 e-c5 f085 b0 f388
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6dd0c32259d942a0fb790f345cd13800a57e814a

---


# Setting up a double opt-in process{#setting-up-a-double-opt-in-process}

## About double opt-in {#about-double-opt-in}

傳送電子郵件時，需要使用雙加入機制。它可保護平台不會出現錯誤或無效的電子郵件地址、垃圾郵件，並防止可能出現垃圾郵件抱怨。

原則是傳送電子郵件以確認訪客的合約，然後將其儲存為「促銷活動」資料庫中的「個人檔案」：訪客會填寫線上登陸頁面，然後收到電子郵件，並必須按一下確認連結中的，以完成訂閱。

![](assets/optin_mechanism.png)

若要設定此選項，您必須：

1. 建立和發佈登陸頁面，讓訪客可以註冊和訂閱。此登陸頁面將可從網站取得。Visitors who fill in and submit this landing page will be stored in the database but ‘blacklisted', in order not to receive any communication before the final validation (see [Managing blacklisting in Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)).
1. 使用確認連結建立並自動傳送選擇加入電子郵件。此電子郵件將會鎖定提交著陸頁面的人口族群。它會以允許目標「退出」設定檔的電子郵件範本為基礎。
1. 重新導向至確認登陸頁面。此最終登陸頁面將提議確認按鈕：訪客必須按一下它。您可以設計歡迎電子郵件，在確認完成時傳送，例如新增電子郵件中的特殊選件給新收件者。

必須以特定順序在Adobe Campaign中設定這些步驟，才能正確啓用所有參數。

## Step 1: Create the confirmation landing page {#step-1--create-the-confirmation-landing-page}

設定雙重加入機制的程序始於建立確認登陸頁面：當訪客點按確認電子郵件以註冊時，將會顯示此頁面。

若要建立並設定此著陸頁面，您必須：

1. Design a [new landing page](../../channels/using/about-landing-pages.md) based on the **[!UICONTROL Profile acquisition (acquisition)]** template. Enter the label '**CONFIRMATION**'.

   If you need to use [services](../../audiences/using/about-subscriptions.md), you can also use the **[!UICONTROL Subscription (sub)]** template.

1. Edit the landing page properties and under the **[!UICONTROL Access and loading]** section, unselect the option **[!UICONTROL Authorize unidentified visitors]**, select **[!UICONTROL Preload visitor data]** (this one is not mandatory).

   ![](assets/optin_confirmlp_param.png)

1. In the **[!UICONTROL Job]** &gt; **[!UICONTROL Additional data]** section, click **[!UICONTROL Add an element]** and enter the following context path:

   /context/profile/blackList

   Set the value to **false** and click **[!UICONTROL Add]**.

   ![](assets/optin_confirmlp_newelement.png)

   此上下文會移除黑名單欄位，以便傳送電子郵件。We will see later that the first landing page was setting this field to **true** before confirmation, to prevent from sending emails to non-confirmed profiles. For more on this, see [Step 3: Create the acquisition landing page](../../channels/using/setting-up-a-double-opt-in-process.md#step-3--create-the-acquisition-landing-page).

1. 自訂登陸頁面的內容：您可以顯示個人化資料，並將確認按鈕標籤變更為「按一下此處以確認我的訂閱」。

   ![](assets/optin_confirmlp_design.png)

1. 調整確認頁面的內容，通知您的訂閱者已註冊。

   ![](assets/optin_confimlp_page2.png)

1. [測試並發佈](../../channels/using/sharing-a-landing-page.md) 登陸頁面。

## Step 2: Create the confirmation email {#step-2--create-the-confirmation-email}

在建立確認著陸頁面後，您可以設計確認電子郵件：此電子郵件會自動傳送給驗證贏取登陸頁面的每位訪客。此驗證視為事件，電子郵件則是交易訊息，連結至特定的打字規則，可鎖定退出人口族群。

以下說明建立這些元素的步驟。您必須先關注它們，才能建立贏取著陸頁面本身，因為此電子郵件範本將會被參照。

### Create the event {#create-the-event}

The confirmation email is a [transactional message](../../channels/using/about-transactional-messaging.md) as it reacts to an event: the validation of the form. 您必須先建立事件，然後建立交易訊息的範本。

1. Create an event, from the **[!UICONTROL Marketing plans]** &gt; **[!UICONTROL Transactional messages]** &gt; **[!UICONTROL Event configuration]** menu, accessible from the Adobe Campaign logo, and enter the label '**CONFIRM**'.
1. Select the **[!UICONTROL Profile]** targeting dimension and click **[!UICONTROL Create]**.

   ![](assets/optin_eventcreate.png)

1. In the **[!UICONTROL Fields]** section, click **[!UICONTROL Create element]** and add the **[!UICONTROL email]** in the data structure to enable reconciliation.
1. In the **[!UICONTROL Enrichment]** section, click **[!UICONTROL Create element]** and select the target resource **[!UICONTROL Profile]**. You can then map on the **[!UICONTROL email]** in the **[!UICONTROL Join definition]** section, or any other composite reconciliation key, depending on your needs.

   ![](assets/optin_eventcreate_join.png)

   If you need to use services, you can also add the **[!UICONTROL serviceName]**.

1. Select **[!UICONTROL Profile]** as the **[!UICONTROL Targeting enrichment]** in the dropdown list.
1. Click **[!UICONTROL Publish]** to publish the event.

事件已就緒。您現在可以設計電子郵件範本。This template must include a link to the **CONFIRMATION** landing page created before. For more on this, see [Design the confirmation message](../../channels/using/setting-up-a-double-opt-in-process.md#design-the-confirmation-message).

### Create the typology rule {#create-the-typology-rule}

You need to create a specific [typology rule](../../administration/using/about-typology-rules.md), by duplicating an out-of-box one. 此規則允許傳送訊息給未確認其合約且仍列入黑名單的個人檔案。依預設，打字規則排除退出(即列入黑名單的)描述檔。若要建立此類型學規則，請遵循下列步驟：

1. From the Adobe Campaign logo, select **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Typologies]** and click **[!UICONTROL Typologies]**.
1. Duplicate the out-of-box typology **[!UICONTROL Transactional message on profile (mcTypologyProfile)]**.
1. Once duplication confirmed, edit the new typology and enter the label **TYPOLOGY_PROFILE**.
1. Remove the **blacklisted address** rule.
1. Click **[!UICONTROL Save]**.

此類型學現在可以與確認電子郵件相關聯。

### Design the confirmation message {#design-the-confirmation-message}

確認電子郵件是根據過去建立之事件的交易訊息。請依照下列步驟建立此訊息：

1. From the Adobe Campaign logo, select **[!UICONTROL Marketing plans]** &gt; **[!UICONTROL Transactional messages]** and click **[!UICONTROL Transactional messages]**.
1. Edit the **CONFIRM** email template and personalize it. 您可以上傳現有內容或使用立即可用的範本。
1. Add a link to the **CONFIRMATION** landing page, and click **[!UICONTROL Confirm]** to save modifications.

   ![](assets/optin_email_selectlp.png)

1. 編輯電子郵件範本屬性。In the **[!UICONTROL Advanced parameters]** &gt; **[!UICONTROL Preparation]** section, select the **TYPOLOGY_PROFILE** typology created before.
1. 儲存並發佈交易訊息。

## Step 3: Create the acquisition landing page {#step-3--create-the-acquisition-landing-page}

您必須建立初始贏取著陸頁面：此op-in表格將會發佈在您的網站上。

若要建立並設定此著陸頁面，您必須：

1. Design a [new landing page](../../channels/using/about-landing-pages.md) based on the **[!UICONTROL Profile acquisition (acquisition)]** template. Enter the label '**ACQUISITION**'.
1. Edit the landing page properties: in the **[!UICONTROL Job]** &gt; **[!UICONTROL Additional data]** section, click **[!UICONTROL Add an element]** and enter the following context path:

   /context/profile/blackList

   and set the value to **true**.

   強制黑名單並避免傳送訊息給未確認其合約的訪客。The validation of the CONFIRMATION landing page will set this field to **false** after confirmation. For more on this, see [Step 1: Create the confirmation landing page](../../channels/using/setting-up-a-double-opt-in-process.md#step-1--create-the-confirmation-landing-page).

1. In the **[!UICONTROL Job]** &gt; **[!UICONTROL Specific actions]** section, select the option **[!UICONTROL Start sending messages]**.
1. In the associated drop-down list, choose the **CONFIRM** transactional message template you created.

   ![](assets/optin_acquisition_startoption.png)

1. 根據您的品牌和您需要取得的資料，自訂登陸頁面的內容。You can display personalized data and change the label of the confirmation button to **Confirm my subscription** for example.

   ![](assets/optin_acquisition_page1.png)

1. 自訂確認頁面以通知新訂閱者，他必須驗證訂閱。

   ![](assets/optin_acquisition_page2.png)

1. [測試並發佈](../../channels/using/sharing-a-landing-page.md) 登陸頁面。

現在已設定雙重加入機制。You can run and test the procedure from end to end, starting from the public URL of this **[!UICONTROL ACQUISITION]** landing page. 此URL會顯示在著陸頁面控制面板中。
