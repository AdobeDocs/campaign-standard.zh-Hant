---
title: 開始使用流程和資料管理
description: 使用工作流程自動化程序、管理資料和對象、傳送訊息等。
audience: automating
content-type: reference
topic-tags: about-workflows-and-data-management
feature: Workflows
role: Data Architect
level: Beginner
exl-id: 26be942a-c252-458f-a590-eb235567ca67
source-git-commit: 6ca3ffe3ba2cf7629e511e4ba035b170b25ad79e
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# 開始使用流程和資料管理 {#get-started-processes-data-management}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_workflows.svg" width="60px"><p><a href="#workflow-activities">工作流活動</a></p></td><td><img src="assets/do-not-localize/icon_activities.svg" width="60px"><p><a href="../../automating/using/workflow-created-query-with-complement.md">使用案例</a></p></td><td><img src="assets/do-not-localize/icon_filter.svg" width="60px"><p><a href="#filter-data">篩選資料</a></p></td>
<td><img src="assets/do-not-localize/icon_manage.svg" width="60px"><p><a href="#import-export-data">導入/導出資料</a></p></td></tr>
</table>

Adobe Campaign 提供完整的圖形環境，讓您設計複雜程式，包括細分、行銷活動執行、檔案處理等。 例如，您可以使用工作流程從伺服器下載檔案、解壓縮，然後將其中的記錄匯入 Adobe Campaign 資料庫。

工作流程也可以讓使用者參與，例如向使用者指派工作或由他們核准已執行的工作。 這表示您可以指派工作給一或數個使用者，以處理內容或指定目標，並在傳送訊息前核准證明。

工作流程可用於不同的內容，例如：

* 定位以管理對象或傳送訊息。
* 資料管理 (ETL)，以操作資料。
* 將資料匯入 Campaign 資料庫。
* 技術流程，例如資料庫清理、復原追蹤資訊等。

>[!IMPORTANT]
>
> Adobe建議客戶不要同時運行20個以上的活動工作流執行，並建議客戶確定工作流執行的優先順序並將其分散。 有關詳細資訊，請參閱 [此頁](../../automating/using/best-practices-workflows.md)。

## 工作流活動 {#workflow-activities}

<img src="assets/do-not-localize/icon_workflows.svg" width="60px">

各種活動可幫助您設計工作流。

[目標活動](../../automating/using/about-targeting-activities.md) 允許您通過定義集和拆分或使用交集、聯合或排除操作組合這些集來構建一個或多個目標。

與 [執行活動](../../automating/using/about-execution-activities.md)，協調您的工作流及其活動，同時 [渠道活動](../../automating/using/about-channel-activities.md) 允許您將Campaign Standard通信通道組合起來建立跨通道工作流。

終於， [資料管理活動](../../automating/using/about-data-management-activities.md) 允許您處理資料庫中的資料。

閱讀全文:

* [建立工作流程](../../automating/using/building-a-workflow.md)
* [執行工作流程](../../automating/using/about-workflow-execution.md)
* [工作流程最佳實務](../../automating/using/best-practices-workflows.md)

## 篩選資料 {#filter-data}

<img src="assets/do-not-localize/icon_filter.svg" width="60px">

利用 **查詢編輯器** 從資料庫中篩選資料並構建填充，以更好地針對收件人。 查詢編輯器可用於在Campaign Standard中執行以下幾個操作：建立查詢類型訪問群體、定義傳遞目標或工作流活動中的總體。

查詢編輯器隨附 **預定義的篩選器和規則** 快速且方便的過濾。 但是，您也可以 **高級表達式編輯** 功能。 這允許您手動輸入條件和使用函式，以便形成您自己的規則。

閱讀全文:

* [編輯查詢](../../automating/using/editing-queries.md)
* [進階運算式編輯](../../automating/using/advanced-expression-editing.md)
* [函式清單](../../automating/using/list-of-functions.md)

## 導入/導出資料 {#import-export-data}

<img src="assets/do-not-localize/icon_manage.svg" width="60px">

Campaign Standard帶有 **資料管理功能** 導入和導出資料。

[工作流資料管理活動](../../automating/using/about-data-management-activities.md) 允許您導入資料、對欄位執行成批更新、接收或發送檔案，或將未標識的資料連結到現有資源。

與 [導入模板](../../automating/using/importing-data-with-import-templates.md)，通過簡化的導入功能管理管理員定義的某些類型的導入。

[導出日誌](../../automating/using/exporting-logs.md) 允許您通過簡單的工作流導出日誌資料，從而可以在您自己的報告或BI工具中分析營銷活動的結果。

利用 [包](../../automating/using/managing-packages.md) 在不同市場活動實例之間交換資源，例如複製實例的配置，或將資料從伺服器傳輸到包括自定義資源在內的另一個市場活動實例。

終於， [導出清單](../../automating/using/exporting-lists.md) 允許您從Campaign Standard中導出任何清單，例如，test配置檔案清單、隔離電子郵件地址清單等。

閱讀全文:

* [匯入和匯出資料](../../automating/using/about-data-import-and-export.md)
* [使用案例：匯出/匯入自訂資源](../../automating/using/exporting-importing-custom-resources.md)

## 額外資源

* [流程和資料管理教程視頻](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/managing-processes-and-data/creating-a-workflow.html?lang=zh-Hant)
* [技術工作流程](../../administration/using/technical-workflows.md)
* [開始使用 Campaign Standard 資料模型](../../developing/using/get-started-data-model.md)
