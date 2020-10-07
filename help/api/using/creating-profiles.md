---
title: 建立設定檔
description: 進一步瞭解如何使用API建立設定檔。
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 建立設定檔 {#creating-profiles}

建立配置式時會對配置 **式資源** 執行POST請求。

>[!CAUTION]
>
>如果要將 <b>orgUnit</b> 與建立的配置檔案關聯，您需要將此欄位擴展配置檔案資源，並在發佈擴展後對 <b></b> ProfileAndServicesExt端點執行POST請求。
>
>如需描述檔資源擴充功能的詳細資訊，請參閱促銷活 <a href="https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html#partitioning-profiles">動檔案</a>。

<br/>

***請求範例***

建立具有電子郵件「john.doe@mail.com」之描述檔的POST要求範例。

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-i
-d '{"email":"john.doe@mail.com"}'
```

它會傳回新建立的設定檔，並加上「john.doe@mail.com」電子郵件地址。

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
