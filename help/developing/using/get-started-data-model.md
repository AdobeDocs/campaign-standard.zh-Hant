---
title: 開始使用 Campaign Standard 資料模型
description: 以自訂欄位和資源豐富Campaign Standard資料模型，並擴充REST API以公開延伸欄位。
page-status-flag: never-activated
uuid: 7c1e8cea-90d0-491f-ab8f-6cd69f8a6c3b
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: about-workflows-and-data-management
discoiquuid: 40503917-7a53-4d99-96a4-57aa9e98ec87
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 24%

---


# 開始使用 Campaign Standard 資料模型 {#get-started-data-model}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_datamodel.svg" width="60px"><p><a href="#data-model">資料模型</a></p></td>
<td><img src="assets/do-not-localize/icon_custom.svg" width="60px"><p><a href="#custom-resources">自訂資源</a></p></td><td><img src="assets/do-not-localize/icon_api.svg" width="60px"><p><a href="#custom-resources">使用API</a></p></td></tr>
</table>

使用您自己的欄位和資源擴充 Campaign Standard 資料模型，並將所有資料模型變更監視為單一檢視。

## 資料模型 {#data-model}

<img src="assets/do-not-localize/icon_datamodel.svg" width="60px">

促銷活動使用的資料是透過預先定義的資料模型中定義的 **不同資源來定義**。 資料模型會針對一組行銷相關資源顯示現成可用的SQL結構：傳送、觀眾、登陸頁面、個人檔案等。 每個資源都提供關聯的篩選，讓您在資源中導覽。

「診 **斷** 」功能表可讓您列出Campaign Standard產生的技術物件：資料結構、網頁、篩選器等，讓您監控資料模型及對其進行的任何變更。

顯示全文:

* [資料模型概念](../../developing/using/data-model-concepts.md)
* [資料模型最佳實務](../../developing/using/data-model-best-practices.md)
* [資料模型說明](../../developing/using/datamodel-introduction.md)
* [監控資料模型變更](../../developing/using/monitoring-data-model-changes.md)

## 自訂資源 {#custom-resources}

<img src="assets/do-not-localize/icon_custom.svg" width="60px">

Campaign Standard可讓您豐 **富預先定義的資料模型** ，以建立您自己的資源（例如新增「購買」或「產品」表格），或以新欄位擴充現有資源。 您也可以設定「促銷活動」畫面，以最佳化已建立之新資源和欄位的導覽。

此外，您可以 **擴充Campaign Standard REST API** ，以便在自訂資源設定檔的API擴充欄位中公開。 例如，這可讓您以帳單系統產生的促銷代碼來更新客戶的個人檔案。

顯示全文:

* [新增或擴充資源](../../developing/using/key-steps-to-add-a-resource.md)
* [擴充API](../../developing/using/about-extending-the-api.md)
* [使用案例：使用新欄位擴充描述檔資源](../../developing/using/extending-the-profile-resource-with-a-new-field.md)
* [使用案例：將預訂擴展到應用程式資源](../../developing/using/extending-the-subscriptions-to-an-application-resource.md)

## 使用API {#apis}

<img src="assets/do-not-localize/icon_api.svg" width="60px">

透過Campaign Standard API，建立Adobe Campaign Standard的整合，並將Campaign與您使用的技術面板結合，以建立您自己的生態系統。 [開始使用 Campaign Standard REST API](../../api/using/get-started-apis.md)

## 其他資源

* [關於 Adobe Experience Platform Data Connector](../../developing/using/aep-about-data-connector.md)
* [建立自訂資源（視訊）](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/developing/custom-resources-develop/creating-custom-resources.html)
* [匯出/匯入自訂資源](https://helpx.adobe.com/campaign/kb/acs-get-started-with-cusres.html)
