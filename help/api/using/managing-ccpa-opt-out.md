---
solution: Campaign Standard
product: campaign
title: 管理 CCPA 選擇退出
description: 瞭解如何使用API管理CCPA選擇退出
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: 資料工程師
level: 經驗豐富
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '152'
ht-degree: 4%

---


# 管理 CCPA 選擇退出 {#managing-ccpa-optout}

使用&#x200B;**ccpaOptOut**&#x200B;描述檔屬性和「true」或「false」值，可監控和管理描述檔的CCPA退出狀態：

`"ccpaOptOut": <value>`

* **true**:禁止銷售個人資訊。
* **false**:授權銷售個人資訊。

>[!CAUTION]
>
>「CCPA選擇退出」屬性僅從19.4開始提供。對於19.3環境，您需要擴展Profiles資源並添加布爾欄位。 此欄位將會新增至具有所選標籤的API。 我們建議您使用「退出CCPA」。
>
>有關詳細資訊，請參閱[管理隱私請求文檔](../../start/using/privacy-requests.md#sale-of-personal-information-ccpa)。

<br/>

***請求範例***

* 擷取描述檔CCPA退出狀態的範例GET請求。

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profilesAndServices/profile/<PKEY> \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>' \
   -H 'Content-Type: application/json;charset=utf-8'
   ```

   回應GET請求。

   ```
   {
   "PKey": "<PKEY>",
     "ccpaOptOut": false,
     "firstName": "John",
     "lastName": "Doe",
   ...
   }
   ```

* 標示CCPA選擇退出描述檔的POST請求範例。

   ```
   -X POST https://mc.adobe.io/<ORGANIZATION>/campaign/profilesAndServices/profile/ \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>' \
   -H 'Content-Type: application/json;charset=utf-8'
   -i
   -d {
   -d  "firstName": "John",
   -d  "lastName": "Doe",
   -d  "email": "jdoe@mail.com",
   -d  "ccpaOptOut": true
   -d }'
   ```

   回應GET請求。

   ```
   {
       ...
       "email": "john.doe@mail.com",
       "firstName": "John",
       "lastName": "Doe",
       "ccpaOptOut": true,
       ...
   }
   ```

* 更新CCPA選擇退出描述檔的PATCH請求範例。

   ```
   -X PATCH https://mc.adobe.io/<ORGANIZATION>/campaign/profilesAndServices/profile/<PKEY> \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>' \
   -H 'Content-Type: application/json;charset=utf-8'
   -i
   -d {
   -d  "ccpaOptOut": true
   -d }'
   ```

   回應GET請求。

   ```
   {
       ...
       "email": "john.doe@mail.com",
       "firstName": "John",
       "lastName": "Doe",
       "ccpaOptOut": true,
       ...
   }
   ```
