---
title: 使用協調功能更新資料
description: 下列範例會示範一個工作流程，其會從包含新客戶之匯入檔案直接建立設定檔對象。
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: reconciliation,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: cfca6202-791d-4baf-b5ed-677d2480cf06
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '128'
ht-degree: 67%

---

# 使用協調功能更新資料 {#data-update-reconciliation}

下列範例會示範一個工作流程，其會從包含新客戶之匯入檔案直接建立設定檔對象。它由下列活動組成：

![](assets/identification_example2.png)

* A [載入檔案](../../automating/using/load-file.md) 活動，它載入並檢測要導入的檔案的資料。 匯入的檔案包含下列資料：

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

* A [協調](../../automating/using/reconciliation.md) 活動，它將載入檔案的每列連結到配置檔案維列。 無法識別的檔案記錄（遺失資料、不相容的資料類型等）會遭到忽略，以保留最終對象資料的完整性。

   ![](assets/identification_example1.png)

* A [保存受眾](../../automating/using/save-audience.md) 活動，可保存配置檔案的受眾。

   ![](assets/identification_example3.png)
