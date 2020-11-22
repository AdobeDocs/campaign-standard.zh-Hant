---
solution: Campaign Standard
product: campaign
title: 排序
description: 進一步瞭解如何執行排序作業
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 11%

---


# 排序

排序可依遞增或遞減順序進行。 若要這麼做，請使 **用%20desc** 或 **** %20asc參數來處理您的請求。

要知道欄位是否可以排序，請將「可排序」參數檢入資源元資料中。 如需詳細資訊，請參閱[本章節](../../api/using/metadata-mechanism.md)。

<br/>

***請求範例***

* GET要求範例，以依字母順序在資料庫中擷取電子郵件。

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email/email?_order=email \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```

   回應請求。

   ```
   {
   "content": [
       "adam@email.com",
       "allison.durance@example.com",
       "amy.dakota@mail.com",
       "andrea.johnson@mail.com",
       ...
   ]
   ...
   }
   ```

* GET要求範例，以遞減字母順序擷取資料庫中的電子郵件。

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email?_order=email%20desc \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```

   回應請求。

   ```
   {
   "content": [
       "tombinder@example.com",
       "tombinder@example.com",
       "timross@example.com",
       "john.smith@example.com",
       ...
   ]
   }
   ```
