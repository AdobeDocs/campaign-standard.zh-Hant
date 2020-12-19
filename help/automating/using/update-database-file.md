---
solution: Campaign Standard
product: campaign
title: 使用外部資料更新資料庫
description: 此使用案例說明如何使用從檔案中復原的資料新增或更新Adobe Campaign資料庫的設定檔。
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: writer,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '106'
ht-degree: 33%

---


# 使用外部資料更新資料庫 {#update-database-file}

以下示例顯示&#x200B;**[!UICONTROL Load file]**&#x200B;活動後的&#x200B;**[!UICONTROL Update data]**&#x200B;活動的配置。 此工作流程的目的在於，使用從檔案復原的資料，將設定檔新增或更新至 Adobe Campaign 資料庫。

在此示例中，使用的協調密鑰是&#x200B;**電子郵件地址**。 在[Load file](../../automating/using/load-file.md)活動中載入的檔案是包含以下示例資料的&#x200B;**.txt**&#x200B;格式檔案：

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

[Update data](../../automating/using/update-data.md)活動的配置如下：

![](assets/deduplication_example2_writer1.png)

![](assets/deduplication_example2_writer2.png)
