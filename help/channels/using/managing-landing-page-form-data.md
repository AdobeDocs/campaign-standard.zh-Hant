---
title: 管理登錄頁面表單資料
description: 瞭解如何管理登錄頁面表單資料。
audience: channels
content-type: reference
topic-tags: landing-pages
context-tags: landingPage,main
feature: Landing Pages
role: User
level: Intermediate
exl-id: 7083447c-4cac-41cb-8453-369819e0c7c1
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '835'
ht-degree: 14%

---

# 管理登陸頁面表單資料{#managing-landing-page-form-data}

在登入頁面內容中，輸入欄位可用來儲存或更新來自Campaign資料庫的資料。

要執行此操作，這些欄位必須對應到資料庫欄位。

您可以透過左側浮動視窗上的&#x200B;**[!UICONTROL Form data]**&#x200B;區段來定義及管理其對應。

![](assets/lp_form-data.png)

## 對應表單欄位 {#mapping-form-fields}

若要根據您的需求更新Campaign資料庫，請將相關資料庫欄位連結至登入頁面的輸入區域、單選按鈕或核取方塊型別區塊。

要執行此操作，請遵循下列步驟：

1. 在登入頁面內容中選取區塊。

   >[!NOTE]
   >
   >內建登錄頁面的預設欄位已預先設定。您可以視需要修改它們。

1. 存取左側浮動視窗上的&#x200B;**[!UICONTROL Form data]**&#x200B;區段。

