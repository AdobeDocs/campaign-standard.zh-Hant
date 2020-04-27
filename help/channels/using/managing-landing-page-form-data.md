---
title: 管理登錄頁面表單資料
description: 瞭解如何管理著陸頁面表單資料。
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
source-git-commit: 8c24e048c698f7ad699e83a753c114fcfd25f6a0

---


# 管理登錄頁面表單資料{#managing-landing-page-form-data}

## 變更著陸頁面表單資料屬性{#changing-a-landing-page-form-data-properties}

您可以將資料庫欄位連結到輸入區域、單選按鈕或複選框類型塊。 若要這麼做，請選取區塊並在浮動視窗 **[!UICONTROL Form data]** 中輸入。

![](assets/delivery_content_9.png)

* 欄位 **輸入區** ，可讓您選取要與表單欄位連結的資料庫欄位。
* 「必 **備** 」選項可讓您僅在使用者已填入欄位時授權頁面的提交。 如果未填入必填欄位，則會出現錯誤訊息。

## 對應表單欄位 {#mapping-form-fields}

輸入欄位可用來儲存或更新促銷活動資料庫中的資料。 為此，您需要將資料庫欄位與輸入區域、單選按鈕或複選框類型塊連結起來。 操作步驟：

1. 在著陸頁面中選取區塊。
1. 在浮動視 **[!UICONTROL Form data]** 窗中完成部件。

   ![](assets/editing_lp_content_4.png)

1. 選擇資料庫欄位以與選擇區域中的表單欄位 **[!UICONTROL Field]** 連結。 著陸頁面只能與描述檔 **對應**。

1. 視需要 **[!UICONTROL Mandatory]** 勾選選項。 只有當使用者已填妥此欄位時，才能提交頁面。 如果未完成必填欄位，當使用者驗證頁面時，將會顯示錯誤訊息。

1. 通過選擇（例如，或）選 **[!UICONTROL Text]**&#x200B;擇 **[!UICONTROL Number]**&#x200B;選 **[!UICONTROL Date]** 擇欄位 **[!UICONTROL HTML type of the field]** 類型。
如果您選擇必 **[!UICONTROL Checkbox]**&#x200B;備項目，請確定其類 **[!UICONTROL Field]** 型。

>[!NOTE]
>
>內建著陸頁面的預設欄位已預先設定。 您可以視需要修改它們。

## 資料儲存與協調{#data-storage-and-reconciliation}

資料協調參數可讓您定義在使用者提交登陸頁面中輸入的資料後，如何加以管理。

操作步驟：

1. 編輯透過著陸頁面控制面板中 ![](assets/edit_darkgrey-24px.png) 的圖示存取的著陸頁面屬性，並顯示 **[!UICONTROL Job]** 參數。

   ![](assets/lp_parameters_4.png)

1. 選擇 **[!UICONTROL Reconciliation key]**:這些資料庫欄位(例如：電子郵件、名字、姓氏)可用來判斷訪客是否有已在Adobe Campaign資料庫中知道的描述檔。 這允許您根據定義的更新策略參數更新或建立配置檔案。
1. 定義 **[!UICONTROL Form parameter mapping]**:此部分允許您映射著陸頁面欄位參數以及協調鍵中使用的參數。
1. 選擇 **[!UICONTROL Update strategy]**:如果協調鍵恢復了現有資料庫配置檔案，您可以選擇使用此配置檔案以表單中輸入的資料進行更新，或者改為阻止此更新。
