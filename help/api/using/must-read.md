---
title: 必讀
description: 必須先閱讀，才能使用API。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 9e2d1b59-55a5-4715-adfb-35191a9df536
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '374'
ht-degree: 0%

---

# 必讀 {#must-read}

## 技術需求

* Adobe Campaign API只能使用伺服器對伺服器。
* 如果您要實作的使用案例與Adobe Campaign API允許的比例相符，請務必洽詢您的Adobe技術聯絡人。
* 設定AdobeIO存取需要特定權限，如有任何問題，請聯絡Adobe支援。

## 權限與存取

* 依預設，Adobe Campaign API會使用管理員內容，因此組織單位和角色不適用。
* Adobe Campaign API會從角色內容中排除。
* 如果您想要以組織單位或角色來設定API，請先洽詢您的Adobe技術聯絡人。

## 資源表示

所有API資源都可在&#x200B;**JSON**&#x200B;中，以URL副檔名或在HTTP Accept Header中使用：

`GET /profileAndServices/<resourceName>.json`

>[!NOTE]
>
>若URL中沒有副檔名，**json格式是content-type的預設格式**。

<br/>

***請求範例***

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile.json \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

## 主要索引鍵和URL

* 請勿自行建立URL。 API會傳回所有URL。 不過，您可以根據頂層資源名稱來建立URL。

* 說明示例的自動主鍵(PKey)值不打算在其他特定部署中工作。 由Adobe Campaign API製作。

* Adobe Campaign產生的自動主索引鍵值絕不得儲存至外部資料庫或網站。 您必須在資料庫定義中產生特定索引鍵欄位，並在開發期間使用它。

## 自訂金鑰 {#custom-keys}

如果設定檔資源已使用自訂金鑰欄位擴充，您可以將此欄位作為金鑰，而非Adobe Campaign產生的自動主金鑰：

`GET /.../profileAndServicesExt/profile/<customKey>`

如果鍵值與原始鍵不同，或者您使用自己的業務鍵作為URI，而不是PATCH提供的業務鍵，則無法使用Adobe操作修改自定義鍵。

僅對&#x200B;**頂層配置檔案資源**&#x200B;使用自定義鍵。 URL由API傳回，且絕不應由您自己建立。

<br/>

***範例要求***

若要使用自訂金鑰擷取設定檔的訂閱，請對自訂金鑰執行GET作業。

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

它會傳回設定檔的訂閱清單。

```
"service": {
"PKey": "<PKEY>",
"href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>",
"label": "Sport Newsletter",
"name": "SVC1",
"title": "Sport Newsletter (SVC1)"
}
```
