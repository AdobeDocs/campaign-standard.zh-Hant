---
solution: Campaign Standard
product: campaign
title: 從匯入的檔案中重複刪除資料
description: 此範例說明如何先從匯入的檔案重複刪除資料，然後再將資料載入資料庫中。
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: dedup,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '328'
ht-degree: 89%

---


# 從匯入的檔案中重複刪除資料 {#deduplicating-the-data-from-an-imported-file}

此範例說明如何先從匯入的檔案重複刪除資料，然後再將資料載入資料庫中。此程序可改善載入到資料庫中的資料品質。

工作流程由以下部分組成：

![](assets/deduplication_example2_workflow.png)

* 使用[Load file](../../automating/using/load-file.md)活動導入包含配置檔案清單的檔案。 在此範例中，匯入的檔案使用 .csv 格式並包含 10 個設定檔：

   ```
   lastname;firstname;dateofbirth;email
   Smith;Hayden;23/05/1989;hayden.smith@example.com
   Mars;Daniel;17/11/1987;dannymars@example.com
   Smith;Clara;08/02/1989;hayden.smith@example.com
   Durance;Allison;15/12/1978;allison.durance@example.com
   Lucassen;Jody;28/03/1988;jody.lucassen@example.com
   Binder;Tom;19/01/1982;tombinder@example.com
   Binder;Tommy;19/01/1915;tombinder@example.com
   Connor;Jade;10/10/1979;connor.jade@example.com
   Mack;Clarke;02/03/1985;clarke.mack@example.com
   Ross;Timothy;04/07/1986;timross@example.com
   ```

   此檔案也可作為範例檔案，以偵測並定義欄的格式。在 **[!UICONTROL Column definition]** 索引標籤中，確定匯入檔案的每一列均已正確設定。

   ![](assets/deduplication_example2_fileloading.png)

* A [重複資料消除](../../automating/using/deduplication.md)活動。 會在匯入檔案之後以及將資料插入資料庫之前直接執行重複刪除資料。因此，應以來自 **[!UICONTROL Load file]** 活動的 **[!UICONTROL Temporary resource]** 為基礎。

   在此範例中，我們希望為檔案包含的每個獨特電子郵件保留單一項目。因此，會在暫時資源的&#x200B;**電子郵件**&#x200B;列上執行重複身份識別。但是有兩個電子郵件地址在檔案中出現兩次。因此，會將這兩行視為重複項目。

   ![](assets/deduplication_example2_dedup.png)

* [更新資料](../../automating/using/update-data.md)活動允許您將重複資料消除過程中保留的資料插入到資料庫中。 只有當更新資料時，才會將匯入的資料識別為屬於該設定檔維度。

   我們在此希望 **[!UICONTROL Insert only]** 資料庫尚未存在的設定檔。我們希望使用來自&#x200B;**Profile**&#x200B;維度（與調解金鑰相同）之檔案的電子郵件欄及電子郵件欄位，來執行這項作業。

   ![](assets/deduplication_example2_writer1.png)

   指定要從您希望插入資料的檔案欄以及 **[!UICONTROL Fields to update]** 索引標籤之資料庫欄位之間的對應。

   ![](assets/deduplication_example2_writer2.png)

然後開始進行工作流程。之後，會將從重複資料刪除程序期間儲存的記錄新增到資料庫中的設定檔。
