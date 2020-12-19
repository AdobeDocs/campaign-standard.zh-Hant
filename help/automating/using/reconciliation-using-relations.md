---
solution: Campaign Standard
product: campaign
title: 使用關係進行資料協調
description: 下列範例會示範使用檔案中的購買資料更新資料庫的工作流程。
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: reconciliation,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 86%

---


# 使用關係進行資料協調 {#reconciliation-relations}

下列範例會示範使用檔案中的購買資料更新資料庫的工作流程。採購資料包含參考其他維度的資料元素，例如客戶電子郵件和產品代碼。

>[!NOTE]
>
>依預設，Adobe Campaign 資料庫中沒有此範例使用的&#x200B;**交易**&#x200B;及&#x200B;**產品**&#x200B;資源。因此，會預先使用[自訂資源](../../developing/using/data-model-concepts.md)函式建立這些資源。與已匯入檔案的電子郵件地址以及產品相對應的設定檔，會預先載入資料庫。

工作流程由下列活動組成：

![](assets/reconciliation_example1.png)

* [載入檔案](../../automating/using/load-file.md)活動，可載入並偵測要匯入的檔案資料。 匯入的檔案包含下列資料：

   * 交易日期
   * 客戶電子郵件地址
   * 購買產品的代碼

   ```
   date;client;product
   2015-05-19 09:00:00;mail1@email.com;ZZ1
   2015-05-19 09:01:00;mail2@email.com;ZZ2
   2015-05-19 09:01:01;mail3@email.com;ZZ2
   2015-05-19 09:01:02;mail4@email.com;ZZ2
   2015-05-19 09:02:00;mail5@email.com;ZZ3
   2015-05-19 09:03:00;mail6@email.com;ZZ4
   2015-05-19 09:04:00;mail7@email.com;ZZ5
   2015-05-19 09:05:00;mail8@email.com;ZZ7
   2015-05-19 09:06:00;mail9@email.com;ZZ6
   ```

* [協調](../../automating/using/reconciliation.md)活動，用於將購買資料綁定到資料庫配置檔案以及產品。 因此，必須定義檔案資料與設定檔表格及產品表格之間的關係。會在活動 **[!UICONTROL Relations]** 索引標籤中執行此設定：

   * 與&#x200B;**設定檔**&#x200B;的關係：檔案的&#x200B;**客戶**&#x200B;欄已連結至&#x200B;**設定檔**&#x200B;維度的&#x200B;**電子郵件**&#x200B;欄位。
   * 與&#x200B;**產品**&#x200B;的關係：檔案的&#x200B;**產品**&#x200B;欄已連結至&#x200B;**設定檔**&#x200B;維度的 **productCode** 欄位。

   會將欄新增至入站資料，以參考連結維度的外部索引鍵。

   ![](assets/reconciliation_example3.png)

* [Update data](../../automating/using/update-data.md)活動允許您定義要使用導入資料進行更新的資料庫欄位。 由於已將資料識別為屬於前一個活動的&#x200B;**交易**&#x200B;維度，因此，您可以在此處使用 **[!UICONTROL Directly using the targeting dimension]** 識別選項。

   使用會自動偵測要更新欄位的選項，會將前一個活動（至設定檔及產品）中設定的連結新增到 **[!UICONTROL Fields to update]** 清單。您也必須確定與交易日期相對應的欄位已正確新增至此清單。

   ![](assets/reconciliation_example5.png)

   ![](assets/reconciliation_example4.png)
