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
source-wordcount: '0'
ht-degree: 0%

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

市場活動使用的資料是通過在 **預定義資料模型**。 資料模型顯示一組與市場營銷相關的資源的現成SQL結構：交付、受眾、登錄頁、個人資料等。 每個資源都帶有關聯的篩選器，允許您瀏覽資源。

的 **診斷** 菜單，您可以列出由Campaign Standard生成的技術對象：資料架構、網頁、篩選器等，允許您監視資料模型和對其所做的任何更改。

閱讀全文:

* [資料模型概念](../../developing/using/data-model-concepts.md)
* [資料模型最佳實務](../../developing/using/data-model-best-practices.md)
* [資料模型說明](../../developing/using/datamodel-introduction.md)
* [監控資料模型變更](../../developing/using/monitoring-data-model-changes.md)

## 自訂資源 {#custom-resources}

<img src="assets/do-not-localize/icon_custom.svg" width="60px">

Campaign Standard允許您 **豐富了預定義的資料模型** 建立您自己的資源（例如添加「採購」或「產品」表），或使用新欄位擴展現有資源。 您還可以配置「市場活動」螢幕，以優化通過已建立的新資源和欄位的導航。

另外，您 **擴展Campaign StandardREST API** 以便在自定義資源配置檔案的API擴展欄位中公開。 例如，這允許您使用從計費系統生成的促銷代碼更新客戶的配置檔案。

閱讀全文:

* [新增或擴充資源](../../developing/using/key-steps-to-add-a-resource.md)
* [擴展API](../../developing/using/about-extending-the-api.md)
* [用例：使用新欄位擴展配置檔案資源](../../developing/using/extending-the-profile-resource-with-a-new-field.md)
* [用例：將預訂擴展到應用程式資源](../../developing/using/extending-the-subscriptions-to-an-application-resource.md)

## 使用API {#apis}

<img src="assets/do-not-localize/icon_api.svg" width="60px">

利用Campaign StandardAPI，為Adobe Campaign Standard建立整合，並通過將「活動」與您使用的技術面板對接來構建自己的生態系統。 [開始使用 Campaign Standard REST API](../../api/using/get-started-apis.md)

## 額外資源

* [匯出/匯入自訂資源](https://helpx.adobe.com/campaign/kb/acs-get-started-with-cusres.html)
* [將資料從 Campaign 匯出至 Adobe Experience Platform](../../integrating/using/export-campaign-data.md)
