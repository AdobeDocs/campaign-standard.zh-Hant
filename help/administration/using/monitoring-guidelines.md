---
solution: Campaign Standard
product: campaign
title: 監視准則
description: 本節介紹監控Campaign Standard的一般准則。
audience: production
content-type: reference
topic-tags: introduction
index: y
feature: 存取管理
role: 管理員
level: 經驗豐富
translation-type: tm+mt
source-git-commit: 7979d8fd88b93a1cdd7b5a11bb66e894ab12f1c2
workflow-type: tm+mt
source-wordcount: '511'
ht-degree: 14%

---


# 監視准則 {#monitoring-guidelines}

<table>
<tr><td><img src="assets/do-not-localize/icon_system.svg" width="60px"><p><a href="#monitoring-system">監控系統</a></p></td>
<td><img src="assets/do-not-localize/icon_workflows.svg" width="60px"><p><a href="#moniroting-workflows">監控工作流程</a></p></td>
<td><img src="assets/do-not-localize/icon_send.svg" width="60px"><p><a href="#monitoring-deliveries">監視傳遞</a></p></td></tr>
</table>

Campaign Standard提供數種監控例項的方式，以確保您的系統正常運作，並最終排解在設定工作流程、傳送傳送等時可能發生的問題。

## 監視系統{#monitoring-system}

<img src="assets/do-not-localize/icon_system.svg" width="60px">

**系統通知**

Campaign Standard介面提供通知窗格，可讓您隨時得知系統發生的情況：事件狀態、系統更新、需要的動作等。 [顯示全文](../../start/using/interface-description.md#top-bar)


**技術工作流程**

技術工作流程是排程定期在伺服器上執行的操作或作業。為確保您的例項是健康且正常運作，您必須確保它們一律正常運作。 [顯示全文](../../administration/using/technical-workflows.md)

**控制面板**

「控制面板」可讓您管理數個例項的設定：URL權限、檢查您的例項詳細資訊，例如伺服器的建置版本、監視作用中的設定檔使用情況等。 它還允許您監視連接到實例的SFTP伺服器上的可用空間。 [顯示全文](https://docs.adobe.com/content/help/zh-Hant/control-panel/using/control-panel-home.html)。

>[!NOTE]
>
>所有管理員使用者都可存取控制面板。 授予使用者管理員存取權的步驟詳見[本頁](https://experienceleague.adobe.com/docs/control-panel/using/discover-control-panel/managing-permissions.html?lang=en#discover-control-panel)。

**技術物件**

**[!UICONTROL Diagnosis]**&#x200B;功能表是監控和分析應用程式所產生的不同技術物件的重要工具：資料結構、網頁、批次工作等。 [顯示全文](../../developing/using/monitoring-data-model-changes.md)

**匯出稽核**

匯出稽核可讓您監控執行個體的匯出：從工作流程上傳的檔案、清單匯出和從直接郵件訊息下載的檔案。
[顯示全文](../../administration/using/auditing-export-logs.md)

**授權**

使用&#x200B;**[!UICONTROL Licenses]**功能表，監控您的例項相關資訊：安裝的授權、建置版本和條款合約接受。
[顯示全文](../../administration/using/licenses.md)

## 監控工作流程 {#monitoring-workflows}

<img src="assets/do-not-localize/icon_workflows.svg" width="60px">

**最佳實務及疑難排解**

使用工作流程時，請遵循最佳實務和疑難排解指引，有助於改善效能。
[顯示全文](../../automating/using/best-practices-workflows.md)

**記錄檔和工作**

工作流程記錄監控是分析工作流程並確保其正常執行的關鍵步驟。
[顯示全文](../../automating/using/monitoring-workflow-execution.md#workflow-log-and-tasks)

**通知**

Campaign Standard可讓您傳送通知給主管，以監控工作流程的執行情況，並查看是否有任何需要您注意的錯誤。
[顯示全文](../../automating/using/monitoring-workflow-execution.md#error-management)

## 監視傳遞{#monitoring-deliveries}

<img src="assets/do-not-localize/icon_send.svg" width="60px">

**傳送能力**

Campaign Standard提供多種傳遞性工具，可協助您改善成功傳送訊息的數量：傳送吞吐量報告、傳送時間最佳化、訊息預覽、電子郵件轉譯、隔離管理等。
[顯示全文](../../sending/using/about-deliverability.md)

**傳遞**

在傳送訊息後，詳細記錄可讓您監控傳送情況並評估促銷活動的成功程度，以及追蹤訊息收件者的行為。
[顯示全文](../../sending/using/monitoring-a-delivery.md)

**傳送警報**

使用「傳送警報」功能，您可以設定警報，該警報將自動傳送給一組使用者，告知傳送的執行：發送或準備失敗，跳出率不高，吞吐量低等。
[顯示全文](../../sending/using/receiving-alerts-when-failures-happen.md)

**動態報告**

動態報表提供多種報表，協助您隨時得知傳送的執行情形：彈回數、收件者檢視的傳送次數最多、傳送的總處理量等。
[顯示全文](../../reporting/using/about-dynamic-reports.md)
