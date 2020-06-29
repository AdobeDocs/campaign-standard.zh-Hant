---
title: 協調檔案對象與資料庫
description: 此範例說明如何使用「讀取對象」活動協調直接從檔案匯入建立的對象。
page-status-flag: never-activated
uuid: 58c54e71-f4a7-4ae9-80a3-33c379ab1db9
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 674684e5-8830-4d2f-ba97-59ed4ba7422f
context-tags: readAudience,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7ffa48365875883a98904d6b344ac005afe26e18
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 0%

---


# 協調檔案對象與資料庫 {#example--reconcile-a-file-audience-with-the-database}

此範例說明如何使用活 **[!UICONTROL Read audience]** 動協調直接從檔案匯入建立的對象。

執行檔案匯入時，您可以直接將其內容儲存在觀眾中。 此對象是檔案對象，其資料未連結至任何資料庫資源。

匯入工作流程的設計如下：

![](assets/readaudience_activity_example3.png)

* 「載 [入檔案](../../automating/using/load-file.md) 」活動會上傳包含從外部工具擷取之描述檔資料的檔案。

   例如：

   ```
   lastname;firstname;birthdate;email;crmID
   Smith;Hayden;23/05/1989;hayden.smith@example.com;124365
   Mars;Daniel;17/11/1987;dannymars@example.com;123545
   Smith;Clara;08/02/1989;hayden.smith@example.com;124567
   Durance;Allison;15/12/1978;allison.durance@example.com;120987
   Lucassen;Jody;28/03/1988;jody.lucassen@example.com;127634
   Binder;Tom;19/01/1982;tombinder@example.com;128653
   Binder;Tommy;19/01/1915;tombinder@example.com;134576
   Connor;Jade;10/10/1979;connor.jade@example.com;132452
   Mack;Clarke;02/03/1985;clarke.mack@example.com;149876
   Ross;Timothy;04/07/1986;timross@example.com;157643
   ```

* 「儲 [存觀眾](../../automating/using/save-audience.md) 」活動會將傳入的資料儲存為觀眾。 由於資料尚未協調，因此對象是檔案對象，其資料尚未被識別為描述檔資料。

協調工作流程的設計如下：

![](assets/readaudience_activity_example2.png)

* 「讀 [取對象](../../automating/using/read-audience.md) 」活動會上傳在匯入工作流程中建立的「檔案對象」。 觀眾資料尚未與Adobe Campaign資料庫協調。
* 「協 [調](../../automating/using/reconciliation.md) 」活動通過其頁籤將傳入資料標識為配 **[!UICONTROL Identification]** 置檔案。 例如，使用電子郵件 **欄位** 作為協調標準。
* 「更 [新資料](../../automating/using/update-data.md) 」活動將插入和更新帶有傳入資料的資料庫的配置檔案資源。 由於資料已標識為配置檔案，您可以選 **[!UICONTROL Directly using the targeting dimension]** 擇選項並 **[!UICONTROL Profiles]** 在活動 **[!UICONTROL Identification]** 的頁籤中選擇。 然後，您只需要在標籤中新增需要更新的欄位清單。
