---
title: 使用協調功能更新資料
description: 下列範例示範從包含新用戶端的匯入檔案直接建立描述檔對象的工作流程。
page-status-flag: never-activated
uuid: 7884db8c-1717-4724-be15-3b0b32ccc071
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: cb8c43f4-9cdd-4e85-99a4-004b36b336aa
context-tags: reconciliation,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 175709a41607bb9d64da7fac77dd749fa84f7360
workflow-type: tm+mt
source-wordcount: '128'
ht-degree: 0%

---


# 使用協調功能更新資料 {#data-update-reconciliation}

下列範例示範從包含新用戶端的匯入檔案直接建立描述檔對象的工作流程。 它由以下活動組成：

![](assets/identification_example2.png)

* 載 [入檔案](../../automating/using/load-file.md) ，此活動會載入並偵測要匯入之檔案的資料。 匯入的檔案包含下列資料：

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

* 「 [協調](../../automating/using/reconciliation.md) 」活動，將載入檔案的每列連結到配置檔案維列。 無法識別的檔案記錄（遺失資料、不相容的資料類型等） 會被忽略，以保留最終觀眾資料的完整性。

   ![](assets/identification_example1.png)

* 「儲 [存觀眾](../../automating/using/save-audience.md) 」活動，可儲存設定檔的觀眾。

   ![](assets/identification_example3.png)
