---
solution: Campaign Standard
product: campaign
title: 疑難排解
description: 進一步瞭解與Campaign Standard API相關的常見問題。
audience: developing
content-type: reference
topic-tags: use-case--extending-the-api
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 0%

---


# 疑難排解 {#troubleshooting}

* **前往Adobe.io Console時，您會收到下列錯誤：「Adobe I/O主控台僅適用於選擇的企業帳戶成員。如果您認為您應該擁有訪問權限，請聯繫您的系統管理員。&quot;**

您只能為您所管理的IMS組織建立API金鑰。 如果顯示此訊息，而您想要建立API金鑰，而且您想要向IMS組織的管理員提出要求。

* **對Adobe.io執行請求時，您會收到{&quot;error_code&quot;:&quot;403023&quot;,&quot;message&quot;:&quot;Profile is not valid&quot;}**

這表示您的特定促銷活動產品的IMS布建有問題：ims團隊需要修正它。

若要取得更多詳細資訊，您可以使用您的Token呼叫IMS API，以查看您的IMS設定檔外觀：您需要有prodCtx，其中organization_id與您在URL中放置的prodCtx相同，Adobe.io才能傳送您的請求。
如果IMS布建遺失，則需要修正。

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

* **對Adobe.io執行請求時，您會收到{&quot;code&quot;:500, &quot;message&quot;:&quot;Aorsh.出了點問題。 檢查您的URI並再試一次。&quot;}**

Adobe.io宣告您的無效URI:您請求的URI很可能無效。 在Adobe.io上，當您選取Campaign服務時，會收到含有可能organization_id清單的選擇器。 您必須檢查您選擇的是否是您置入URL的URL。

* **對Adobe.io執行請求時，您會收到{&quot;error_code&quot;:&quot;401013&quot;,&quot;message&quot;:&quot;Oauth token is not valid&quot;}**

您的Token無效（用來產生Token的不當IMS呼叫）或您的Token已過期。

* **我在創作完成後就看不到個人檔案**

根據實例配置，建立的配置檔案必須與&#x200B;**orgUnit**&#x200B;關聯。 要瞭解如何在建立中添加此欄位，請參考[本節](../../api/using/creating-profiles.md)。

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
