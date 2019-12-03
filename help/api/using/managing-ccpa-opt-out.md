---
title: 管理CCPA選擇退出
description: 瞭解如何使用API管理CCPA選擇退出
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: aee0e0437cbfe578cb2f715a2433099c79dd1748

---


# 管理CCPA選擇退出 {#managing-ccpa-optout}

可使用 **** ccpaOptOut配置檔案屬性和「true」或「false」值來監視和管理配置檔案的CCPA退出狀態：

`"ccpaOptOut": <value>`

* **true**: 禁止銷售個人資訊。
* **false**:授權銷售個人資訊。

>[!CAUTION]
>
>「CCPA選擇退出」屬性僅從19.4開始提供。對於19.3環境，您需要擴展Profiles資源並添加布爾欄位。 此欄位將會新增至具有所選標籤的API。 我們建議您使用「退出CCPA」。
>
>如需詳細資訊，請參閱隱私權 [管理檔案](https://helpx.adobe.com/campaign/kb/acs-privacy.html#ccpa)。

<br/>

***請求範例***

* 擷取描述檔CCPA退出狀態的範例GET要求。

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

* 標示CCPA退出描述檔的POST要求範例。

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

* 更新CCPA選擇退出配置檔案的PATCH請求示例。

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
