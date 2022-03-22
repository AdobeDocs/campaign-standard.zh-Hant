---
title: 使用API建立配置檔案
description: 瞭解如何使用API建立配置檔案。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 69e8d034-6bdd-4b82-bcd7-1ef4be0a59b3
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 0%

---

# 使用API建立配置檔案 {#creating-profiles-api}

建立配置檔案時使用 **POST** 請求。

>[!CAUTION]
>
>如果要關聯 <b>組織單位</b> 在建立的配置檔案中，您需要使用此欄位擴展配置檔案資源，並在發佈擴展後對 <b>配置檔案和服務擴展</b> 端點。
>
>有關配置檔案資源擴展的詳細資訊，請參閱 <a href="https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html#partitioning-profiles">市場活動文檔</a>。

<br/>

***示例請求***

POST請求示例，以使用電子郵件「john.doe@mail.com」建立配置檔案。

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-i
-d '{"email":"john.doe@mail.com"}'
```

它返回新建立的配置檔案，並帶有「john.doe@mail.com」電子郵件地址。

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
