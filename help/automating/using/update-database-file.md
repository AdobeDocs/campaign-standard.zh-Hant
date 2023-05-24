---
title: 使用外部資料更新資料庫
description: 此使用案例介紹如何使用從檔案恢復的資料向Adobe Campaign資料庫添加或更新配置檔案。
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: writer,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 2df7fbed-b979-4706-bd56-83f712cc3070
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '106'
ht-degree: 33%

---

# 使用外部資料更新資料庫 {#update-database-file}

以下示例顯示了 **[!UICONTROL Update data]** 活動 **[!UICONTROL Load file]** 的子菜單。 此工作流程的目的在於，使用從檔案復原的資料，將設定檔新增或更新至 Adobe Campaign 資料庫。

在本示例中，使用的協調鍵是 **電子郵件地址**。 載入到 [載入檔案](../../automating/using/load-file.md) 活動是 **.txt** 包含以下示例資料的格式檔案：

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

的 [更新資料](../../automating/using/update-data.md) 活動配置如下：

![](assets/deduplication_example2_writer1.png)

![](assets/deduplication_example2_writer2.png)
