---
title: 步驟 3：驗證擴充
description: 瞭解如何使用Rest API存取擴充欄位。
audience: developing
content-type: reference
topic-tags: use-case-extending-the-api
feature: Data Model
role: Developer
level: Experienced
exl-id: 34cb416c-ee3d-4b7c-a75b-640432db320d
TQID: https://experienceleague.adobe.com/XadrenC5de4Xh6MSCUiQUc-qXaTKr-xpG-7znnlWeeQ
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: d5ef99fa-df0c-4153-bf94-105ad0724167
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 61
ht-degree: 16%

---

# 步驟 3：驗證擴充{#step-verify-the-extension}

1. 在Profiles &amp; Services擴充功能API的中繼資料上進行GET作業，以檢查在Profiles自訂資源中新增的欄位現在是否可用。

   ```
   GET profileAndServicesExt/resourceType/profile
   ```

1. 它會傳回：

   ![](assets/extendpandsapiview.png)

   此欄位現在可用於進一步開發和整合。
