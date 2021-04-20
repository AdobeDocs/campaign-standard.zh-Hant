---
solution: Campaign Standard
product: campaign
title: 開始使用流程和資料管理
description: 使用工作流程自動化程序，管理資料和對象、傳送訊息等。
audience: automating
content-type: reference
topic-tags: about-workflows-and-data-management
feature: Workflows
role: Data Architect
level: Beginner
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '523'
ht-degree: 13%

---


# 開始使用流程和資料管理 {#get-started-processes-data-management}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_workflows.svg" width="60px"><p><a href="#workflow-activities">工作流程活動</a></p></td><td><img src="assets/do-not-localize/icon_activities.svg" width="60px"><p><a href="../../automating/using/workflow-created-query-with-complement.md">使用案例</a></p></td><td><img src="assets/do-not-localize/icon_filter.svg" width="60px"><p><a href="#filter-data">篩選資料</a></p></td>
<td><img src="assets/do-not-localize/icon_manage.svg" width="60px"><p><a href="#import-export-data">匯入／匯出資料</a></p></td></tr>
</table>

Adobe Campaign提供完整的圖形環境，讓您設計複雜的程式，包括區段、促銷活動執行、檔案處理等。 例如，您可以使用工作流程從伺服器下載檔案、解壓縮檔案，然後將其記錄匯入Adobe Campaign資料庫。

工作流程也可以讓使用者參與，方法是指派工作或讓他們核准已執行的工作。 這表示您可以指派工作給一或數個使用者，以處理內容或指定目標，並在傳送訊息前核准校樣。

工作流可用於不同的上下文，例如：

* 定位以管理觀眾或傳送訊息。
* 資料管理(ETL)，以控制資料。
* 將資料匯入促銷活動資料庫。
* 技術流程，例如資料庫清理、追蹤資訊的復原等。

## 工作流活動{#workflow-activities}

<img src="assets/do-not-localize/icon_workflows.svg" width="60px">

您可使用各種活動來協助您設計工作流程。

[定位](../../automating/using/about-targeting-activities.md) 活動允許您通過定義集並使用交叉點、聯合或排除操作拆分或組合這些集來構建一個或多個目標。

使用[執行活動](../../automating/using/about-execution-activities.md)來協調您的工作流及其活動，而[渠道活動](../../automating/using/about-channel-activities.md)則可讓您結合Campaign Standard通訊渠道以建立跨通道工作流程。

最後，[資料管理活動](../../automating/using/about-data-management-activities.md)可讓您控制資料庫中的資料。

顯示全文:

* [建立工作流程](../../automating/using/building-a-workflow.md)
* [執行工作流程](../../automating/using/about-workflow-execution.md)
* [工作流程最佳實務](../../automating/using/best-practices-workflows.md)

## 篩選資料{#filter-data}

<img src="assets/do-not-localize/icon_filter.svg" width="60px">

運用&#x200B;**查詢編輯器**&#x200B;來篩選資料庫中的資料，並建立人口族群，以更好地定位收件者。 查詢編輯器可用於在Campaign Standard中執行以下幾個操作：建立查詢類型對象、定義傳送目標或工作流程活動中的人口族群。

查詢編輯器隨附&#x200B;**預先定義的篩選器和規則**，以便快速且輕鬆地篩選。 不過，您也可以使用&#x200B;**進階運算式編輯**&#x200B;功能。 這可讓您手動輸入條件並使用函式，以便形成您自己的規則。

顯示全文:

* [編輯查詢](../../automating/using/editing-queries.md)
* [進階運算式編輯](../../automating/using/advanced-expression-editing.md)
* [函式清單](../../automating/using/list-of-functions.md)

## 匯入／匯出資料{#import-export-data}

<img src="assets/do-not-localize/icon_manage.svg" width="60px">

Campaign Standard提供數種&#x200B;**資料管理功能**&#x200B;以匯入和匯出資料。

[工作流程資料管](../../automating/using/about-data-management-activities.md) 理活動可讓您匯入資料、對欄位執行大量更新、接收或傳送檔案，或將未識別的資料連結至現有資源。

使用[Import templates](../../automating/using/importing-data-with-import-templates.md)，透過簡化的匯入功能管理管理員定義的特定匯入類型。

[匯出](../../automating/using/exporting-logs.md) 記錄可讓您透過簡單的工作流程匯出記錄資料，讓您能夠在自己的報表或BI工具中分析行銷宣傳的結果。

利用[Packages](../../automating/using/managing-packages.md)在不同促銷活動例項之間交換資源，例如複製例項的設定，或將資料從伺服器傳輸至其他伺服器，包括自訂資源。

最後，[匯出清單](../../automating/using/exporting-lists.md)可讓您從Campaign Standard匯出任何清單，例如測試設定檔清單、隔離電子郵件地址清單等。

顯示全文:

* [匯入和匯出資料](../../automating/using/about-data-import-and-export.md)
* [使用案例：匯出/匯入自訂資源](../../automating/using/exporting-importing-custom-resources.md)

## 其他資源

* [流程與資料管理教學課程影片](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/getting-started/create-workflow.html)
* [技術工作流程](../../administration/using/technical-workflows.md)
* [開始使用 Campaign Standard 資料模型](../../developing/using/get-started-data-model.md)
