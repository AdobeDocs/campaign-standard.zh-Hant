---
title: 開始使用 Campaign Standard 資料模型
description: 利用自訂欄位和資源讓 Campaign Standard 資料模型豐富化，並延伸 REST API 以公開延伸的欄位。
audience: automating
content-type: reference
topic-tags: about-workflows-and-data-management
feature: Data Model
role: Developer
level: Intermediate
exl-id: a8d15053-c20f-4334-a732-3b36cb00794d
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 31%

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

Campaign使用的資料是透過 **預先定義的資料模型**. 資料模型會針對一組行銷相關資源顯示現成可用的SQL結構：傳遞、對象、登錄頁面、設定檔等。 每個資源都會提供相關聯的篩選器，讓您導覽資源。

此 **診斷** 功能表中，您可以列出由Campaign Standard產生的技術物件：資料結構、網頁、篩選器等，可讓您監控資料模型及其任何變更。

閱讀全文:

* [資料模型概念](../../developing/using/data-model-concepts.md)
* [資料模型最佳實務](../../developing/using/data-model-best-practices.md)
* [資料模型說明](../../developing/using/datamodel-introduction.md)
* [監控資料模型變更](../../developing/using/monitoring-data-model-changes.md)

## 自訂資源 {#custom-resources}

<img src="assets/do-not-localize/icon_custom.svg" width="60px">

Campaign Standard可讓您 **豐富預先定義的資料模型** 建立您自己的資源（例如新增「購買」或「產品」表格），或使用新欄位擴充現有資源。 您也可以設定Campaign畫面，以最佳化導覽已建立的新資源和欄位。

此外，您也可以 **擴充Campaign StandardREST API** 以在自訂資源設定檔的API延伸欄位中公開。 舉例來說，這可讓您使用從計費系統產生的促銷代碼來更新客戶的設定檔。

閱讀全文:

* [新增或擴充資源](../../developing/using/key-steps-to-add-a-resource.md)
* [擴充API](../../developing/using/about-extending-the-api.md)
* [使用案例：使用新欄位擴充設定檔資源](../../developing/using/extending-the-profile-resource-with-a-new-field.md)
* [使用案例：將訂閱擴充至應用程式資源](../../developing/using/extending-the-subscriptions-to-an-application-resource.md)

## 使用API {#apis}

<img src="assets/do-not-localize/icon_api.svg" width="60px">

透過Campaign StandardAPI，建立Adobe Campaign Standard的整合，並將Campaign與您使用的技術面板結合，以建立您自己的生態系統。 [開始使用 Campaign Standard REST API](../../api/using/get-started-apis.md)

## 額外資源

* [匯出/匯入自訂資源](https://helpx.adobe.com/campaign/kb/acs-get-started-with-cusres.html)
* [將資料從 Campaign 匯出至 Adobe Experience Platform](../../integrating/using/export-campaign-data.md)
