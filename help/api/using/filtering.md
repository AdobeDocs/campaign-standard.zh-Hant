---
solution: Campaign Standard
product: campaign
title: 篩選
description: 瞭解如何執行篩選操作。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 1%

---


# 篩選 {#filtering}

## 擷取篩選器中繼資料

篩選器可用於每個資源。 要標識與資源關聯的篩選器，您需要對資源元資料執行GET請求。 此請求會傳回為特定資源定義所有篩選器的URL。 有關元資料的詳細資訊，請參閱[本節](../../api/using/metadata-mechanism.md)。

若要識別篩選器的中繼資料並決定如何使用，您必須對先前傳回的URL執行GET要求。

<br/>

***請求範例***

下面的示例負載顯示如何檢索「配置檔案」資源的「byText」過濾器元資料。 首先，對&quot;profile&quot;資源元資料執行GET請求。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/resourceType/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

它會傳回說明篩選器的URL。

```
{
"filters": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/resourceType/<PKEY>/filters/"
    }
  }
```

對URL執行GET要求。 它會傳回描述檔資源的篩選清單，其中中繼資料與每個篩選相關聯。

```
{
"birthday": {
        "PKey": "@FL-CbDFXbnHbXcVpeCGWL46VXJLn1LqxLMPagt2vz8sCxQ52lvB15KiUaxXkxJYQw-tZXYrgUWG6K8QcB4gxVY9RKoba5bRFY3294YFshDmorRr8",
        "category": "0150_profile",
        "condition": ...,
        "data": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/birthday?type=$value&precision=$value&operator=$value&day=$value&month=$value&includeStart=$value&endDay=$value&endMonth=$value&includeEnd=$value&relativeValue=$value&nextUnitsValue=$value&previousUnitsValue=$value",
        "formType": "webPage",
        "fragmentName": "",
        "label": "Birthday",
}
```

## 篩選中繼資料結構

每個篩選器可使用相同的中繼資料結構：

* **@formType**&#x200B;和&#x200B;**@webPage**&#x200B;欄位為技術欄位。
* **data**&#x200B;欄位提供如何使用篩選的範例。
* **metadata**&#x200B;節點描述過濾器參數。
* **condition**&#x200B;節點描述過濾器的用途。 中繼資料節點中描述的篩選參數可用來建立篩選條件。 對於每個篩選條件，如果&#x200B;**enabledIf**&#x200B;為true，則會套用&#x200B;**expr**。

<br/>

篩選中繼資料結構範例：

```
"byText": {
        "PKey": "...",
        "category": "99_none",
        "condition": ...,
        "data": "/profileAndServices/profile/byText?text=$value",
        "formType": "none",
        "fragmentName": "",
        "label": "By name or email",
    }
```

## 使用濾鏡

篩選會與下列請求一起執行：

`GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/<resourceName>/by<filterName>?<filterParam>=<filterValue>`

您可以在單一請求中合併多個篩選：

`GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/<resourceName>/<filter1name>/<filter2name>?<filter1param>=<filter1value>&<filter2param>=<filter2value>`

<br/>

***請求範例***

* 檢索「服務」資源的GET請求示例，類型為「電子郵件」。

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/byChannel?channel=email \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```

   回應請求。

   ```
   {
       "content": [
           {
               "PKey": "<PKEY>",
               "created": "2019-09-25 23:20:35.000Z",
               "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/@I_FIiDush4OQPc0mbOVR9USoh36Tt5CsD35lATvQjdWlXrYc0lFkvle2XIwZUbD8GqTVvSp8AfWFUvjkGMe1fPe5nok",
               "label": "Marketing Newsletter",
               "lastModified": "2019-09-25 23:20:35.000Z",
               "limitedDuration": false,
               "messageType": "email",
               "mode": "newsletter",
               ...
           },
           ...
       ],
       ...
   }
   ```

* 擷取「描述檔」資源的範例GET要求，其中包含「Doe」(在
電子郵件或姓氏欄位（byText篩選器會搜尋電子郵件和姓氏欄位）。

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/byText?text=Doe \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```

   回應請求。

   ```
   {
       "content": [
           {
               "PKey": "<PKEY>",
               "firstName": "John",
               "lastName":"Doe",
               "birthDate": "1980-10-24",
               ...
           }
           ...
       ],
       ...
   }
   ```

* GET要求範例，以擷取「email」類型和「sport」標籤的服務資源。

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/byChannel/byText?channel=email&text=sport \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```

   回應請求。

   ```
   {
       "content": [
           {
               "PKey": "<PKEY>",
               "created": "2019-09-26 09:36:01.014Z",
               "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>",
               "label": "sport",
               "lastModified": "2019-09-26 09:36:01.014Z",
               "limitedDuration": false,
               "messageType": "email",
               "mode": "newsletter",
               "name": "SVC13",
               ...
           }
       ],
       ...
   }
   ```

## 自訂篩選器

如果您想要使用自訂篩選，則必須在Adobe Campaign Standard介面中建立並自訂篩選。 然後，自訂篩選器的行為將與預設篩選器相同：

`GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/<resourceName>/by<customFilterName>?<customFilterparam>=<customFilterValue>`

如需詳細資訊，請參閱Campaign Standard檔案：

* [設定篩選定義](https://helpx.adobe.com/campaign/standard/developing/using/configuring-filter-definition.html).
* [使用案例：使用複合標識鍵調用資源](https://docs.adobe.com/content/help/en/campaign-standard/using/developing/adding-or-extending-a-resource/uc-calling-resource-id-key.html)。

<br/>

***請求範例***

檢索事務處理金額為100$或更多的「配置檔案」資源的GET請求示例。 請注意，「byAmount」篩選器已先在Adobe Campaign Standard介面中定義，並連結至「交易」自訂表格。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/byAmount?amount_parameter=100 \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

<!--
Response to the request.

```

{
    "content": [
        {
            "PKey": "<PKEY>",
            "builtIn": false,
            "created": "2019-09-26 09:36:01.014Z",
            "desc": "",
            "end": "",
            "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY>",
            ...
        }
    ],
}

```

-->

<!-- exemple à vérifier de bout en bout-->

<!--+category = query editor
privacy ?
displayFOrmat ?
pour faire un POST sur une enum, il faut lui passer le @name décrit dans le noeud values, chaque @name a une correspondance en format = au format définit par le resType
-->





<!--
 if link ou collection.* resName +
* resTarget tout ca, ca va ensemble : le système de lien, resTarget va donner la ressource targetée par le lien. type
resType = type technique (long..) resType = link alors unbound='false' ou 'true'
If type = enumeration alors champ "values" rajouté et les valeurs sont dans values
pour faire un POST sur une enum, il faut lui passer le @name décrit dans le noeud values, chaque @name a une correspondance en format = au format définit par le resType
ail faut que la valeur poster soit conforme ,elle doit valider la dataPolicy . La dataPolicy peut soit controler la valeur (email invalide), soit transformé (cas du smartCase par exemple)
type dans les metadata = type de haut-niveau (nombre, text)
-->
