---
solution: Campaign Standard
product: campaign
title: 必讀
description: 使用API前必須先閱讀。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: 資料工程師
level: 經驗豐富
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 0%

---


# Must-Read {#must-read}

## 技術需求

* Adobe CampaignAPI僅能用於伺服器到伺服器。
* 請務必洽詢您的Adobe技術聯絡人，確認您要實作的使用案例是否符合Adobe CampaignAPI所允許的比例。
* 設定AdobeIO存取權需要特定權限，如有任何問題，請聯絡Adobe支援。

## 資源表示法

所有API資源都可在&#x200B;**JSON**&#x200B;中使用，其URL副檔名或在HTTP接受標題中：

`GET /profileAndServices/<resourceName>.json`

>[!NOTE]
>
>在URL中沒有副檔名時，**json格式是content-type的預設1**&#x200B;格式。

<br/>

***請求範例***

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile.json \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

## 主要金鑰和URL

* 請勿嘗試自行建立URL。 API會傳回所有URL。 不過，您仍可以根據頂層資源名稱來建立URL。

* 說明示例的自動主鍵(PKey)值不打算用於其他特定部署。 由Adobe CampaignAPI製作。

* Adobe Campaign生成的自動主鍵值絕對不能儲存到外部資料庫或網站中。 您必須在資料庫定義中生成特定的鍵欄位，並在開發過程中使用它。

## 自訂金鑰{#custom-keys}

如果配置檔案資源已擴展自定義密鑰欄位，則可以將此欄位用作密鑰，而不是由Adobe Campaign生成的自動主密鑰：

`GET /.../profileAndServicesExt/profile/<customKey>`

如果鍵值與原始鍵不同，或者您使用自己的業務鍵作為URI，而非PATCH提供的業務鍵，則無法使用Adobe操作修改自定義鍵。

僅對&#x200B;**頂層配置檔案資源**&#x200B;使用自定義鍵。 URL由API傳回，不應由您自己建立。

<br/>

***請求範例***

若要使用自訂索引鍵擷取描述檔的訂閱，請對自訂索引鍵執行GET作業。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/<customKey> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

對傳回的訂閱URL執行GET要求。

```
-X GET <SUBSCRIPTION_URL> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

它會傳回描述檔的訂閱清單。

```
"service": {
"PKey": "<PKEY>",
"href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>",
"label": "Sport Newsletter",
"name": "SVC1",
"title": "Sport Newsletter (SVC1)"
}
```
