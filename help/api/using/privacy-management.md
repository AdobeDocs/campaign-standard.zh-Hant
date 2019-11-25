---
title: 隱私權管理
description: 進一步瞭解使用API進行隱私權管理
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c0c0be79613f99a15676343d8ce10d335baf968a

---


# 隱私權管理 {#privacy-management}

Campaign Standard API提供允許自動處理與隱私權法規（例如GDPR和CCPA）相關要求的功能。

您可以執行的動作如下：

* 建立新的隱私權要求，
* 監控隱私權要求，
* 擷取隱私權資料檔案，
* 管理配置檔案的CCPA選擇退出狀態。

隱私權API端點是 **/privacy/privacyTool**。 PrivacyTool資源說明和相關的篩選器可在資源元資料中使用。 請參閱 [中繼資料機制](../../api/using/metadata-mechanism.md)。

使用ccpaOptOut描述檔屬性來管 **理CCPA退出** 。

如需Adobe Campaign standard和隱私權規範的詳細資訊，請參閱專用 [檔案](https://helpx.adobe.com/campaign/kb/acs-privacy.html)。

## 建立隱私權要求 {#creating-a-privacy-request}

>[!CAUTION]
>
>隱 [私權核心服務](https://adobe.io/apis/cloudplatform/gdpr.html) 「整合」是您應用於所有存取和刪除要求的方法。 從19.4開始，已不再使用促銷活動API和介面來存取和刪除請求。 如需Campaign Standard已停用和移除功能的詳細資訊，請參 [閱此頁](https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html)。

隱私權要求是使用 **POST要求** 。

在建立請求之前，您必須先定義要使用的命名空間。 如需詳細資訊，請參閱隱私 [權管理檔案](https://helpx.adobe.com/campaign/kb/acs-privacy.html#ManagingPrivacyRequests)。

裝載必須包含下列參數：

* **名稱**:唯一的內部名稱
* **namespace**:在Campaign Standard介面中設定的命名空間名稱
* **reconsiblitionValue**:基於命名空間中定義的協調鍵的協調值
* **標籤**:請求標籤
* **類型**:請求類型。 接受的值是「存取」或「刪除」。
* **規章**:監管類型。 範例：「GDPR」、「CCPA」。 此參數為必要參數，且可從Campaign Standard 19.4版開始使用。 如果您使用舊版軟體，則不需要將它新增至裝載。

<br/>

***請求範例***

此POST要求會根據命名空間AMCDS2中定義的電子郵件協調金鑰，建立隱私權要求：

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/privacy/privacyTool \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-H 'Content-Type: application/json;charset=utf-8'

{
"name":"PT11832",
"namespaceName": "AMCDS2",
"reconciliationValue": "customers@adobe.com",
"regulation": "gdpr",
"label":"Delete customers",
"type":"delete"
}
```

回應POST請求。

```
{
    "PKey": "<PKEY>",
    "audit": "",
    "created": "2018-03-21 10:41:58.570Z",
    "desc": "",
    "gdprRequestData": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/head/privacyTool/<PKEY>/gdprRequestData/"
    },
    "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/privacy/privacyTool/<PKEY>",
    "label": "Delete customers",
    "lastModified": "2018-03-21 10:41:58.570Z",
    "name": "PT11832",
    "namespace": {
        "PKey": "<PKEY>",
        "title": "Doc (AMCDS2)"
    },
    "namespaceName": "AMCDS2",
    "reconciliationValue": "customers@adobe.com",
    "regulation": "gdpr",
    "retryCount": 0,
    "status": "new",
    "title": "Delete customers (PT11832)",
    "type": "delete"
}
```

## 監控隱私權要求

您可以使用 **GET要求來監控已建立隱私權要求的** 相關資訊。

「隱私權管理」檔案中提供狀態 [清單說明](https://helpx.adobe.com/campaign/kb/acs-privacy.html#ManagingPrivacyRequests)。

<br/>

***請求範例***

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/privacy/privacyTool \
-H 'Authorization: Bearer <ACCESS_TOKEN>'
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-H 'Content-Type: application/json;charset=utf-8'
```

回應GET要求。

```
{
            "PKey": "<PKEY>",
            "audit": "",
            "created": "2018-03-09 12:28:37.319Z",
            "desc": "",
            "gdprRequestData": {
                "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/privacy/privacyTool/<PKEY>/gdprRequestData/"
            },
            "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/privacy/privacyTool/<PKEY>",
            "label": "Delete customer profile",
            "lastModified": "2018-03-09 12:39:21.232Z",
            "name": "GDPR6",
            "namespace": {
                "PKey": "<PKEY>",
                "title": "Email (defaultNamespace1)"
            },
            "namespaceName": "defaultNamespace1",
            "reconciliationValue": "customers@adobe.com",
            "regulation": "gdpr",
            "retryCount": 0,
            "status": "errorDataNotFound",
            "title": "Delete customer profile (GDPR6)",
            "type": "delete"
        }
```

## 檢索隱私資料檔案

>[!CAUTION]
>
>隱 [私權核心服務](https://adobe.io/apis/cloudplatform/gdpr.html) 「整合」是您應用於所有存取和刪除要求的方法。 從19.4開始，已不再使用促銷活動API和介面來存取和刪除請求。 如需Campaign Standard已停用和移除功能的詳細資訊，請參 [閱此頁](https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html)。

要檢索包含與協調值關聯的所有資訊的檔案，請執行以下三步驟：

1. 執行 **POST** requests，以建立屬性 **type="access"的新請求**，請 [參閱Creating a new privacy request](#creating-a-privacy-request)。

1. 執行 **GET** 要求以擷取有關要求的資訊。

1. 在傳回的privacyRequestData **** URL上執行 **** POST請求，並在裝載內使用隱私權請求內部名稱，以擷取資料檔案。 例如：{"name":"PT17"}。

<br/>

***請求範例***

使用type="access"屬性建立隱私權要求。

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/privacy/privacyTool \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-H 'Content-Type: application/json;charset=utf-8'

{
"name":"PT11832",
"namespaceName": "AMCDS2",
"reconciliationValue": "customers@adobe.com",
"regulation": "gdpr",
"label":"Delete customers",
"type":"access"
}
```

<!-- + réponse -->

執行GET請求以擷取有關請求的資訊。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/privacy/privacyTool \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-H 'Content-Type: application/json;charset=utf-8'
```

它會傳回具有關聯URL的privacyRequestData屬性。

```
{
    ...
    "name": "PR2",
    "namespace": ...,
    "namespaceName": "defaultNamespace1",
    "privacyRequestData": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/privacy/privacyTool/<PKEY>/privacyRequestData/"
    },
    "reconciliationValue": "johndoe@mail.com",
    "regulation": "gdpr",
    "retryCount": 0,
    "status": "complete",
    "title": "EPR (PR2)",
    "type": "access"
    ...
},
```

在privacyRequestData URL上執行POST要求，並在裝載內使用要求內部名稱。

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/privacy/privacyTool/<PKEY>/privacyRequestData \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-H 'Content-Type: application/json;charset=utf-8'
-d '{"name": "PR1"}'
```

它會傳回檔案內容。

```
"{data:<gdprRequestData _cs=\" ()\" id=\"8565163\" reconciliationValue=\"'customer@adobe.com'\">\n  <table name=\"nms:recipient\">\n    <rowId='8569152'\n\t\tlastName='customer'\n\t\tfirstName='customer'\n\t\tgender='1'\n\t\temail='customer@adobe.com'\n\t\tcreatedBy-id='8565162'\n\t\tmodifiedBy-id='8565162'\n\t\tlastModified='2018-03-15 13:54:28.708Z'\n\t\tcreated='2018-03-15 13:54:28.708Z'\n\t\tthumbnail='/nl/img/thumbnails/defaultProfil.png'\n\t\temailFormat='2'</row>\n  </table>\n  <table name=\"nms:broadLogRcp\">\n    <row>deliveryLabel='Send via email'\n\t\tdeliveryType='0'\n\t\tcontactDate='2018-03-15 13:58:31.667Z'\n\t\tid='8003'\n\t\taddress='customer@adobe.com'\n\t\tstatus='1'\n\t\tmsg-id='1194'\n\t\teventDate='2018-03-15 13:58:34.726Z'\n\t\tlastModified='2018-03-15 13:59:02.008Z'\n\t\tvariant='default'\n\t\tdelivery-id='8569153'\n\t\tpublicId='1'\n\t\tprofile-id='8569152'</row>\n  </table>\n  <table name=\"nms:trackingLogRcp\">\n    <row>deliveryLabel='Send via email'\n\t\tdeliveryType='0'\n\t\tcontactDate='2018-03-15 13:58:31.667Z'\n\t\turlLabel='Open'\n\t\turlSource=''\n\t\tuserAgent='-1178080215'\n\t\ttrackedDevice='pc'\n\t\tid='5000'\n\t\tlogDate='2018-03-15 14:00:51.650Z'\n\t\tsourceType='html'\n\t\tuserAgent='-1178080215'\n\t\turl-id='1'\n\t\tdelivery-id='8569153'\n\t\tbroadLog-id='8003'\n\t\trecipient-id='8569152'</row>\n    <row>deliveryLabel='Send via email'\n\t\tdeliveryType='0'\n\t\tcontactDate='2018-03-15 13:58:31.667Z'\n\t\turlLabel='Open'\n\t\turlSource=''\n\t\tuserAgent='0'\n\t\ttrackedDevice=''\n\t\tid='6000'\n\t\tlogDate='2018-03-15 16:00:41.110Z'\n\t\tsourceType='html'\n\t\turl-id='1'\n\t\tdelivery-id='8569153'\n\t\tbroadLog-id='8003'\n\t\trecipient-id='8569152'</row>\n  </table>\n</gdprRequestData>}"
```

## 管理CCPA選擇退出

可使用 **** ccpaOptOut配置檔案屬性和「true」或「false」值來監視和管理配置檔案的CCPA退出狀態：

`"ccpaOptOut": <value>`

* **true**: 禁止銷售個人資訊。
* **false**:授權銷售個人資訊。

>[!CAUTION]
>
>「CCPA選擇退出」屬性僅從19.4開始提供。對於19.3環境，您需要擴展Profiles資源並添加布爾欄位。 此欄位將會新增至具有所選標籤的API。 我們建議您使用「退出CCPA」。
>
>如需詳細資訊，請參閱隱私權 [管理檔案](https://helpx.adobe.com/campaign/kb/acs-privacy.html#ccpa)。

<br/>

***請求範例***

* 擷取描述檔CCPA退出狀態的範例GET要求。

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profilesAndServices/profile/<PKEY> \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>' \
   -H 'Content-Type: application/json;charset=utf-8'
   ```

   回應GET要求。

   ```
   {
   "PKey": "<PKEY>",
     "ccpaOptOut": false,
     "firstName": "John",
     "lastName": "Doe",
   ...
   }
   ```

* 標示CCPA退出描述檔的POST要求範例。

   ```
   -X POST https://mc.adobe.io/<ORGANIZATION>/campaign/profilesAndServices/profile/ \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>' \
   -H 'Content-Type: application/json;charset=utf-8'
   -i
   -d {
   -d  "firstName": "John",
   -d  "lastName": "Doe",
   -d  "email": "jdoe@mail.com",
   -d  "ccpaOptOut": true
   -d }'
   ```

   回應GET要求。

   ```
   {
       ...
       "email": "john.doe@mail.com",
       "firstName": "John",
       "lastName": "Doe",
       "ccpaOptOut": true,
       ...
   }
   ```

* 更新CCPA選擇退出配置檔案的PATCH請求示例。

   ```
   -X PATCH https://mc.adobe.io/<ORGANIZATION>/campaign/profilesAndServices/profile/<PKEY> \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>' \
   -H 'Content-Type: application/json;charset=utf-8'
   -i
   -d {
   -d  "ccpaOptOut": true
   -d }'
   ```

   回應GET要求。

   ```
   {
       ...
       "email": "john.doe@mail.com",
       "firstName": "John",
       "lastName": "Doe",
       "ccpaOptOut": true,
       ...
   }
   ```
