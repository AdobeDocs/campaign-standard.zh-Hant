---
title: '"步驟 3：驗證擴充"'
description: 瞭解如何使用Rest API存取擴充欄位。
page-status-flag: 從未激活
uuid: 35ba89a5-a354-466f-91a0-50de11a2e00
contentOwner: 紹維亞
products: SG_CAMPAIGN/STANDARD
audience: 開發
content-type: 參考
topic-tags: use-case-extending-the-api
discoiquuid: 21bad242-5921-445c-8df9-3d57dbe35197
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 步驟 3：驗證擴充{#step-verify-the-extension}

1. 對Profiles &amp; Services Extension API的中繼資料執行GET作業，以檢查新增至Profiles自訂資源的欄位是否現在可用。

   ```
   GET profileAndServicesExt/resourceType/profile
   ```

1. 它返回：

   ![](assets/extendpandsapiview.png)

   現在，此欄位可供進一步開發與整合。

