---
title: 管理 CCPA 選擇退出
description: 了解如何使用API管理CCPA選擇退出
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: bfc52511-f66f-4948-a939-d0d77e8ef03c
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 4%

---

# 管理 CCPA 選擇退出 {#managing-ccpa-optout}

可使用&#x200B;**ccpaOptOut**&#x200B;設定檔屬性和「true」或「false」值來監控及管理設定檔的CCPA選擇退出狀態：

`"ccpaOptOut": <value>`

* **true**:禁止銷售個人資訊。
* **false**:授權銷售個人資訊。

>[!CAUTION]
>
>「CCPA選擇退出」屬性僅從19.4版開始可用。對於19.3環境，您需要擴充設定檔資源並新增布林值欄位。 此欄位將會以所選標籤新增至API。 建議您使用「選擇退出CCPA」。
>
>如需詳細資訊，請參閱[管理隱私權要求檔案](../../start/using/privacy-requests.md#sale-of-personal-information-ccpa)。

<br/>

***範例要求***

* 擷取設定檔CCPA選擇退出狀態的GET請求範例。

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profilesAndServices/profile/<PKEY> \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>' \
   -H 'Content-Type: application/json;charset=utf-8'
   ```

   回應GET要求。

   ```
   {
   "PKey": "<PKEY>",
     "ccpaOptOut": false,
     "firstName": "John",
     "lastName": "Doe",
   ...
   }
   ```

* 標示CCPA選擇退出設定檔的POST請求範例。

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

   回應GET要求。

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

* 更新CCPA選擇退出設定檔的PATCH請求範例。

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

   回應GET要求。

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
