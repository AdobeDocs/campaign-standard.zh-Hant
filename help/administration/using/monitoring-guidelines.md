---
title: 監控准則
description: 本節提供監控促銷活動標準的一般准則。
page-status-flag: never-activated
uuid: cf0d782d-47bf-40ae-ab6f-d1d47fa15792
contentOwner: sauviat
products: SG_CAMPAIGN/CLASSIC
audience: production
content-type: reference
topic-tags: introduction
discoiquuid: 8b33e6af-15c3-4b30-8ad6-d76a1f33be21
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b4bac585ec25340d1f1d047f9a1f8dcd8e243821
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 6%

---


# 監控准則 {#monitoring-guidelines}

<table>
<tr><td><img src="assets/do-not-localize/icon_system.svg" width="60px"><p><a href="#monitoring-system">監控系統</a></p></td>
<td><img src="assets/do-not-localize/icon_workflows.svg" width="60px"><p><a href="#moniroting-workflows">監控工作流程</a></p></td>
<td><img src="assets/do-not-localize/icon_send.svg" width="60px"><p><a href="#monitoring-deliveries">監控傳送</a></p></td></tr>
</table>

Campaign Standard提供數種監控例項的方式，以確保您的系統正常運作，並最終疑難排解在設定工作流程、傳送傳送等時可能發生的問題。

## 監控系統 {#monitoring-system}

<img src="assets/do-not-localize/icon_system.svg" width="60px">

**系統通知**「促銷活動標準」介面提供通知窗格，可讓您隨時得知系統發生的情況： 事件狀態、系統更新、需要的動作等。 [詳細內容](../../start/using/interface-description.md#top-bar)


**技術工作**&#x200B;流程技術工作流程是計畫定期在伺服器上執行的作業或工作。 為確保您的例項是健康且正常運作，您必須確保它們一律正常運作。 [詳細內容](../../administration/using/technical-workflows.md)

**控制面板**「控制面板」可讓您管理數個執行個體的設定： URL權限、檢查您的例項詳細資訊，例如伺服器的建置版本、監視作用中的設定檔使用情況等。 它還允許您監視連接到實例的SFTP伺服器上的可用空間。 [詳細內容](https://docs.adobe.com/content/help/zh-Hant/control-panel/using/control-panel-home.html)。

>[!NOTE]
>
>請注意，「控制面板」僅供管理員使用者存取，可供所有使用Adobe Managed Services的客戶使用。

**技術對**&#x200B;像菜 **[!UICONTROL Diagnosis]** 單是監控和分析應用程式生成的不同技術對象的關鍵工具： 資料結構、網頁、批次工作等。 [詳細內容](../../developing/using/monitoring-data-model-changes.md)

**導出審核**導出審核允許您監視對實例執行的導出： 從工作流程上傳的檔案、清單匯出和從直接郵件訊息下載的檔案。
[詳細內容](../../administration/using/auditing-export-logs.md)

**授權**&#x200B;透過功能 **[!UICONTROL Licenses]** 表，監控您例項的相關資訊： 安裝的授權、建置版本和條款合約接受。
[詳細內容](../../administration/using/licenses.md)

## 監控工作流程 {#monitoring-workflows}

<img src="assets/do-not-localize/icon_workflows.svg" width="60px">

**最佳實務與疑難排解**使用工作流程時，遵循最佳實務與疑難排解准則有助於改善效能。
[詳細內容](../../automating/using/best-practices-workflows.md)

**記錄檔和工作**工作記錄檔監控是分析工作流程並確保工作流程正常執行的關鍵步驟。
[詳細內容](../../automating/using/monitoring-workflow-execution.md#workflow-log-and-tasks)

**Notifications**Campaign Standard可讓您傳送通知給主管，以監控您的工作流的執行情況，並查看是否有任何需要您注意的錯誤。
[詳細內容](../../automating/using/monitoring-workflow-execution.md#error-management)

## 監控傳送 {#monitoring-deliveries}

<img src="assets/do-not-localize/icon_send.svg" width="60px">

**Deliverability**Campaign Standard提供數種傳送功能工具，可協助您改善成功傳送訊息的數量： 傳送傳送處理報告、傳送時間最佳化、訊息預覽、電子郵件轉譯、隔離管理等。
[詳細內容](../../sending/using/about-deliverability.md)

**傳送**傳送訊息一經傳送，詳細記錄檔可讓您監控傳送情況並評估促銷活動的成功，以及追蹤訊息收件者的行為。
[詳細內容](../../sending/using/monitoring-a-delivery.md)

**傳送警**報使用「傳送警報」功能，您可以設定警報，將自動傳送給一組使用者，以瞭解傳送的執行情況： 發送或準備失敗，跳出率不高，吞吐量低等。
[詳細內容](../../sending/using/receiving-alerts-when-failures-happen.md)

**動態報表**動態報表提供多種報表，協助您隨時得知傳送的執行情形： 彈回數、依收件者檢視的絕大多數版本、傳送的總處理量等。
[詳細內容](../../reporting/using/about-dynamic-reports.md)
