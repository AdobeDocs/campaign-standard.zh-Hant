---
solution: Campaign Standard
product: campaign
title: 監視指南
description: 本節介紹監控Campaign Standard的一般准則。
audience: production
content-type: reference
topic-tags: introduction
index: y
feature: 存取管理
role: Admin
level: Experienced
exl-id: 5f25f2b2-ca41-4baf-ade2-42bbafb4790d
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '507'
ht-degree: 20%

---

# 監視指南 {#monitoring-guidelines}

<table>
<tr><td><img src="assets/do-not-localize/icon_system.svg" width="60px"><p><a href="#monitoring-system">監控系統</a></p></td>
<td><img src="assets/do-not-localize/icon_workflows.svg" width="60px"><p><a href="#moniroting-workflows">監控工作流程</a></p></td>
<td><img src="assets/do-not-localize/icon_send.svg" width="60px"><p><a href="#monitoring-deliveries">監視傳遞</a></p></td></tr>
</table>

Campaign Standard提供數種監控執行個體的方式，以確保您的系統運作正常，並最終疑難排解在設定工作流程、傳送傳遞等作業時可能發生的問題。

## 監控系統 {#monitoring-system}

<img src="assets/do-not-localize/icon_system.svg" width="60px">

**系統通知**

Campaign Standard介面提供通知窗格，可讓您隨時了解系統中發生的情況：事件狀態、系統更新、所需動作等。 [顯示全文](../../start/using/interface-description.md#top-bar)


**技術工作流程**

技術工作流程是排程定期在伺服器上執行的操作或作業。為確保您的執行個體正常運作，您必須確定執行個體一律正常運作。 [顯示全文](../../administration/using/technical-workflows.md)

**控制面板**

「控制面板」可讓您管理執行個體的數個設定：URL權限、檢查您的執行個體詳細資訊，例如伺服器的組建版本、監視作用中設定檔的使用情況等。 它也可讓您監視連線至執行個體之SFTP伺服器上的可用空間。 [顯示全文](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=zh-Hant)。

>[!NOTE]
>
>所有管理員使用者都可存取控制面板。 授予使用者管理員存取權限的步驟已詳載於[本頁](https://experienceleague.adobe.com/docs/control-panel/using/discover-control-panel/managing-permissions.html?lang=en#discover-control-panel)中。

**技術物件**

**[!UICONTROL Diagnosis]**&#x200B;菜單是監視和分析應用程式生成的不同技術對象的關鍵工具：資料結構、網頁、批次作業等。 [顯示全文](../../developing/using/monitoring-data-model-changes.md)

**匯出稽核**

匯出稽核可讓您監控執行個體上執行的匯出：從工作流程上傳的檔案、清單匯出和從直接郵件下載的檔案。
[顯示全文](../../administration/using/auditing-export-logs.md)

**授權**

使用&#x200B;**[!UICONTROL Licenses]**功能表，監視有關實例的資訊：已安裝的許可證、版本和條款協定接受。
[顯示全文](../../administration/using/licenses.md)

## 監控工作流程 {#monitoring-workflows}

<img src="assets/do-not-localize/icon_workflows.svg" width="60px">

**最佳實務及疑難排解**

使用工作流程時遵循最佳實務和疑難排解准則，有助於改善效能。
[顯示全文](../../automating/using/best-practices-workflows.md)

**記錄檔和任務**

工作流程記錄監控是分析工作流程並確保其正常運作的關鍵步驟。
[顯示全文](../../automating/using/monitoring-workflow-execution.md#workflow-log-and-tasks)

**通知**

Campaign Standard可讓您傳送通知給主管，以監控工作流程的執行，並查看是否有任何需要您注意的錯誤。
[顯示全文](../../automating/using/monitoring-workflow-execution.md#error-management)

## 監視傳遞 {#monitoring-deliveries}

<img src="assets/do-not-localize/icon_send.svg" width="60px">

**傳遞度**

Campaign Standard提供數種傳遞工具，可協助您改善成功傳送的訊息數量：傳遞吞吐量報告、傳送時間最佳化、訊息預覽、電子郵件呈現、隔離管理等。
[顯示全文](../../sending/using/about-deliverability.md)

**傳遞**

傳送訊息後，詳細記錄可讓您監控傳送並測量行銷活動的成功，以及追蹤訊息收件者的行為。
[顯示全文](../../sending/using/monitoring-a-delivery.md)

**傳送警報**

透過「傳送警報」功能，您可以設定將自動傳送至一組使用者以執行傳送的警報：發送或準備失敗、跳出率差、吞吐量低等。
[顯示全文](../../sending/using/receiving-alerts-when-failures-happen.md)

**動態報告**

動態報告提供各種報告，協助您不斷得知傳送的執行情形：彈回數、收件者檢視次數最多的傳送、傳送的總處理量等。
[顯示全文](../../reporting/using/about-dynamic-reports.md)
