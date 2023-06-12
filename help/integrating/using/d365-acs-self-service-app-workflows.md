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

此 **[!UICONTROL Workflows]** 頁面會列出技術工作流程及其狀態。

整合應用程式隨附三個工作流程：

![](assets/do-not-localize/d365-to-acs-ui-page-workflows.png)

**Microsoft Dynamics 365至Campaign**
* 傳送 *連絡人* 從Microsoft Dynamics 365移至Adobe Campaign
* *自訂實體*：將自訂表格從Microsoft Dynamics 365帶入Adobe Campaign。 [了解更多](../../integrating/using/d365-acs-using-the-integration.md#data-flows)
* 這也稱為 **入口** (指資料從Microsoft Dynamics 365匯入Adobe Campaign)

**促銷活動至Microsoft Dynamics 365**
* Adobe Campaign Standard的電子郵件行銷事件會傳送至Dynamics 365 （電子郵件傳送、開啟、按一下、彈回）。 [了解更多](../../integrating/using/d365-acs-using-the-integration.md#email-marketing-event-flow)
* 這也稱為 **出口** (指資料從Adobe Campaign輸出至Microsoft Dynamics 365)

**選擇加入/退出**

選擇退出狀態（例如denyList）可以從Microsoft Dynamics 365同步至Adobe Campaign，或從Adobe Campaign同步至Microsoft Dynamics 365。 資料也可以雙向同步（即資料雙向流動）。 [了解更多](../../integrating/using/d365-acs-self-service-app-data-sync.md#opt-in-out-wf)。

>[!IMPORTANT]
>
>強烈建議您停止 **Microsoft Dynamics 365至Campaign** 將變更發佈至Adobe Campaign Standard或Microsoft Dynamics 365之前的工作流程。 這些變更包括整合目前正在使用的資源/實體（及其相關欄位）、連結、識別碼欄等專案的更新。 若未這麼做，可能會導致資料遺失及/或工作流程意外停止。

## 工作流程待處理專案

此整合應用程式會先讀取資料，然後將資料寫入目的地。 此 **[!UICONTROL Backlog]** 欄指出已排入佇列並等待寫入的記錄數。 當您需要處理大量資料時（例如，您是第一次執行整合、您是重播資料等），此值預期會增加。

>[!NOTE]
>如果您的Microsoft Dynamics 365和/或Campaign記錄未更新，您應該先檢查是否有大量記錄等待寫入目的地。

## 工作流程狀態 {#workflow-status}

此 **[!UICONTROL Status]** 欄指示與工作流程相關聯的背景處理程式的狀態。 可能的值包括：

* **執行中**：程式目前正在執行，您的資料應進行同步。
* **已停止**：該程式目前未執行，因此您不應該預期資料應該同步。
* **正在啟動**：您已要求啟動工作流程處理。 應用程式尚未開始同步與此工作流程相關聯的資料，但您可以預期在幾分鐘後便會同步(此時會顯示以下專案的狀態： **執行中**)
* **失敗**：工作流程處理序正在執行中，但發生錯誤，且無法從這些錯誤中復原。

## 可用動作

可能的動作列於下方。

* **編輯**：按一下鉛筆圖示會傳送您至另一個頁面，讓您更新工作流程。 請記住，您所做的任何變更只有在停止工作流程並重新啟動它之後才會生效。

* **開始**：開始按鈕會要求啟動已停止的工作流程。 只有目前停止與工作流程關聯的程式時，此按鈕才會出現。 處理程式會先變更為「STARTING」，然後變更為「RUNNING」。 在工作流程處於「執行中」狀態之前，與工作流程關聯的資料不會開始同步。

   開始按鈕為切換按鈕。 如果工作流程程式已啟動，按鈕將變更為 **停止** 按鈕。

* **停止**：A **停止** 按鈕要求停止執行中的工作流程。 只有在與工作流程相關聯的程式目前正在執行時，此按鈕才會出現。

編輯工作流程時，您的更新不會立即併入執行中流程的規則，直到您停止工作流程，然後按一下 **開始** 按鈕。 然後，您的更新會合併到正在執行的程式中（程式返回之後） **執行中** state)。

警告指示已新增至 **停止** 按鈕讓您知道何時已(a)更新工作流程，但(b)尚未完成此工作流程的停止/開始。

![](assets/do-not-localize/d365-to-acs-icon-stop-with-changes.png)
