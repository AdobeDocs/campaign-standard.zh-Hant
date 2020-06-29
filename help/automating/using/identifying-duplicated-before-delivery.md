---
title: 在傳送前識別重複項目
description: 以下示例說明了一個重複資料消除，它允許您在發送電子郵件之前排除目標的重複項。 這表示您不必多次傳送通訊至相同的描述檔。
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
source-wordcount: '285'
ht-degree: 0%

---


# 在傳送前識別重複項目 {#identifying-duplicates-before-a-delivery}

以下示例說明了一個重複資料消除，它允許您在發送電子郵件之前排除目標的重複項。 這表示您不必多次傳送通訊至相同的描述檔。

工作流由以下幾部分組成：

![](assets/deduplication_example_workflow.png)

* 一 [個查詢](../../automating/using/query.md) ，允許您定義電子郵件的目標。 在此，工作流將目標鎖定在客戶端資料庫中已存留超過一年的18到25歲的所有配置檔案。

   ![](assets/deduplication_example_query.png)

* 重複 [資料消除](../../automating/using/deduplication.md) (Deduplication)活動，允許您識別來自前一查詢的重複項。 在此示例中，每個復本僅保存一條記錄。 重複項目是使用電子郵件地址識別。 這表示每個要存在於定位中的電子郵件地址只能傳送一次電子郵件傳送。

   選擇的重複資料消除方 **[!UICONTROL Non-empty value]**&#x200B;法。 這可讓您確保在記錄中，若有重複項目，優先順序會指定給已提供 **名字** 。 如果在電子郵件內容的個人化欄位中使用名字，這會使其更連貫。

   此外，還新增了額外的轉場功能，以保留復本並列出復本。

   ![](assets/deduplication_example_dedup.png)

* 在重 [復資料消除](../../automating/using/email-delivery.md) (DTF)的主要出站過渡之後發送電子郵件。
* 在重複 [資料消除的額外過渡](../../automating/using/save-audience.md) 後放置的「保存對象」活動，以便將重複資料保存在 **Duplicates對象中** 。 此對象可重複使用，以直接將其成員排除在每封電子郵件的傳送之外。