1. 若要變更欄位型別，請從&#x200B;**[!UICONTROL HTML type of the field]**&#x200B;下拉式清單中選取值。

   ![](assets/lp_html-field-type.png)

   >[!NOTE]
   >
   >如需在登入頁面中使用核取方塊型別的詳細資訊，請參閱[更新多個服務訂閱](#multiple-subscriptions)和[合約核取方塊](#agreement-checkbox)區段。

1. 如果您選取的欄位型別與目前在&#x200B;**[!UICONTROL Field]**&#x200B;區域中選取的資料庫欄位不相容，則會顯示警告訊息。 若要取得最佳對應，請選取適當的值。

   ![](assets/lp_field-type-warning.png)

1. 使用&#x200B;**[!UICONTROL Field]**&#x200B;區域選取要連結至表單欄位的資料庫欄位。

   ![](assets/lp_select-database-field.png)

   >[!NOTE]
   >
   >登入頁面只能對應至&#x200B;**[!UICONTROL Profiles]**&#x200B;或&#x200B;**[!UICONTROL Service]**&#x200B;資源。

   在此範例中，將登入頁面的&#x200B;**Name**&#x200B;欄位對應至&#x200B;**[!UICONTROL Profiles]**&#x200B;資源的&#x200B;**[!UICONTROL Last name]**&#x200B;欄位。

   ![](assets/lp_database-field-example.png)

1. 視需要核取 **[!UICONTROL Mandatory]** 選項。在此情況下，只有在使用者已填入此欄位時，才能提交登入頁面。

   ![](assets/lp_mandatory-option.png)

   如果未填入必填欄位，當使用者提交頁面時會顯示錯誤訊息。

1. 按一下&#x200B;**[!UICONTROL Confirm]**&#x200B;以儲存變更。

<!--If you choose a mandatory **[!UICONTROL Checkbox]**, make sure that it is of **[!UICONTROL Field]** type.-->

## 資料儲存與調解{#data-storage-and-reconciliation}

資料調和參數可讓您定義在使用者提交登錄頁面中輸入的資料後，如何加以管理。

操作步驟：

1. 編輯透過登錄頁面控制面板中 ![](assets/edit_darkgrey-24px.png) 圖示存取的登錄頁面屬性，並顯示 **[!UICONTROL Job]** 參數。

   ![](assets/lp_parameters_job.png)

1. 選取&#x200B;**[!UICONTROL Reconciliation key]**：此資料庫欄位是用來判斷訪客是否有已在Adobe Campaign資料庫中知道的設定檔。 例如電子郵件、名字、姓氏等。 調解金鑰可讓您根據下面定義的&#x200B;**[!UICONTROL Update strategy]**&#x200B;引數更新或建立設定檔。

1. 定義 **[!UICONTROL Form parameter mapping]**：此部分允許您對應登錄頁面欄位參數以及調解金鑰中使用的參數。

1. 選取&#x200B;**[!UICONTROL Update strategy]**：如果調解金鑰復原現有的資料庫設定檔，您可以選擇使用表單中輸入的資料來更新此設定檔，或者改為阻止此更新。

   ![](assets/lp_parameters_update-strategy.png)

## 多項服務訂閱 {#multiple-subscriptions}

您可以在單一登陸頁面上使用數個核取方塊，讓使用者訂閱或取消訂閱多項服務。

要執行此操作，請遵循下列步驟：

1. 設計登入頁面時：

   * 選取區塊，並從&#x200B;**[!UICONTROL Form data]**&#x200B;區段中選擇&#x200B;**[!UICONTROL Checkbox]**&#x200B;做為欄位型別。

     ![](assets/lp_field-type-checkbox.png)

   * 如果您熟悉HTML，也可以使用&#x200B;**[!UICONTROL Show source]**&#x200B;按鈕手動插入核取方塊。

     ![](assets/lp_show_source.png)

     這可讓您在頁面上方便的位置插入核取方塊。

     ![](assets/lp_manual-checkbox.png)

1. 確保在內容中選取核取方塊。 **[!UICONTROL Type]**&#x200B;下拉式清單會顯示在左側浮動視窗的&#x200B;**[!UICONTROL Form data]**&#x200B;區段中。 從清單中選取&#x200B;**[!UICONTROL Service and subscription]**。

   ![](assets/lp_service-and-subscription.png)

1. 從&#x200B;**[!UICONTROL Behavior]**&#x200B;下拉式清單中選擇選項。

   ![](assets/lp_checkbox-behavior.png)

1. 從對應的清單中選取[服務](../../audiences/using/creating-a-service.md)。

   ![](assets/lp_checkbox-service.png)

1. 請確定未核取&#x200B;**[!UICONTROL Mandatory]**&#x200B;選項。 否則，您的使用者將沒有選擇。

   ![](assets/lp_uncheck-mandatory.png)

1. 若要新增更多核取方塊，讓使用者訂閱其他服務，請視需要重複上述步驟。

   ![](assets/lp_multiple-checkboxes.png)

發佈登入頁面後，使用者可以從同一頁面選取多個核取方塊以訂閱數份電子報。

## 合約核取方塊 {#agreement-checkbox}

您可以新增核取方塊，設定檔在提交登入頁面之前必須先進行檢查。

例如，這可讓您在使用者提交表單前，要求使用者同意隱私權原則，或讓使用者接受您的條款與條件。

>[!IMPORTANT]
>
>選取此核取方塊對您的使用者是強制性的。 如果未選取，他們將無法提交登入頁面。

若要插入並設定此核取方塊，請執行下列動作：

1. 設計登入頁面時：

   * 選取區塊，並從&#x200B;**[!UICONTROL Form data]**&#x200B;區段中選擇&#x200B;**[!UICONTROL Checkbox]**&#x200B;做為欄位型別。

     ![](assets/lp_field-type-checkbox.png)

   * 如果您熟悉HTML，也可以使用&#x200B;**[!UICONTROL Show source]**&#x200B;按鈕手動插入核取方塊。

     ![](assets/lp_show_source.png)

     <!--Manually insert a checkbox, such as in the example below:

      <!--Click **[!UICONTROL Hide source]**.-->

1. 確定已選取核取方塊。

   ![](assets/lp_select_checkbox.png)

1. **[!UICONTROL Type]**&#x200B;下拉式清單會顯示在左側浮動視窗的&#x200B;**[!UICONTROL Form data]**&#x200B;區段中。 從清單中選取&#x200B;**[!UICONTROL Agreement]**。

   ![](assets/lp_form_data_drop-down.png)

   >[!NOTE]
   >
   >**[!UICONTROL Agreement]**&#x200B;專案未對應至Campaign資料庫的欄位。

1. 按一下&#x200B;**[!UICONTROL Form data]**&#x200B;旁的![](assets/lp-properties-icon.png)圖示以存取核取方塊進階屬性。

1. 您可以視需要編輯訊息。

   ![](assets/lp_agreement_message.png)

   如果使用者在提交表單前未選取核取方塊，此文字將顯示為警告。

   >[!NOTE]
   >
   >依預設，此動作是強制性的，無法變更。

1. 按一下&#x200B;**[!UICONTROL Confirm]**。

現在，每次顯示登入頁面時，使用者必須先選取此核取方塊，才能提交表單。 否則，將顯示警告，在啟用核取方塊之前，使用者將無法提交表單。