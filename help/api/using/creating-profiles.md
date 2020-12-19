---
solution: Campaign Standard
product: campaign
title: 建立設定檔
description: 進一步瞭解如何使用API建立設定檔。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 3%

---


# 建立設定檔 {#creating-profiles}

建立配置式時，在配置式資源上使用&#x200B;**POST**&#x200B;請求執行。

>[!CAUTION]
>
>如果要將<b>orgUnit</b>關聯到建立的配置檔案，您需要將此欄位擴展配置檔案資源，並在發佈擴展後，對<b>ProfileAndServicesExt</b>端點執行POST請求。
>
>如需描述檔資源擴充功能的詳細資訊，請參閱<a href="https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html#partitioning-profiles">促銷活動檔案</a>。

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
