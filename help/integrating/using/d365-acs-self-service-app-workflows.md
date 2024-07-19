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
source-wordcount: '658'
ht-degree: 0%

---

# Campaign - Microsoft Dynamics 365整合工作流程

**[!UICONTROL Workflows]**&#x200B;頁面列出技術工作流程及其狀態。

整合應用程式隨附三個工作流程：

![](assets/do-not-localize/d365-to-acs-ui-page-workflows.png)

**Microsoft Dynamics 365至Campaign**
* 從Microsoft Dynamics 365傳送&#x200B;*個連絡人*&#x200B;至Adobe Campaign
* *自訂實體*：從Microsoft Dynamics 365將自訂表格匯入Adobe Campaign。 [了解更多](../../integrating/using/d365-acs-using-the-integration.md#data-flows)
* 這也稱為&#x200B;**輸入** (指從Microsoft Dynamics 365到Adobe Campaign的資料輸入)

**促銷活動至Microsoft Dynamics 365**
* Adobe Campaign Standard的電子郵件行銷事件會傳送至Dynamics 365 （電子郵件傳送、開啟、按一下、退回）。 [了解更多](../../integrating/using/d365-acs-using-the-integration.md#email-marketing-event-flow)
* 這也稱為&#x200B;**輸出** (指資料從Adobe Campaign輸出至Microsoft Dynamics 365)

**選擇加入/退出**

選擇退出狀態（例如，denyList）可以從Microsoft Dynamics 365同步至Adobe Campaign，或從Adobe Campaign同步至Microsoft Dynamics 365。 資料也可以雙向同步（即資料雙向流動）。 [了解更多](../../integrating/using/d365-acs-self-service-app-data-sync.md#opt-in-out-wf)。

>[!IMPORTANT]
>
>強烈建議您先停止&#x200B;**Microsoft Dynamics 365至Campaign**&#x200B;工作流程，再發佈變更至Adobe Campaign Standard或Microsoft Dynamics 365。 這些變更包括整合目前正在使用的資源/實體（及其相關欄位）、連結、識別碼欄等……的更新。 若未這麼做，可能會導致資料遺失及/或工作流程意外停止。

## 工作流程待處理專案

此整合應用程式會先讀取資料，然後將資料寫入目的地。 **[!UICONTROL Backlog]**&#x200B;資料行指出已排入佇列並等待寫入的記錄數目。 當您需要處理大量資料時（例如，您是第一次執行整合、您是重播資料等），此值預期會增加。

>[!NOTE]
>如果您的Microsoft Dynamics 365和/或Campaign記錄未更新，您應該先檢查是否有大量記錄等待寫入目的地。
>

## 工作流程狀態 {#workflow-status}

**[!UICONTROL Status]**&#x200B;欄指出與工作流程關聯的背景處理程式的狀態。 可能的值包括：

* **正在執行**：處理序目前正在執行，您的資料應該要同步處理。
* **已停止**：處理序目前未執行，所以您不應該期望資料應該同步。
* **正在啟動**：您已要求啟動工作流程處理。 應用程式尚未開始同步處理與此工作流程關聯的資料，但您可以預期它會在幾分鐘後執行（屆時會顯示&#x200B;**正在執行**&#x200B;的狀態）
* **失敗**：工作流程處理序正在執行，但是發生錯誤，而且無法從這些錯誤復原。

## 可用動作

可能的動作列於下方。

* **編輯**：按一下鉛筆圖示會將您傳送到另一個頁面，讓您更新工作流程。 請記住，您所做的任何變更，只有在停止工作流程並重新啟動它之後，才會生效。

* **開始**：「開始」按鈕要求啟動已停止的工作流程。 只有目前停止與工作流程關聯的程式時，此按鈕才會出現。 處理程式會先變更為「STARTING」，然後再變更為「RUNNING」。 在工作流程處於「執行中」狀態時，與工作流程關聯的資料才會開始同步。

  開始按鈕為切換按鈕。 如果工作流程程式已經啟動，按鈕將變更為&#x200B;**停止**&#x200B;按鈕。

* **停止**： **停止**&#x200B;按鈕要求停止執行中的工作流程。 只有在與工作流程關聯的程式目前正在執行時，此按鈕才會出現。

當您編輯工作流程時，您的更新不會立即併入執行中的處理序規則，直到您停止工作流程，然後按一下&#x200B;**開始**&#x200B;按鈕為止。 然後，您的更新會合併到執行中的處理序中（一旦處理序返回&#x200B;**RUNNING**&#x200B;狀態）。

**停止**&#x200B;按鈕已新增警告指示，讓您知道您(a)已更新工作流程，但(b)尚未完成此工作流程的停止/開始。

![](assets/do-not-localize/d365-to-acs-icon-stop-with-changes.png)
