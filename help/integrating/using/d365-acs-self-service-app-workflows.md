---
title: 整合應用程式工作流
description: 市場活動和動態整合工作流
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
feature: Microsoft CRM Integration
role: Data Architect
level: Intermediate
exl-id: 51f07f08-5d57-4c4c-aff2-d03e5956ec6f
source-git-commit: e7fdaa4b1d77afdae8004a88bbe41bbbe75a3f3c
workflow-type: tm+mt
source-wordcount: '645'
ht-degree: 0%

---

# 市場活動 — MicrosoftDynamics 365整合工作流

的 **[!UICONTROL Workflows]** 列出技術工作流及其狀態。

整合應用程式附帶三個工作流：

![](assets/do-not-localize/d365-to-acs-ui-page-workflows.png)

**Microsoft動力365競選**
* 發送 *聯繫人* 從Microsoft動力365型飛機進入Adobe Campaign
* *自定義實體*:將自定義表從MicrosoftDynamics 365導入Adobe Campaign。 [了解更多](../../integrating/using/d365-acs-using-the-integration.md#data-flows)
* 這也稱為 **入口** (指從MicrosoftDynamics 365進入Adobe Campaign的資料)

**Microsoft動力365戰役**
* 從Adobe Campaign Standard發來的電子郵件營銷活動會發送到Dynamics 365（電子郵件發送、開啟、按一下、彈出）。 [了解更多](../../integrating/using/d365-acs-using-the-integration.md#email-marketing-event-flow)
* 這也稱為 **出口** (參考Adobe Campaign到Microsoft動力365的資料進展)

**選擇加入/退出**

選擇退出狀態（例如denyList）可以從MicrosoftDynamics 365同步到Adobe Campaign，或從Adobe Campaign同步到MicrosoftDynamics 365。 資料也可以通過雙向同步（即雙向資料流）。 [了解更多](../../integrating/using/d365-acs-self-service-app-data-sync.md#opt-in-out-wf)。

>[!IMPORTANT]
>
>強烈建議您停止 **Microsoft動力365競選** 將更改發佈到Adobe Campaign Standard或MicrosoftDynamics 365之前。 這些更改包括對資源/實體（及其關聯欄位）的更新、連結、標識符列等，這些當前正由整合使用。 如果不這樣做，可能會導致資料丟失和/或工作流意外停止。

## 工作流積壓

此整合應用程式首先讀取資料，然後將資料寫入目標。 的 **[!UICONTROL Backlog]** 列指示已排隊並等待寫入的記錄數。 當您有大量要處理的資料時（例如，您首次運行整合，正在重播資料等），此值預計會增長。

>[!NOTE]
>如果您的MicrosoftDynamics 365和/或市場活動記錄未更新，您應首先檢查是否有大量記錄等待寫入目標。

## 工作流狀態 {#workflow-status}

的 **[!UICONTROL Status]** 列指示與工作流關聯的後台進程的狀態。 可能的值為：

* **正在運行**:進程當前正在運行，您的資料應該同步。
* **已停止**:該進程當前未運行，因此您不應期望資料應同步。
* **開始**:您已請求啟動工作流進程。 應用程式尚未開始同步與此工作流關聯的資料，但您可以預期它將在幾分鐘後(此時它將顯示與 **正在運行**)
* **失敗**:工作流進程正在運行，但遇到錯誤，無法從這些進程中恢復。

## 可用操作

下面列出了可能的操作。

* **編輯**:按一下鉛筆表徵圖會將您發送到另一個頁面，該頁面將允許您對工作流進行更新。 請記住，在停止工作流並重新啟動之前，您所做的任何更改都不會生效。

* **開始**:「開始」按鈕請求啟動已停止的工作流。 僅當當前停止與工作流關聯的進程時，此按鈕才會出現。 進程將首先更改為「啟動」，然後更改為「運行」。 在工作流處於「正在運行」狀態之前，與工作流關聯的資料不會開始同步。

   「開始」按鈕是切換。 如果工作流進程已啟動，則按鈕將更改為 **停止** 按鈕

* **停止**:A **停止** 按鈕請求停止正在運行的工作流。 僅當與工作流關聯的進程當前正在運行時，此按鈕才會出現。

編輯工作流時，不會立即將更新納入正在運行的進程的規則中，直到您停止工作流，然後按一下 **開始** 按鈕 然後，更新將併入正在運行的進程(一旦該進程返回到 **正在運行** )。

在 **停止** 按鈕，以在以下情況下通知您：(a)已對工作流進行更新，但(b)尚未對此工作流執行「停止/啟動」。

![](assets/do-not-localize/d365-to-acs-icon-stop-with-changes.png)
