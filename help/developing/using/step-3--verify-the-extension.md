---
title: "步驟 3：驗證擴充"
description: 瞭解如何使用Rest API存取擴充欄位。
audience: developing
content-type: reference
topic-tags: use-case--extending-the-api
feature: Data Model
role: Developer
level: Experienced
exl-id: 34cb416c-ee3d-4b7c-a75b-640432db320d
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '59'
ht-degree: 13%

---

# 步驟 3：驗證擴充{#step-verify-the-extension}

1. 對Profiles &amp; Services擴充功能API的中繼資料進行GET操作，以檢查在Profiles自訂資源中新增的欄位現在是否可用。

   ```
   GET profileAndServicesExt/resourceType/profile
   ```

1. 它會傳回：

   ![](assets/extendpandsapiview.png)

   此欄位現在可用於進一步開發和整合。
