---
title: API故障排除
description: 瞭解與常見問題相關的Campaign StandardAPI的更多資訊
feature: API
role: Data Engineer
level: Experienced
exl-id: 404356cd-021f-4739-a88f-b8b1b79e19bc
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 1%

---

# API 疑難排解 {#troubleshooting}

* **轉到Adobe.io控制台時，將出現以下錯誤：&quot;Adobe I/O控制台僅可用於選擇企業帳戶的成員。 如果您認為您應該擁有訪問權限，請與系統管理員聯繫。」**

您只能為您管理的IMS組織建立API密鑰。 如果顯示此消息，並且您想建立API密鑰，並且您想詢問IMS組織的管理員之一。

* **在請求Adobe.io時，您會得到{ &quot;error_code&quot;:&quot;403023&quot;,&quot;message&quot;:&quot;配置檔案無效&quot;}**

這意味著您的特定市場活動產品的IMS配置存在問題：IMS團隊需要修復它。

要獲取更多詳細資訊，您可以使用令牌調用IMS API，以查看您的IMS配置檔案的樣式：您需要有一個prodCtx，其中organization_id與URL中的organization_id相同，以便Adobe.io能夠路由您的請求。
如果缺少IMS配置，需要修復。

```
-X GET https://mc.adobe.io/{ORGANIZATION}/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

它返回以下錯誤。

```
{"error_code":"403023","message":"Profile is not valid"}
```

使用此請求檢查您的IMS配置檔案。

```
-X GET https://ims-na1.adobelogin.com/ims/profile/v1 \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

在響應中，ORGANIZATION_ID值在第一個GET請求中必須相同。

```
{
  "countryCode": "FR",
  "mrktPermEmail": null,
  "projectedProductContext": [
    {
    "prodCtx": {
      "statusCode": "ACTIVE",
      "ident": "ZQ9FRQK7BF09YXAESFY9DDQP1G",
      "modDts": 1448307260000,
      "organization_id": "actest",
      "owningEntity": "6096892F54B5819E0A4C98A2@AdobeOrg",
      "serviceCode": "dma_tartan",
      "label": "Adobe Marketing Cloud",
      "serviceLevel": "standard",
      "createDts": 1421181343000,
      "deal_id": " "
      }
    }
  ]
}
```

* **在請求Adobe.io時，您會得到{&quot;code&quot;:500, &quot;message&quot;:&quot;Aoh。 發生錯誤. 請檢查URI，然後重試。&quot;}**

Adobe.io聲明無效的URI:您請求的URI很可能無效。 在Adobe.io上，選擇「市場活動」服務時，您將得到一個具有可能organization_id清單的選取器。 您需要檢查您選擇的是否是您在URL中輸入的。

* **在請求Adobe.io時，您會得到{&quot;error_code&quot;:&quot;401013&quot;,&quot;message&quot;:&quot;Oauth令牌無效&quot;}**

令牌無效（用於生成令牌的IMS調用不正確）或令牌已過期。

* **建立後我看不到個人資料**

根據實例配置，建立的配置檔案需要與 **組織單位**。 要瞭解如何在建立中添加此欄位，請咨詢 [此部分](../../api/using/creating-profiles-api.md)。

<!-- * (error duplicate key : quand tu crées un profile qui existe déjà , il faut faire un patch pour updater le profile plutôt qu’un POST)

With Curl
List all profiles

Create a profile

Update the mobilePhone attribute of a profile

API Calls on Service

GET the list of services

-->

<!--

How to find and use a filter?
Error codes:

* PAtch sur Age = message d'erreur :
500
Cannot update the 'age' property that is read-only
'age' property is not valid for the 'profile' resource.
-->

<!--
How to filter a list of subscribed profiles with available profile filters ? by date (by les filtres dispo sur la ressource) ?

Pattern classique :

recupérer la liste des subscriptions filtrées d'un profile
1) get sur profile
2) recup PKey
3) get sur PKey
4) get sur href des subscriptions

Comment savoir quel filtre appliquer ?

1) get sur metadata de profile
2) retourne description de la collection subscription
3) get sur la valeur du champ resTarget
4) get sur le href dans filters
5) retourne les filtres applicables sur l'url des data.

-->
