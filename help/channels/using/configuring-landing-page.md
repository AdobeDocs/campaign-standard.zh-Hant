---
title: 設定著陸頁面
description: 瞭解如何設定著陸頁面的屬性。
page-status-flag: never-activated
uuid: 5b222ea2-6628-457f-a618-bfc0e5eb93dd
contentOwner: lemaitre
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: landing-pages
discoiquuid: 899c7152-f415-4df9-b4b4-5ff3470a4e32
context-tags: landingPage,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 95e01eb33097fc76caac3f4dd5f5591461b887cf

---


# 設定著陸頁面 {#configuring-landing-page}

## 確認著陸頁面提交 {#confirm-a-landing-page-submission}

當訪客提交著陸頁面時，您可以設定觸發的動作。 操作步驟：

1. 編輯透過著陸頁面控制面板中 ![](assets/edit_darkgrey-24px.png) 的圖示存取的著陸頁面屬性，並顯示 **[!UICONTROL Job]** 參數。

   ![](assets/lp_edit_properties_button.png)

1. 在該節 **[!UICONTROL Specific actions]** 下，選 **[!UICONTROL Start sending message]** 擇確定自動消息的發送，例如確認服務的訂閱。 然後您需要選取電子郵件傳送範本。

   請注意，如果服務級別已配置確認消息，則不應在此螢幕中選擇一個消息以避免發送多個確認消息。 請參 [閱Configure a service](../../audiences/using/creating-a-service.md)。

1. 建立 **[!UICONTROL Additional data]** 以啟用在提交著陸頁面時儲存其他資料。 此資料對瀏覽頁面的使用者不可見。 只考慮常數值。

   ![](assets/lp_parameters_6.png)

## 將登陸頁面連結至服務 {#linking-a-landing-page-to-a-service}

您可以將表單連結至服務，如此在驗證著陸頁面時，描述檔就可以訂閱特定服務。

連結著陸頁面的參數可讓您指定執行的動作類型，以及著陸頁面是否特別連結至單一服務或是否為一般服務。

要選擇要連結的服務，您需要：

1. 編輯透過著陸頁面控制面板中 ![](assets/edit_darkgrey-24px.png) 的圖示存取的著陸頁面屬性，並顯示 **[!UICONTROL Job]** 參數。

   ![](assets/lp_edit_properties_button.png)

1. 從下 **[!UICONTROL Subscription]** 拉式清 **[!UICONTROL Specific actions]** 單中選擇。

   ![](assets/lp_parameters_5.png)

1. 選擇 **[!UICONTROL Specific service]** 將登陸頁面連結至單一服務。 如果您想要在登陸頁面上使用數個服務，請勿選取此選項。

   使用 **[!UICONTROL Specified service in the URL]** 選項可允許將登陸頁面用於數個服務。 因此，在配置服務時，您必須參考著陸頁面。

## 設定權限和預先載入資料 {#setting-permissions-and-pre-loading-data}

登陸頁面的存取權可限制給已識別的訪客，這些訪客來自例如促銷活動所傳送之訊息中的連結，或是特定組織單位。
若是已識別的訪客，您可以在登陸頁面中預先載入其資料。 操作步驟：

1. 編輯透過著陸頁面控制面板中 ![](assets/edit_darkgrey-24px.png) 的圖示存取的著陸頁面屬性，並顯示 **[!UICONTROL Access & loading]** 參數。

   ![](assets/lp_edit_properties_button.png)

1. Select **[!UICONTROL Preload visitor data]**.

   如果頁面的訪客與資料庫中的描述檔相對應，則其資料會顯示在與資料庫資料對應的表單欄位中，而著陸頁面的個人化元素也會納入考量。

   ![](assets/lp_parameters_3.png)

您也可以：

* 使用URL參數來識別訪客，使用下列 **[!UICONTROL Authorize visitor identification via URL parameters]** 選項：然後，您必須選擇載入索引鍵，並將篩選參數對應至對應URL的參數。
* 使用選項授權任何訪客存取著陸 **[!UICONTROL Authorize unidentified visitors]** 頁面。

著陸頁面也可以連結至組織單位。 這將定義使用者對不同登陸頁面的存取權。 要分配組織單位，請執行以下操作：

1. 透過圖示存取您的著陸頁面 **[!UICONTROL Edit properties]** 屬性。

   ![](assets/lp_parameters_google3.png)

1. 展開 **[!UICONTROL Access authorization]**。

1. 按一下下拉式功能表，然後選取您的組織單位。 有關如何建立組織單位的詳細資訊，請參閱本 [頁](../../administration/using/organizational-units.md)。

   ![](assets/lp_org_unit_2.png)

1. 自 **[!UICONTROL Created by]**&#x200B;動完 **[!UICONTROL Created]**&#x200B;成、 **[!UICONTROL Access authorization]** 和 **[!UICONTROL Last modified]** 欄位。

1. 按一 **[!UICONTROL Confirm]** 下 **[!UICONTROL Save]**。

您的登陸頁面現在只能由所選組織單位內的使用者存取和管理。

![](assets/lp_org_unit_3.png)

## 設定Google reCAPTCHA {#setting-google-recaptcha}

您可以使用登陸頁面設定Google reCAPTCHA V3，以保護其免受Bot造成的垃圾訊息和濫用。 若要將它用於著陸頁面，您必須先建立外部帳戶。 有關如何配置的詳細資訊，請參閱本 [節](../../administration/using/external-accounts.md#google-recaptcha-external-account)。

一旦您的Google reCAPTCHA V3外部帳戶設定完成後，您就可以將它新增至您的登陸頁面：

1. 發佈著陸頁面之前，請先存取透過您著陸頁面控制面板 ![](assets/edit_darkgrey-24px.png) 圖示存取的頁面屬性。

   ![](assets/lp_parameters_google3.png)

1. 展開功 **[!UICONTROL Access & loading]** 能表。
1. 勾選 **[!UICONTROL Use reCAPTCHA to protect your site from spam and abuse]** 選項。
1. 選取您先前建立的Google reCAPTCHA外部帳戶。

   ![](assets/lp_parameters_google.png)

1. Click **[!UICONTROL Confirm]**.

您的登陸頁面現在已設定Google reCAPTCHA，可在頁面底部檢視。

![](assets/lp_parameters_google2.png)

然後，Google reCAPTCHA會根據使用者與您頁面的互動，傳回分數。 若要檢查您的分數，請連線至您的 [Google管理控制台](https://g.co/recaptcha/admin)。
