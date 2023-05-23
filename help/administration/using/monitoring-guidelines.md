---
title: 監視指南
description: 本頁提供監視Campaign Standard的一般准則
audience: production
feature: Access Management
role: Admin
level: Experienced
exl-id: 5f25f2b2-ca41-4baf-ade2-42bbafb4790d
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 21%

---

# 監視指南 {#monitoring-guidelines}

<table>
<tr><td><img src="assets/do-not-localize/icon_system.svg" width="60px"><p><a href="#monitoring-system">監視系統</a></p></td>
<td><img src="assets/do-not-localize/icon_workflows.svg" width="60px"><p><a href="#moniroting-workflows">監控工作流程</a></p></td>
<td><img src="assets/do-not-localize/icon_send.svg" width="60px"><p><a href="#monitoring-deliveries">監視傳遞</a></p></td></tr>
</table>

Campaign Standard提供了多種監視實例的方法，以確保系統正常，並最終解決在設定工作流、發送遞送等時可能出現的問題。

## 監視系統 {#monitoring-system}

<img src="assets/do-not-localize/icon_system.svg" width="60px">

**系統通知**

Campaign Standard介面提供通知窗格，使您能夠隨時瞭解系統中發生的情況：事件狀態、系統更新、所需操作等。 [深入了解](../../start/using/interface-description.md#top-bar)


**技術工作流程**

技術工作流程是排程定期在伺服器上執行的操作或作業。要確保實例運行正常且正常，您需要確保它們始終處於啟動和運行狀態。 [深入了解](../../administration/using/technical-workflows.md)

**控制面板**

通過「控制面板」，您可以管理實例的幾個設定：URL權限、檢查您的實例詳細資訊，如伺服器的生成版本、監視活動配置檔案的使用情況等。 它還允許您監視連接到實例的SFTP伺服器上的可用空間。 [顯示全文](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=zh-Hant)。

>[!NOTE]
>
>所有管理員使用者都可存取控制面板。 授予使用者管理員存取權限的步驟已詳載於[本頁](https://experienceleague.adobe.com/docs/control-panel/using/discover-control-panel/managing-permissions.html?lang=zh-Hant#discover-control-panel)中。

**技術物件**

的 **[!UICONTROL Diagnosis]** 菜單是監控和分析應用程式生成的不同技術對象的關鍵工具：資料架構、網頁、批處理作業等。 [深入了解](../../developing/using/monitoring-data-model-changes.md)

**導出審核**

導出審核允許您監視對實例執行的導出：從工作流上載的檔案、清單導出以及從直接郵件下載的檔案。
[深入了解](../../administration/using/auditing-export-logs.md)

**授權**

使用 **[!UICONTROL Licenses]** 菜單，監視有關實例的資訊：已安裝的許可證、生成版本和條款協定接受。
[深入了解](../../administration/using/licenses.md)

## 監控工作流程 {#monitoring-workflows}

<img src="assets/do-not-localize/icon_workflows.svg" width="60px">

**最佳實務及疑難排解**

使用工作流時遵循最佳做法和故障排除指南有助於提高效能。
[深入了解](../../automating/using/best-practices-workflows.md)

**記錄和任務**

工作流日誌監視是分析工作流並確保它們正常運行的關鍵步驟。
[深入了解](../../automating/using/monitoring-workflow-execution.md#workflow-log-and-tasks)

**通知**

Campaign Standard允許您向主管發送通知以監視工作流的執行，並查看是否存在需要您注意的錯誤。
[深入了解](../../automating/using/monitoring-workflow-execution.md#error-management)

## 監視傳遞 {#monitoring-deliveries}

<img src="assets/do-not-localize/icon_send.svg" width="60px">

**傳遞度**

Campaign Standard提供了幾種可傳送的工具，以幫助您提高成功傳送的郵件數：交付吞吐量報告、發送時間優化、消息預覽、電子郵件呈現、隔離管理等。
[深入了解](../../sending/using/about-deliverability.md)

**傳遞**

發送郵件後，詳細日誌允許您監視交貨情況和衡量市場活動的成功程度，並跟蹤郵件收件人的行為。
[深入了解](../../sending/using/monitoring-a-delivery.md)

**傳遞警報**

使用「交付」警報功能，您可以設定將自動發送給一組用戶的有關交付執行的警報：發送或準備失敗、邊界率不佳、吞吐量低等。
[深入了解](../../sending/using/receiving-alerts-when-failures-happen.md)

**動態報告**

動態報告提供各種報告，幫助您隨時瞭解交貨的執行情況：收件、按收件人查看的多數交貨、交貨吞吐量等。
[深入了解](../../reporting/using/about-dynamic-reports.md)
