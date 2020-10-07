---
title: 使用外部資料更新資料庫
description: 此使用案例說明如何使用從檔案中復原的資料新增或更新Adobe Campaign資料庫的設定檔。
page-status-flag: never-activated
uuid: 1dc55db5-affd-4688-b673-adfb8c1338b5
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: 4db83c95-4b75-4a16-8dbf-bd8940431fa9
context-tags: writer,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 使用外部資料更新資料庫 {#update-database-file}

The following example shows the configuration of an **[!UICONTROL Update data]** activity following a **[!UICONTROL Load file]** activity. 此工作流程的目的在於，使用從檔案復原的資料，將設定檔新增或更新至 Adobe Campaign 資料庫。

在此示例中，使用的協調密鑰是電 **子郵件地址**。 載入「載入檔案 [」活動中的檔案是](../../automating/using/load-file.md)**** .txt格式檔案，包含下列範例資料：

```
lastname;firstname;email;birthdate
jackman;megan;megan.jackman@testmail.com;07/08/1975
phillips;edward;phillips@testmail.com;09/03/1986
weaver;justin;justin_w@testmail.com;11/15/1990
martin;babeth;babeth_martin@testmail.net;11/25/1964
reese;richard;rreese@testmail.com;02/08/1987
cage;nathalie;cage.nathalie227@testmail.com;07/03/1989
xiuxiu;andrea;andrea.xiuxiu@testmail.com;09/12/1992
grimes;daryl;daryl_890@testmail.com;12/06/1979
tycoon;tyreese;tyreese_t@testmail.net;10/08/1971
```

The [Update data](../../automating/using/update-data.md) activity is configured as follows:

![](assets/deduplication_example2_writer1.png)

![](assets/deduplication_example2_writer2.png)
