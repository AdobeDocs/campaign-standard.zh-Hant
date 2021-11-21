---
title: 疑難排解
description: 進一步了解與Campaign StandardAPI相關的常見問題。
audience: developing
content-type: reference
topic-tags: use-case--extending-the-api
feature: API
role: Data Engineer
level: Experienced
exl-id: 404356cd-021f-4739-a88f-b8b1b79e19bc
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 0%

---

# 疑難排解 {#troubleshooting}

* **前往Adobe.io主控台時，您會收到下列錯誤：「Adobe I/O控制台僅可用於選擇企業帳戶的成員。 如果您認為應該擁有訪問權限，請與您的系統管理員聯繫。」**

您只能為您所管理的IMS組織建立API金鑰。 如果顯示此訊息，而您想建立API金鑰，且想要向IMS組織的管理員之一詢問。

* **對Adobe.io執行請求時，您會收到{&quot;error_code&quot;:&quot;403023&quot;,&quot;message&quot;:&quot;配置檔案無效&quot;}**

這表示您特定Campaign產品的IMS布建有問題：IMS團隊需要加以修正。

若要取得更多詳細資料，您可以使用代號呼叫IMS API，查看您的IMS設定檔外觀：您必須有一個prodCtx，其中organization_id與您在Adobe.io的URL中放入的organization_id相同，才能路由您的請求。
如果缺少IMS布建，則需要修正。

```
-X GET https://mc.adobe.io/{ORGANIZATION}/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

它會傳回下列錯誤。

```
{"error_code":"403023","message":"Profile is not valid"}
```

使用此請求檢查您的IMS設定檔。

```
-X GET https://ims-na1.adobelogin.com/ims/profile/v1 \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

在回應中，ORGANIZATION_ID值在您的第一個GET請求中必須相同。

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

* **對Adobe.io執行請求時，您會收到{&quot;code&quot;:500, &quot;message&quot;:&quot;Aosh。 出了點問題。 請檢查URI，然後重試。&quot;}**

Adobe.io聲明您的無效URI:您請求的URI很可能無效。 在Adobe.io上，當您選取Campaign服務時，畫面會顯示可能的organization_id清單的選取器。 您需要檢查您選擇的是否是您放入URL的URL。

* **對Adobe.io執行請求時，您會收到{&quot;error_code&quot;:&quot;401013&quot;,&quot;message&quot;:&quot;Oauth token無效&quot;}**

您的Token無效（用來產生Token的IMS呼叫不正確）或Token已過期。

* **建立後我沒有看到我的個人資料**

根據執行個體設定，建立的設定檔必須與 **orgUnit**. 若要了解如何在您的建立中新增此欄位，請參閱 [本節](../../api/using/creating-profiles.md).

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
