---
solution: Campaign Standard
product: campaign
title: 管理登錄頁面表單資料
description: 瞭解如何管理登錄頁面表單資料。
audience: channels
content-type: reference
topic-tags: landing-pages
context-tags: landingPage,main
feature: 登陸頁面
role: User
level: Intermediate
exl-id: 7083447c-4cac-41cb-8453-369819e0c7c1
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '613'
ht-degree: 62%

---

# 管理登陸頁面表單資料{#managing-landing-page-form-data}

## 變更登錄頁面表單資料屬性{#changing-a-landing-page-form-data-properties}

您可以將資料庫欄位連結到輸入區域、單選按鈕或核取方塊類型區塊。要執行此操作，請選取區塊並存取浮動視窗中的&#x200B;**[!UICONTROL Form data]**。

![](assets/delivery_content_9.png)

* **欄位**&#x200B;輸入區域可讓您選取要與表單欄位連結的資料庫欄位。
* 「**必填**」選項可讓您僅在使用者已填入欄位時，授權提交頁面。如果未填入必填欄位，則會出現錯誤訊息。

## 對應表單欄位 {#mapping-form-fields}

輸入欄位可用來儲存或更新行銷活動資料庫中的資料。為此，您需要將資料庫欄位與輸入區域、單選按鈕或核取方塊類型區塊連結起來。操作步驟：

1. 在登錄頁面中選取區塊。
1. 完成浮動視窗中的 **[!UICONTROL Form data]** 部分。

   ![](assets/editing_lp_content_4.png)

1. 選取資料庫欄位以與 **[!UICONTROL Field]** 選取區域中的表單欄位連結。登錄頁面只能與&#x200B;**設定檔**&#x200B;相對應。

1. 視需要核取 **[!UICONTROL Mandatory]** 選項。只有當使用者已填妥此欄位時，才能提交頁面。如果未完成必填欄位，當使用者驗證頁面時，將會顯示錯誤訊息。

1. 定義欄位類型，方法是選取如 **[!UICONTROL Text]**、**[!UICONTROL Number]**，或是 **[!UICONTROL HTML type of the field]** 選取區域中的 **[!UICONTROL Date]**。如果您選取必填項目 **[!UICONTROL Checkbox]**，請確定其屬於 **[!UICONTROL Field]** 類型。

>[!NOTE]
>
>內建登錄頁面的預設欄位已預先設定。您可以視需要修改它們。

## 資料儲存與調解{#data-storage-and-reconciliation}

資料調解參數可讓您定義在使用者提交登錄頁面中輸入的資料後，如何加以管理。

操作步驟：

1. 編輯透過登錄頁面控制面板中 ![](assets/edit_darkgrey-24px.png) 圖示存取的登錄頁面屬性，並顯示 **[!UICONTROL Job]** 參數。

   ![](assets/lp_parameters_4.png)

1. 選取 **[!UICONTROL Reconciliation key]**：這些資料庫欄位（例如：電子郵件、名字、姓氏）可用來判斷訪客是否有已在 Adobe Campaign 資料庫中知道的設定檔。這允許您根據定義的更新策略參數更新或建立設定檔。
1. 定義 **[!UICONTROL Form parameter mapping]**：此部分允許您對應登錄頁面欄位參數以及調解金鑰中使用的參數。
1. 選取 **[!UICONTROL Update strategy]**：如果調解金鑰恢復現有資料庫設定檔，您可以選取使用此設定檔以表單中輸入的資料進行更新，或者改為阻止此更新。

## 協定核取方塊 {#agreement-checkbox}

您可以在提交登錄頁面之前新增設定檔必須勾選的核取方塊。

例如，這可讓您在使用者提交表單前，要求其同意隱私權政策，或讓他們接受您的條款與條件。

<!--This is particularly useful in the following case:

When a profile opens the landing page from an Outlook.com mailbox, Outlook checks whether the links on the landing page are suspicious. However, this Outlook security feature (called safelinks) has an unwanted effect: it automatically activates the buttons included on the landing page. Consequently, profiles are automatically subscribed or unsubscribed without confirmation when the landing page is displayed after clicking the email link, even if they do not submit the form.

![](assets/lp_submit_button.png)

To avoid this, Adobe recommends you always add to your landing page a checkbox which enables the profile to agree before proceeding with subscription or unsubscription.-->

>[!IMPORTANT]
>
>您的使用者必須選取此核取方塊。 若未選取，他們將無法提交登錄頁面。

要插入並配置此複選框，請執行以下操作：

1. 設計登錄頁面時，按一下&#x200B;**[!UICONTROL Show source]**。

   ![](assets/lp_show_source.png)

1. 手動插入核取方塊，如以下範例中：

   ![](assets/lp_checkbox_code.png)

   <!--
   <div id="HtmlPage_htmlPage.line3" data-nl-format="datetime"><input type="checkbox" class="nl-dce-todo" data-nl-bindto="agreement" data-nl-agreementmsg="You must agree with the terms and conditions before proceeding" />I agree with the terms and conditions</div>
   -->

1. 按一下&#x200B;**[!UICONTROL Hide source]**。

1. 隨即顯示新核取方塊。 選取它。

   ![](assets/lp_select_checkbox.png)

1. 相應的下拉清單顯示在調色板的&#x200B;**[!UICONTROL Form data]**&#x200B;部分中。 從清單中選擇&#x200B;**[!UICONTROL Agreement]**。

   ![](assets/lp_form_data_drop-down.png)

   >[!NOTE]
   >
   >**[!UICONTROL Agreement]**&#x200B;元素未對應至Campaign資料庫的欄位。

1. 按一下&#x200B;**[!UICONTROL Form data]**&#x200B;旁的![](assets/lp-properties-icon.png)圖示以存取核取方塊進階屬性。

1. 您可以視需要編輯訊息。

   ![](assets/lp_agreement_message.png)

   如果使用者在提交表單之前未選取核取方塊，此文字將會顯示為警告。

   >[!NOTE]
   >
   >預設情況下，此操作是強制操作，無法更改。

1. 按一下&#x200B;**[!UICONTROL Confirm]**。

現在，每次顯示登錄頁面時，使用者必須先選取此核取方塊，才能提交表單。 若未顯示，則會顯示警告，且在啟動核取方塊前，使用者無法提交表單。