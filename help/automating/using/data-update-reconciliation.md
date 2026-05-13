---
title: 使用協調功能更新資料
description: 下列範例會示範一個工作流程，其會從包含新客戶之匯入檔案直接建立輪廓客群。
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: reconciliation,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: cfca6202-791d-4baf-b5ed-677d2480cf06
TQID: https://experienceleague.adobe.com/cEXfESw1LZcrQVlLsgrlDB8J2aGz4zCoSUrIAshECo0
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 128
ht-degree: 49%

---

# 使用協調功能更新資料 {#data-update-reconciliation}

下列範例會示範一個工作流程，其會從包含新客戶之匯入檔案直接建立輪廓客群。 它由下列活動組成：

![](assets/identification_example2.png)

* [載入檔案](../../automating/using/load-file.md)活動，可載入並偵測要匯入之檔案的資料。 匯入的檔案包含下列資料：

  ```
  lastname;firstname;email;dateofbirth
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

* [調解](../../automating/using/reconciliation.md)活動，可將載入檔案的每個欄連結到設定檔維度欄。 無法識別的檔案記錄（遺失資料、不相容的資料型別等） 會遭到忽略，以保留最終對象資料的完整性。

  ![](assets/identification_example1.png)

* [儲存對象](../../automating/using/save-audience.md)活動，可儲存設定檔的對象。

  ![](assets/identification_example3.png)
