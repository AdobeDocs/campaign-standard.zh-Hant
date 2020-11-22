---
solution: Campaign Standard
product: campaign
title: 必讀
description: 使用API前必須先閱讀。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 0%

---


# Must-Read {#must-read}

## 技術需求

* Adobe Campaign API僅能用於伺服器對伺服器。
* 如果您要實作的使用案例符合Adobe Campaign API所允許的規模，請務必洽詢您的Adobe技術聯絡人。
* 設定AdobeIO存取權需要特定權限，如有任何問題，請聯絡Adobe支援。

## 資源表示法

所有API資源都可在 **JSON中使用** ，其副檔名為URL，或在HTTP接受標題內：

`GET /profileAndServices/<resourceName>.json`

>[!NOTE]
>
>在URL中沒有副檔名時， **json格式是內容類型的預設格式** 。

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

* 說明示例的自動主鍵(PKey)值不打算用於其他特定部署。 這些應用程式是由Adobe Campaign API所製作。

* Adobe Campaign產生的自動主要金鑰值絕對不能儲存在外部資料庫或網站中。 您必須在資料庫定義中生成特定的鍵欄位，並在開發過程中使用它。

## 自訂金鑰 {#custom-keys}

如果描述檔資源已使用自訂金鑰欄位進行擴充，您可將此欄位用作金鑰，而非Adobe Campaign產生的自動主要金鑰：

`GET /.../profileAndServicesExt/profile/<customKey>`

如果密鑰值與原始密鑰不同，或者您使用自己的業務密鑰作為URI而不是Adobe提供的密鑰，則不能使用PATCH操作來修改自定義密鑰。

僅對頂層描述檔 **資源使用自訂金鑰** 。 URL由API傳回，不應由您自己建立。

<br/>

***請求範例***

若要使用自訂金鑰擷取描述檔的訂閱，請對自訂金鑰執行GET作業。

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
