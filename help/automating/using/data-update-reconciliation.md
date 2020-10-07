---
title: 使用協調功能更新資料
description: 下列範例會示範一個工作流程，其會從包含新客戶之匯入檔案直接建立設定檔對象。
page-status-flag: never-activated
uuid: 7884db8c-1717-4724-be15-3b0b32ccc071
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: cb8c43f4-9cdd-4e85-99a4-004b36b336aa
context-tags: reconciliation,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 使用協調功能更新資料 {#data-update-reconciliation}

下列範例會示範一個工作流程，其會從包含新客戶之匯入檔案直接建立設定檔對象。它由下列活動組成：

![](assets/identification_example2.png)

* A [Load file](../../automating/using/load-file.md) activity, which loads and detects tshe data of the file to import. 匯入的檔案包含下列資料：

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

* A [Reconciliation](../../automating/using/reconciliation.md) activity, which links each column of the loaded file to a profile dimension column. 無法識別的檔案記錄（遺失資料、不相容的資料類型等）會遭到忽略，以保留最終對象資料的完整性。

   ![](assets/identification_example1.png)

* A [Save audience](../../automating/using/save-audience.md) activity, which saves the audience of profiles.

   ![](assets/identification_example3.png)
