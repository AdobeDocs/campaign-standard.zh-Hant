---
title: 從導入的檔案中消除重複資料
description: 此示例說明如何在將資料載入到資料庫中之前從導入的檔案中消除重複資料。
page-status-flag: never-activated
uuid: 11a22a9c-3bfe-4953-8a52-2f4e93c128fb
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: e7a5e1e7-4680-46c7-98b8-0a47bb7be2b8
context-tags: dedup,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7ffa48365875883a98904d6b344ac005afe26e18
workflow-type: tm+mt
source-wordcount: '328'
ht-degree: 0%

---


# 從導入的檔案中消除重複資料 {#deduplicating-the-data-from-an-imported-file}

此示例說明如何在將資料載入到資料庫中之前從導入的檔案中消除重複資料。 此過程提高了在資料庫中載入的資料的質量。

工作流由以下幾部分組成：

![](assets/deduplication_example2_workflow.png)

* 包含配置檔案清單的檔案使用「載入檔案」( [Load file](../../automating/using/load-file.md) )活動導入。 在此範例中，匯入的檔案為。csv格式，並包含10個描述檔：

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

   此檔案也可用作範例檔案，以偵測並定義欄的格式。 在頁籤 **[!UICONTROL Column definition]** 中，確保已導入檔案的每一列都配置正確。

   ![](assets/deduplication_example2_fileloading.png)

* 重複數 [據消除](../../automating/using/deduplication.md) 。 重複資料消除直接在導入檔案後和將資料插入資料庫之前執行。 因此，它應以活動 **[!UICONTROL Temporary resource]** 為基礎 **[!UICONTROL Load file]** 。

   在此範例中，我們希望每個檔案中包含的唯一電子郵件地址保留一個項目。 因此，在臨時資源的電子郵 **件列** 上執行重複標識。 不過，檔案中會出現兩個電子郵件地址。 因此，兩行將視為重複行。

   ![](assets/deduplication_example2_dedup.png)

* 「更 [新資料](../../automating/using/update-data.md) 」活動允許您將重複資料消除過程中保留的資料插入到資料庫中。 只有在更新資料時，匯入的資料才會被識別為屬於描述檔維度。

   在此，我們希望 **[!UICONTROL Insert only]** 看到資料庫中不存在的配置檔案。 我們將使用檔案的電子郵件欄和「描述檔」維度的電子郵件欄位作為 **協調金鑰** ，來執行此動作。

   ![](assets/deduplication_example2_writer1.png)

   指定要從中插入資料的檔案列與頁籤中資料庫欄位之間的映 **[!UICONTROL Fields to update]** 射。

   ![](assets/deduplication_example2_writer2.png)

然後啟動工作流程。 然後，從重複資料消除過程中保存的記錄將添加到資料庫中的配置檔案中。
