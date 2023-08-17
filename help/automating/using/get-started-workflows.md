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
source-wordcount: '553'
ht-degree: 38%

---

# 開始使用流程和資料管理 {#get-started-processes-data-management}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_workflows.svg" width="60px"><p><a href="#workflow-activities">工作流程活動</a></p></td><td><img src="assets/do-not-localize/icon_activities.svg" width="60px"><p><a href="../../automating/using/workflow-created-query-with-complement.md">使用案例</a></p></td><td><img src="assets/do-not-localize/icon_filter.svg" width="60px"><p><a href="#filter-data">篩選資料</a></p></td>
<td><img src="assets/do-not-localize/icon_manage.svg" width="60px"><p><a href="#import-export-data">匯入/匯出資料</a></p></td></tr>
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
> Adobe建議客戶不要同時執行超過20個作用中工作流程，並隨著時間安排工作流程執行的優先順序和分佈。 如需詳細資訊，請參閱中提供的最佳實務 [此頁面](../../automating/using/best-practices-workflows.md).

## 工作流程活動 {#workflow-activities}

<img src="assets/do-not-localize/icon_workflows.svg" width="60px">

提供各種活動來協助您設計工作流程。

[目標定位活動](../../automating/using/about-targeting-activities.md) 可讓您定義集合，並使用交集、等位或排除作業來分割或組合這些集合，以建立一或多個目標。

替換為 [執行活動](../../automating/using/about-execution-activities.md)，協調您的工作流程及其活動，同時 [頻道活動](../../automating/using/about-channel-activities.md) 可讓您合併Campaign Standard通訊頻道，以建立跨頻道工作流程。

最後， [資料管理活動](../../automating/using/about-data-management-activities.md) 可讓您操控資料庫的資料。

閱讀全文:

* [建立工作流程](../../automating/using/building-a-workflow.md)
* [執行工作流程](../../automating/using/about-workflow-execution.md)
* [工作流程最佳實務](../../automating/using/best-practices-workflows.md)

## 篩選資料 {#filter-data}

<img src="assets/do-not-localize/icon_filter.svg" width="60px">

善用 **查詢編輯器** 以篩選資料庫中的資料，並建立母體以更妥善地鎖定收件者。 查詢編輯器可用於在Campaign Standard中執行數個動作：建立查詢型別對象、定義傳遞目標或工作流程活動中的人口。

查詢編輯器隨附 **預先定義的篩選器和規則** 方便快速篩選。 不過，您也可以使用 **進階運算式編輯** 功能。 這可讓您手動輸入條件並使用函式，以形成自己的規則。

閱讀全文:

* [編輯查詢](../../automating/using/editing-queries.md)
* [進階運算式編輯](../../automating/using/advanced-expression-editing.md)
* [函式清單](../../automating/using/list-of-functions.md)

## 匯入/匯出資料 {#import-export-data}

<img src="assets/do-not-localize/icon_manage.svg" width="60px">

Campaign Standard隨附幾項 **資料管理功能** 以匯入及匯出資料。

[工作流程資料管理活動](../../automating/using/about-data-management-activities.md) 可讓您匯入資料、對欄位執行大量更新、接收或傳送檔案，或將未識別的資料連結至現有資源。

替換為 [匯入範本](../../automating/using/importing-data-with-import-templates.md)，透過簡化的匯入功能管理管理員定義的特定匯入型別。

[匯出記錄檔](../../automating/using/exporting-logs.md) 可讓您透過簡單的工作流程匯出記錄資料，讓您在自己的報告或BI工具中分析行銷活動的結果。

善用 [封裝](../../automating/using/managing-packages.md) 在不同的campaign執行個體之間交換資源，例如，複製執行個體的設定，或將資料從伺服器傳輸至另一個包含自訂資源的伺服器。

最後， [匯出清單](../../automating/using/exporting-lists.md) 可讓您從Campaign Standard匯出任何清單，例如測試設定檔清單、隔離區電子郵件地址清單等。

閱讀全文:

* [匯入和匯出資料](../../automating/using/about-data-import-and-export.md)
* [使用案例：匯出/匯入自訂資源](../../automating/using/exporting-importing-custom-resources.md)

## 額外資源

* [流程和資料管理教學課程影片](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/managing-processes-and-data/creating-a-workflow.html?lang=zh-Hant)
* [技術工作流程](../../administration/using/technical-workflows.md)
* [開始使用 Campaign Standard 資料模型](../../developing/using/get-started-data-model.md)
