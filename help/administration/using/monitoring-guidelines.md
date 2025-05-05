---
title: 監視指南
description: 此頁面提供監督Campaign Standard的一般准則
audience: production
feature: Access Management
role: Admin
level: Experienced
exl-id: 5f25f2b2-ca41-4baf-ade2-42bbafb4790d
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 12%

---

# 監視指南 {#monitoring-guidelines}

<table>
<tr><td><img src="assets/do-not-localize/icon_system.svg" width="60px"><p><a href="#monitoring-system">監視系統</a></p></td>
<td><img src="assets/do-not-localize/icon_workflows.svg" width="60px"><p><a href="#moniroting-workflows">監視工作流程</a></p></td>
<td><img src="assets/do-not-localize/icon_send.svg" width="60px"><p><a href="#monitoring-deliveries">監視傳遞</a></p></td></tr>
</table>

Campaign Standard提供數種監視執行個體的方式，以確保您的系統健康且最終疑難排解設定工作流程、傳送傳遞等時可能發生的問題。

## 監視系統 {#monitoring-system}

<img src="assets/do-not-localize/icon_system.svg" width="60px">

**系統通知**

Campaign Standard介面會提供通知窗格，讓您隨時瞭解系統中發生的情況：事件狀態、系統更新、所需的動作等。 [閱讀更多](../../start/using/interface-description.md#top-bar)


**技術工作流程**

技術工作流程是排程定期在伺服器上執行的操作或工作。 為確保您的執行個體正常運作，您需要確保執行個體隨時啟動並執行。 [閱讀更多](../../administration/using/technical-workflows.md)

**控制面板**

「控制面板」可以讓您管理執行個體的多項設定：URL許可權、檢查執行個體詳細資訊（例如伺服器的組建版本）、監視作用中設定檔的使用情況等。 它也可讓您監視連線到執行個體的SFTP伺服器上的可用空間。 [閱讀全文](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=zh-Hant)。

>[!NOTE]
>
>所有管理員使用者都可存取控制面板。 授予使用者管理員存取權限的步驟已詳載於[本頁](https://experienceleague.adobe.com/docs/control-panel/using/discover-control-panel/managing-permissions.html?lang=zh-Hant#discover-control-panel)中。

**技術物件**

**[!UICONTROL Diagnosis]**&#x200B;功能表是用於監視和分析應用程式產生的不同技術物件的關鍵工具：資料結構描述、網頁、批次工作等。 [閱讀更多](../../developing/using/monitoring-data-model-changes.md)

**匯出稽核**

匯出稽核可讓您監視在執行個體上執行的匯出：從工作流程上傳的檔案、清單匯出以及從直接郵件訊息下載的檔案。
[閱讀更多](../../administration/using/auditing-export-logs.md)

**授權**

透過&#x200B;**[!UICONTROL Licenses]**&#x200B;功能表，監視執行個體的相關資訊：已安裝的授權、組建版本和條款合約接受。
[閱讀更多](../../administration/using/licenses.md)

## 監視工作流程 {#monitoring-workflows}

<img src="assets/do-not-localize/icon_workflows.svg" width="60px">

**最佳作法和疑難排解**

使用工作流程時，遵循最佳實務和疑難排解准則有助於改善效能。
[閱讀更多](../../automating/using/best-practices-workflows.md)

**記錄檔與工作**

工作流程記錄監視是分析工作流程並確保其正常執行的關鍵步驟。
[閱讀更多](../../automating/using/monitoring-workflow-execution.md#workflow-log-and-tasks)

**通知**

Campaign Standard可讓您傳送通知給主管，以監視工作流程的執行並檢視是否有任何需要您注意的錯誤。
[閱讀更多](../../automating/using/monitoring-workflow-execution.md#error-management)

## 監視傳遞 {#monitoring-deliveries}

<img src="assets/do-not-localize/icon_send.svg" width="60px">

**傳遞度**

Campaign Standard提供數種傳遞能力工具，協助您改善成功傳遞的訊息數量：傳遞輸送量報告、傳送時間最佳化、訊息預覽、電子郵件呈現、隔離管理等。
[閱讀更多](../../sending/using/about-deliverability.md)

**傳遞**

傳送訊息後，詳細的記錄檔可讓您監視傳遞並測量行銷活動是否成功，以及追蹤訊息收件者的行為。
[閱讀更多](../../sending/using/monitoring-a-delivery.md)

**傳遞警報**

透過傳送警報功能，您可以設定自動傳送給一組使用者有關傳送執行的警報：傳送或準備失敗、退回率不佳、輸送量低等。
[閱讀更多](../../sending/using/receiving-alerts-when-failures-happen.md)

**動態報告**

動態報告提供各種報告，協助您隨時瞭解傳遞的執行狀況：跳出數、收件者檢視次數最多的傳遞、傳遞的輸送量等。
[閱讀更多](../../reporting/using/about-dynamic-reports.md)
