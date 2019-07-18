---
title: 「步驟3：驗證延伸功能」
seo-title: 「步驟3：驗證延伸功能」
description: 「步驟3：驗證延伸功能」
seo-description: 瞭解如何使用REST API存取延伸欄位。
page-status-flag: 從未啓動
uuid: 35ba89a5-a354-466f-91a0-50de111 a2 e00
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 開發
content-type: reference
topic-tags: use-case—extending-the-api
discoiquuid: 21錯誤242-5921-445c-8df9-3d57dobe35197
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Step 3: Verify the extension{#step-verify-the-extension}

1. 對Profiles&amp; Services Extension API的中繼資料進行GET操作，以檢查是否已在Profiles自訂資源中新增欄位。

   ```
   GET profileAndServicesExt/resourceType/profile
   ```

1. 它會傳回：

   ![](assets/extendpandsapiview.png)

   現在此欄位可供進一步開發和整合。

