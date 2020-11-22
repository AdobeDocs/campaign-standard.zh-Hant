---
solution: Campaign Standard
product: campaign
title: 使用資料庫調解檔案對象
description: 此範例說明如何使用「讀取對象」活動協調直接從檔案匯入建立的對象。
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: readAudience,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 87%

---


# 使用資料庫調解檔案對象 {#example--reconcile-a-file-audience-with-the-database}

此範例說明如何使用 **[!UICONTROL Read audience]** 活動調解直接從檔案匯入建立的對象。

執行檔案匯入時，您可以直接將其內容儲存在對象中。此對象是檔案對象，其資料未連結至任何資料庫資源。

匯入工作流程的設計如下：

![](assets/readaudience_activity_example3.png)

* [載入檔案](../../automating/using/load-file.md)活動會上傳包含從外部工具擷取之設定檔資料的檔案。

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

* 「儲 [存對象](../../automating/using/save-audience.md) 」活動會將傳入的資料儲存為對象。由於資料尚未調解，因此對象是檔案對象，其資料尚未被識別為設定檔資料。

調解工作流程的設計如下：

![](assets/readaudience_activity_example2.png)

* A [Read audience](../../automating/using/read-audience.md) activity uploads the File audience created in the import workflow. 尚未與 Adobe Campaign 資料庫調解對象資料。
* [調解](../../automating/using/reconciliation.md)活動會透過 **[!UICONTROL Identification]** 索引標籤，將傳入資料識別為設定檔。例如，使用&#x200B;**電子郵件**&#x200B;欄位作為調解標準。
* [更新資料](../../automating/using/update-data.md)活動將插入和更新包含傳入資料之資料庫的設定檔資源。由於已將資料識別為設定檔，您可以選取 **[!UICONTROL Directly using the targeting dimension]** 選項，然後再選取活動之 **[!UICONTROL Identification]** 索引標籤中的 **[!UICONTROL Profiles]**。之後，您只需要在隨後出現的索引標籤中新增需要更新的欄位清單即可。
