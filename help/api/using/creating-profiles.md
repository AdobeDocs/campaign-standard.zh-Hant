---
title: 建立設定檔
description: 進一步了解如何使用API建立設定檔。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 69e8d034-6bdd-4b82-bcd7-1ef4be0a59b3
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 3%

---

# 建立設定檔 {#creating-profiles}

在設定檔資源上，使用&#x200B;**POST**&#x200B;請求來建立設定檔。

>[!CAUTION]
>
>如果要將<b>orgUnit</b>關聯到建立的配置檔案，則需要將配置檔案資源擴展到此欄位，並在發佈擴展後，在<b>ProfileAndServicesExt</b>端點上執行POST請求。
>
>如需設定檔資源擴充功能的詳細資訊，請參閱<a href="https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html#partitioning-profiles">Campaign檔案</a>。

<br/>

***範例要求***

以電子郵件「john.doe@mail.com」建立設定檔的POST請求範例。

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-i
-d '{"email":"john.doe@mail.com"}'
```

它會傳回新建立的設定檔，並附上「john.doe@mail.com」電子郵件地址。

```
{
    "PKey": "<PKEY>",
    "firstName": "John",
    "lastName":"Doe",
    "birthDate": "1980-10-24",
    "email": "john.doe@mail.com",
    ...
}
```
