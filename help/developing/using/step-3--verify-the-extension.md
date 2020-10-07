---
title: '"步驟 3：驗證擴充"'
description: 瞭解如何使用Rest API存取擴充欄位。
page-status-flag: never-activated
uuid: 35ba89a5-a354-466f-91a0-50de111a2e00
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: use-case--extending-the-api
discoiquuid: 21bad242-5921-445c-8df9-3d57dbe35197
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 步驟 3：驗證擴充{#step-verify-the-extension}

1. 對Profiles &amp; Services Extension API的中繼資料執行GET作業，以檢查新增至Profiles自訂資源的欄位是否現在可用。

   ```
   GET profileAndServicesExt/resourceType/profile
   ```

1. 它返回：

   ![](assets/extendpandsapiview.png)

   現在，此欄位可供進一步開發與整合。

