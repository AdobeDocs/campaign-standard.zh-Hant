---
title: 整合應用程式工作流程
description: Campaign與Dynamics整合工作流程
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

# Campaign - Microsoft Dynamics 365整合工作流程

此 **[!UICONTROL Workflows]** 頁面列出技術工作流程及其狀態。

整合應用程式隨附三個工作流程：

![](assets/do-not-localize/d365-to-acs-ui-page-workflows.png)

**Microsoft Dynamics 365至Campaign**
* 傳送 *聯繫人* 從Microsoft Dynamics 365到Adobe Campaign
* *自訂實體*:將自訂表格從Microsoft Dynamics 365帶入Adobe Campaign。 [了解更多](../../integrating/using/d365-acs-using-the-integration.md#data-flows)
* 這也稱為 **入口** (指從Microsoft Dynamics 365進入Adobe Campaign的資料)

**促銷活動至Microsoft Dynamics 365**
* 來自Adobe Campaign Standard的電子郵件行銷事件會傳送至Dynamics 365（電子郵件傳送、開啟、按一下、退信）。 [了解更多](../../integrating/using/d365-acs-using-the-integration.md#email-marketing-event-flow)
* 這也稱為 **輸出** (指資料從Adobe Campaign輸出至Microsoft Dynamics 365)

**選擇加入/退出**

退出狀態（例如denyList）可從Microsoft Dynamics 365同步至Adobe Campaign，或從Adobe Campaign同步至Microsoft Dynamics 365。 資料也可以通過雙向同步（即資料雙向流動）。 [深入瞭解](../../integrating/using/d365-acs-self-service-app-data-sync.md#opt-in-out-wf)。

>[!IMPORTANT]
>
>強烈建議您停止 **Microsoft Dynamics 365至Campaign** 工作流程，再將變更發佈至Adobe Campaign Standard或Microsoft Dynamics 365。 這些變更包括整合目前正在使用的資源/實體（及其相關欄位）、連結、識別碼欄等的更新。 若未這麼做，可能會導致資料遺失和/或工作流程意外停止。

## 工作流程積壓

此整合應用程式會先讀取資料，然後將資料寫入目的地。 此 **[!UICONTROL Backlog]** 列指示已排隊並等待寫入的記錄數。 當您有大量資料要處理時（例如，您是第一次執行整合、您正在重播資料等），此值將會增加。

>[!NOTE]
>如果您的Microsoft Dynamics 365和/或促銷活動記錄未更新，您應先檢查是否有大量記錄等待寫入目的地。

## 工作流程狀態 {#workflow-status}

此 **[!UICONTROL Status]** 欄指示與工作流關聯的後台進程的狀態。 可能的值包括：

* **執行中**:該進程當前正在運行，應同步您的資料。
* **已停止**:此程式目前未執行，因此您不應期望資料已同步。
* **開始**:您已請求工作流進程啟動。 應用程式尚未開始同步與此工作流關聯的資料，但您可以預期它將在幾分鐘後(此時它將顯示 **執行中**)
* **失敗**:工作流進程正在運行，但遇到錯誤，無法從這些進程中恢復。

## 可用動作

可能的動作列於下方。

* **編輯**:按一下鉛筆圖示會將您傳送至另一個頁面，讓您對工作流程進行更新。 請記住，在停止工作流程並重新啟動之前，您所做的任何變更都不會生效。

* **開始**:「開始」按鈕會要求啟動已停止的工作流程。 只有與工作流程相關聯的程式目前停止時，才會顯示此按鈕。 流程將先變更為「STARTING」，然後變更為「RUNNING」。 在工作流程處於「執行中」狀態之前，與工作流程相關聯的資料將不會開始同步。

   「開始」按鈕是切換按鈕。 如果工作流程程式已啟動，按鈕將變更為 **停止** 按鈕。

* **停止**:A **停止** 按鈕會要求停止執行中的工作流程。 只有與工作流程相關聯的程式目前執行時，才會顯示此按鈕。

編輯工作流程時，在您停止工作流程並按一下 **開始** 按鈕。 然後，您的更新會整合到執行中的程式中(一旦程式返回 **執行中** 州)。

警告指示會新增至 **停止** 按鈕，通知您何時已(a)更新工作流程，但(b)尚未停止/開始此工作流程。

![](assets/do-not-localize/d365-to-acs-icon-stop-with-changes.png)
