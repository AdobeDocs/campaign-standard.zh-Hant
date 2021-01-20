---
title: 整合應用程式工作流程
description: 促銷活動與動態整合工作流程
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
translation-type: tm+mt
source-git-commit: 6be7a20cde8fcaee73972b8919765ea631f2f1ee
workflow-type: tm+mt
source-wordcount: '645'
ht-degree: 0%

---


# Campaign - Microsoft Dynamics 365整合工作流程

**[!UICONTROL Workflows]**&#x200B;頁面列出技術工作流程及其狀態。

整合應用程式提供三個工作流程：

![](assets/d365-to-acs-ui-page-workflows.png)

**Microsoft Dynamics 365 to Campaign**
* 將&#x200B;*連絡人*&#x200B;從Microsoft Dynamics 365傳送至Adobe Campaign
* *自訂實體*:將自訂表格從Microsoft Dynamics 365匯入Adobe Campaign。[進一步瞭解](../../integrating/using/d365-acs-using-the-integration.md#data-flows)
* 這也稱為&#x200B;**Ingress**（指從Microsoft Dynamics 365傳入Adobe Campaign的資料）

**Campaign to Microsoft Dynamics 365**
* 從Adobe Campaign Standard傳送電子郵件行銷活動至Dynamics 365（電子郵件傳送、開啟、按一下、彈回）。 [進一步瞭解](../../integrating/using/d365-acs-using-the-integration.md#email-marketing-event-flow)
* 這也稱為&#x200B;**Egress**（指Adobe Campaign到Microsoft Dynamics 365的資料匯出）

**選擇加入／退出**

退出狀態（例如denyList）可從Microsoft Dynamics 365同步到Adobe Campaign，或從Adobe Campaign同步到Microsoft Dynamics 365。 資料也可以通過雙向同步（即雙向資料流）。 [進一步瞭解](../../integrating/using/d365-acs-self-service-app-data-sync.md#opt-in-out-wf)。

>[!IMPORTANT]
>
>強烈建議您先停止&#x200B;**Microsoft Dynamics 365至Campaign**&#x200B;工作流程，再發佈Adobe Campaign Standard或Microsoft Dynamics 365的變更。 這些變更包括對整合目前使用的資源／實體（及其相關欄位）、連結、識別碼欄等的更新。 若無法這麼做，可能導致資料遺失及／或工作流程意外停止。

## 工作流程積壓

此整合應用程式會先讀取資料，然後將資料寫入目標。 **[!UICONTROL Backlog]**&#x200B;列指示已排隊並等待寫入的記錄數。 當您有大量資料要處理時（例如您第一次執行整合、您正在重新播放資料等），此值預期會增加。

>[!NOTE]
>如果您的Microsoft Dynamics 365和／或促銷活動記錄未更新，您應先檢查是否有大量記錄等待寫入目標。


## 工作流程狀態{#workflow-status}

**[!UICONTROL Status]**&#x200B;欄會指出與工作流程相關聯的背景進程狀態。 可能的值包括：

* **正在運行**:該進程當前正在運行，您的資料應同步。
* **已停止**:此程式目前尚未執行，因此您不應期望您的資料能同步化。
* **開始**:您已要求啟動工作流進程。應用程式尚未開始同步與此工作流程相關的資料，但您可以預期會在幾分鐘後（屆時它會顯示&#x200B;**RUNNING**&#x200B;的狀態）
* **失敗**:工作流進程正在運行，但它們遇到錯誤，無法從中恢復。

## 可用動作

可能的動作列於下方。

* **編輯**:按一下鉛筆圖示會將您傳送至另一個可讓您更新工作流程的頁面。請記住，您所做的任何變更都必須先停止工作流程再重新啟動，才會生效。

* **開始**:「開始」按鈕會要求啟動已停止的工作流。僅當與工作流關聯的進程當前停止時，此按鈕才會顯示。 流程將首先變更為「開始」，然後變更為「執行中」。 在工作流處於「正在運行」狀態之前，與工作流關聯的資料將不會開始同步。

   開始按鈕是切換按鈕。 如果工作流進程已經啟動，則按鈕將更改為&#x200B;**Stop**&#x200B;按鈕。

* **停止**:「停 **** 止」按鈕會要求停止執行中的工作流程。僅當與工作流關聯的進程當前正在運行時，此按鈕才會顯示。

編輯工作流時，您的更新不會立即併入正在運行的進程的規則中，直到您停止工作流，然後按一下&#x200B;**開始**&#x200B;按鈕。 然後，您的更新會併入執行中的進程中（一旦進程返回&#x200B;**RUNNING**&#x200B;狀態）。

在&#x200B;**Stop**&#x200B;按鈕中添加警告指示，以告知您何時(a)更新了工作流，但(b)尚未執行此工作流的「停止／開始」。

![](assets/d365-to-acs-icon-stop-with-changes.png)
