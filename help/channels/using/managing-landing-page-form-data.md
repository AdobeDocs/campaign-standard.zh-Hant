---
solution: Campaign Standard
product: campaign
title: 管理登錄頁面表單資料
description: 瞭解如何管理登錄頁面表單資料。
audience: channels
content-type: reference
topic-tags: landing-pages
context-tags: landingPage,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '394'
ht-degree: 100%

---


# 管理登錄頁面表單資料{#managing-landing-page-form-data}

## 變更登錄頁面表單資料屬性{#changing-a-landing-page-form-data-properties}

您可以將資料庫欄位連結到輸入區域、單選按鈕或核取方塊類型區塊。若要這麼做，請選取區塊並在浮動視窗中輸入 **[!UICONTROL Form data]**。

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
