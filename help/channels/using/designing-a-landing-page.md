---
title: 設計登陸頁面
seo-title: 設計登陸頁面
description: 設計登陸頁面
seo-description: 請依照下列步驟來設計登陸頁面的內容，並將其連結至服務。
page-status-flag: 從未啓動
uuid: de6fe190-835c-40fd-8101-a809 b430 b423
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 頻道
content-type: reference
topic-tags: 登陸頁面
discoiquuid: bd77d6f0-3143-4030-a91 b-988a2 bbc534
context-tags: LandingPage，主要
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b0cf437ec97153b53bd4502171b24286abb25731

---


# Designing a landing page{#designing-a-landing-page}

## About content design {#about-content-design}

Landing pages are created as any [marketing activity](../../start/using/marketing-activities.md#about-marketing-activities).

在設計著陸頁面時，您必須定義下列內容：

* 頁面本身，
* 確認頁面，
* 錯誤頁面。

使用動作列下方的切換器來顯示並設定每個頁面。

這些頁面的內容是透過促銷活動內容編輯器來設計。Refer to [Design content](../../designing/using/about-landing-page-content-design.md).

## Mapping form fields {#mapping-form-fields}

輸入欄位可用來儲存或更新Campaign資料庫中的資料。為此，您需要連結資料庫欄位與輸入區域、選項按鈕或核取方塊類型區塊。若要這麼做：

1. 在登陸頁面中選取區塊。
1. Complete the **[!UICONTROL Form data]** part in the palette.

   ![](assets/editing_lp_content_4.png)

1. Choose a database field to link with the form field in the **[!UICONTROL Field]** selection zone.

   When the **[!UICONTROL Mandatory]** option is checked, the page can only be submitted if the user has completed this field. 如果強制欄位尚未完成，當使用者驗證頁面時會出現錯誤訊息。

   >[!NOTE]
   >
   >Landing pages can only be mapped with **Profiles**.

1. Define the field type by choosing, for example **[!UICONTROL Text]**, **[!UICONTROL Number]**,or **[!UICONTROL Date]** in the **[!UICONTROL HTML type of the field]** selection area.

>[!NOTE]
>
>內建著陸頁面的預設欄位已預先設定。您可以視需要加以修改。

## Submitting the form {#submitting-the-form}

您可以選取訪客點按送出按鈕時要執行的動作。若要這麼做：

1. 選取登陸頁面的送出按鈕。
1. 在左側面板的下拉式清單中選取動作。Possible actions are: **[!UICONTROL Refresh]** (to refresh the page) and **[!UICONTROL Next page]** (to display the confirmation page).

   ![](assets/editing_lp_content_5.png)

此外，您還可以變更按鈕的標籤或設定特定連結。若要這麼做：

1. 選取送出按鈕。
1. Click on the ![](assets/lp_link_properties.png) button in the left panel.
1. 輸入按鈕的標籤，選取連結類型、屬性和目標。

   ![](assets/lp_link_custom.png)

## Linking a form to a service {#linking-a-form-to-a-service}

您可以將表單連結至服務，讓描述檔在驗證登陸頁面時訂閱特定服務。

連結著陸頁面的參數可讓您指定執行中的動作類型，以及著陸頁面是否明確連結至單一服務或是否為一般服務。

若要選擇要連結的服務，您必須：

1. Edit the landing page properties accessed via the ![](assets/edit_darkgrey-24px.png) icon in the landing page dashboard, and display the **[!UICONTROL Job]** parameters.

   ![](assets/lp_edit_properties_button.png)

1. Choose **[!UICONTROL Subscription]** in the **[!UICONTROL Specific actions]** drop-down list.

   ![](assets/lp_parameters_5.png)

1. Select **[!UICONTROL Specific service]** to link the landing page to a single service. 如果您想要使用著陸頁面使用多個服務，請勿選取此選項。

   Use the **[!UICONTROL Specified service in the URL]** option to allow the landing page to be used for several services. 因此，您必須在設定服務時參考著陸頁面。

### Confirm a landing page submission {#confirm-a-landing-page-submission}

當訪客提交著陸頁面時，您可以設定觸發的動作。若要這麼做：

1. Edit the landing page properties accessed via the ![](assets/edit_darkgrey-24px.png) icon in the landing page dashboard, and display the **[!UICONTROL Job]** parameters.

   ![](assets/lp_edit_properties_button.png)

1. Under the **[!UICONTROL Specific actions]** section, select **[!UICONTROL Start sending message]** to determine the sending of an automatic message, for example to confirm subscription to a service. 然後您需要選取電子郵件傳送範本。

   請注意，如果已在服務層級設定確認訊息，您不應在此畫面中選取一個確認訊息，以避免傳送多個確認訊息。Refer to [Configure a service](../../audiences/using/creating-a-service.md).

1. Create **[!UICONTROL Additional data]** to enable storing additional data when the landing page is being submitted. 造訪頁面的人看不到此資料。只會考量常數值。

   ![](assets/lp_parameters_6.png)

## Setting permissions and pre-loading data {#setting-permissions-and-pre-loading-data}

著陸頁面的存取權可以限制為已識別的訪客，這些訪客來自促銷活動傳送之訊息中的連結。在此情況下，您可以在登陸頁面中預先載入資料。若要這麼做：

1. Edit the landing page properties accessed via the ![](assets/edit_darkgrey-24px.png) icon in the landing page dashboard, and display the **[!UICONTROL Access & loading]** parameters.

   ![](assets/lp_edit_properties_button.png)

1. Select **[!UICONTROL Preload visitor data]**.

   如果頁面訪客對應至資料庫中的描述檔，則其資料會顯示在表單欄位中以資料庫資料對應的表格欄位中，並考量著陸頁面的個人化元素。

   ![](assets/lp_parameters_3.png)

您也可以：

* Use the URL parameters to identify the visitors, using the **[!UICONTROL Authorize visitor identification via URL parameters]** option: then you must choose the loading key and map the filter parameters with the parameters of the corresponding URL.
* Authorize any visitor to access the landing page, using the **[!UICONTROL Authorize unidentified visitors]** option.

## Setting Google reCAPTCHA {#setting-google-recaptcha}

您可以使用著陸頁面設定Google ReCAPTCHA V3，以保護其不受機器人造成的垃圾郵件和濫用。若要將它與登陸頁面搭配使用，您必須先建立外部帳戶。For more information on how to configure it, refer to this [section](../../administration/using/external-accounts.md#google-recaptcha-external-account).

在您的Google ReCAPTCHA V外部帳戶設定完成後，您可以將其新增至登陸頁面：

1. Before publishing your landing page, access the page properties accessed via the ![](assets/edit_darkgrey-24px.png) icon from you landing page dashboard.

   ![](assets/lp_parameters_google3.png)

1. Unfold the **[!UICONTROL Access & loading]** menu.
1. Check the **[!UICONTROL Use reCAPTCHA to protect your site from spam and abuse]** option.
1. 選取您先前建立的Google ReCAPTCHA外部帳戶。

   ![](assets/lp_parameters_google.png)

1. Click **[!UICONTROL Confirm]**.

您的登陸頁面現在會使用Google ReCAPTCHA設定，您可在頁面底部檢視。

![](assets/lp_parameters_google2.png)

然後Google ReCAPTCHA會根據使用者與您頁面的互動情況，傳回分數。To check your score, connect to your [Google admin console](https://g.co/recaptcha/admin).
