---
solution: Campaign Standard
product: campaign
title: '"步驟 3：驗證擴充"'
description: 瞭解如何使用Rest API存取擴充欄位。
audience: developing
content-type: reference
topic-tags: use-case--extending-the-api
feature: Data Model
role: Developer
level: Experienced
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '63'
ht-degree: 12%

---


# 步驟 3：驗證擴充{#step-verify-the-extension}

1. 對Profiles &amp; Services Extension API的中繼資料執行GET作業，以檢查新增至Profiles自訂資源的欄位是否現在可用。

   ```
   GET profileAndServicesExt/resourceType/profile
   ```

1. 它返回：

   ![](assets/extendpandsapiview.png)

   現在，此欄位可供進一步開發與整合。

