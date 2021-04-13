---
solution: Campaign Standard
product: campaign
title: 開始使用 Campaign Standard 資料模型
description: 利用自訂欄位和資源讓 Campaign Standard 資料模型豐富化，並延伸 REST API 以公開延伸的欄位。
audience: automating
content-type: reference
topic-tags: about-workflows-and-data-management
feature: 資料模型
role: Developer
level: Intermediate
exl-id: a8d15053-c20f-4334-a732-3b36cb00794d
translation-type: tm+mt
source-git-commit: c5a9c27a2ce459dfd0f04159095bfc8a2cf4c0f6
workflow-type: tm+mt
source-wordcount: '340'
ht-degree: 28%

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

促銷活動使用的資料是透過預先定義之資料模型&#x200B;**中定義的不同資源來定義。**&#x200B;資料模型會針對一組行銷相關資源顯示現成可用的SQL結構：傳送、觀眾、登陸頁面、個人檔案等。 每個資源都提供關聯的篩選，讓您在資源中導覽。

**診斷**&#x200B;菜單允許您列出由Campaign Standard生成的技術對象：資料結構、網頁、篩選器等，讓您監控資料模型及對其進行的任何變更。

顯示全文:

* [資料模型概念](../../developing/using/data-model-concepts.md)
* [資料模型最佳實務](../../developing/using/data-model-best-practices.md)
* [資料模型說明](../../developing/using/datamodel-introduction.md)
* [監控資料模型變更](../../developing/using/monitoring-data-model-changes.md)

## 自訂資源 {#custom-resources}

<img src="assets/do-not-localize/icon_custom.svg" width="60px">

Campaign Standard可讓您&#x200B;**豐富預先定義的資料模型**，以建立您自己的資源（例如新增購買或產品表格），或使用新欄位擴充現有資源。 您也可以設定「促銷活動」畫面，以最佳化已建立之新資源和欄位的導覽。

此外，您可以&#x200B;**擴充Campaign StandardREST API**，以便在自訂資源描述檔的API擴充欄位中公開。 例如，這可讓您以帳單系統產生的促銷代碼來更新客戶的個人檔案。

顯示全文:

* [新增或擴充資源](../../developing/using/key-steps-to-add-a-resource.md)
* [擴充API](../../developing/using/about-extending-the-api.md)
* [使用案例：使用新欄位擴充描述檔資源](../../developing/using/extending-the-profile-resource-with-a-new-field.md)
* [使用案例：將預訂擴展到應用程式資源](../../developing/using/extending-the-subscriptions-to-an-application-resource.md)

## 使用API {#apis}

<img src="assets/do-not-localize/icon_api.svg" width="60px">

透過Campaign StandardAPI，建立Adobe Campaign Standard的整合，並將Campaign與您使用的技術面板結合，以建立您自己的生態系統。 [開始使用 Campaign Standard REST API](../../api/using/get-started-apis.md)

## 其他資源

* [匯出/匯入自訂資源](https://helpx.adobe.com/campaign/kb/acs-get-started-with-cusres.html)
* [將資料從Campaign匯出至Adobe Experience Platform](../../integrating/using/export-campaign-data.md)
