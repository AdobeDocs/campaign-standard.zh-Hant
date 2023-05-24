---
title: 必讀
description: 使用API之前必須讀取。
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

## 技術要求

* Adobe CampaignAPI必須僅使用伺服器到伺服器。
* 如果要實施的用例與Adobe CampaignAPI允許的比例一致，請始終與Adobe技術聯繫人聯繫。
* 設定AdobeIO訪問需要特定權限，請與Adobe支援聯繫以解決任何問題。

## 權限和訪問

* 預設情況下，Adobe CampaignAPI使用管理員上下文，因此組織單位和角色不適用。
* Adobe CampaignAPI被排除在角色上下文之外。
* 如果要使用組織單位或角色配置API，請首先與要Adobe的技術聯繫人聯繫。

## 資源表示

所有API資源均可用於 **JSON** URL擴展或HTTP接受標頭內：

`GET /profileAndServices/<resourceName>.json`

>[!NOTE]
>
>如果URL中沒有副檔名， **json格式是預設格式** 的子菜單。

<br/>

***請求示例***

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile.json \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

## 主鍵和URL

* 不要嘗試自己生成URL。 所有URL都由API返回。 但是，可以基於頂級資源名稱生成URL。

* 說明這些示例的自動主鍵(PKey)值不適用於其他特定部署。 它們由Adobe CampaignAPI生產。

* Adobe Campaign生成的自動主鍵值永遠不能儲存到外部資料庫或網站中。 必須在資料庫定義中生成特定的關鍵字欄位，並在開發過程中使用它。

## 自定義鍵 {#custom-keys}

如果配置檔案資源已使用自定義鍵欄位進行擴展，則可以將此欄位用作鍵，而不是Adobe Campaign生成的自動主鍵：

`GET /.../profileAndServicesExt/profile/<customKey>`

如果鍵值與源鍵不同，或者您使用自己的業務鍵作為URI而不是PATCH提供的業務鍵，則無法使用Adobe操作修改自定義鍵。

使用自定義鍵 **頂級配置檔案資源** 只是。 URL由API返回，不應由自己生成。

<br/>

***示例請求***

要使用自定義鍵檢索配置檔案的GET，請對自定義鍵執行訂閱操作。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/<customKey> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

對返回的訂閱URL執行GET請求。

```
-X GET <SUBSCRIPTION_URL> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

它返回配置檔案的訂閱清單。

```
"service": {
"PKey": "<PKEY>",
"href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>",
"label": "Sport Newsletter",
"name": "SVC1",
"title": "Sport Newsletter (SVC1)"
}
```
