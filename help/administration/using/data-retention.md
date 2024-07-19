---
title: 資料保留
description: 瞭解標準表格的預設保留值
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 01cfa2a0-4ff5-4520-a515-11676de82528
source-git-commit: 2e81a05b1b647991250d13d7d37f5da275a8db44
workflow-type: tm+mt
source-wordcount: '395'
ht-degree: 5%

---

# 資料保留{#data-retention}

Campaign中的標準記錄表具有預設的保留期間，可限制其資料儲存持續時間，以避免系統過載。

資料保留設定是由Adobe技術管理員在實施期間所設定，每個實作的值可能會因客戶需求而有所不同。

請洽詢Adobe顧問或技術管理員，以進一步瞭解適用於您環境的保留期間，或設定自訂保留期間。

請注意，使用標準工作流程功能，即可設定任何自訂表格的保留期間。

以下是標準表格的預設保留期間。 Adobe會儘可能根據您的資料使用情況，建議您改用建議的保留期間，以改善Campaign執行個體的效能。

* **整合追蹤**： 6個月（建議： 1個月）
* **傳遞記錄**： 6個月（建議： 1個月）
* **追蹤記錄**： 6個月（建議： 1個月）
* **事件**：1 個月
* **事件處理的統計資料**： 6個月（建議： 1個月）
* **已封存的事件**：6個月（建議：1個月）
* **臨時實體**：7 天
* **忽略的管線事件**：1 個月
* **傳送警報**：1 個月
* **匯出稽核**： 6個月（建議： 1個月）

## 傳遞的保留期 {#deliveries}

依預設，傳遞的保留期間為無限制。

不過，如果您的執行個體上有大量傳遞，您可以更新&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Application settings]**&#x200B;功能表中的&#x200B;**NmsCleanup_DeliveryPurgeDelay**&#x200B;選項。

每次執行&#x200B;**[!UICONTROL Database cleanup]**&#x200B;工作流程時，符合此選項所設定條件的傳遞都會被刪除。

此動作有助於加快處理速度，例如&#x200B;**[!UICONTROL Copy headers from delivery templates]**&#x200B;工作流程。

>[!NOTE]
>
>在[本節](technical-workflows.md)中進一步瞭解技術工作流程。


**NmsCleanup_DeliveryPurgeDelay**&#x200B;選項的預設值為`-1`。 在此情況下，不會刪除任何傳遞。

例如，如果您將其設為`180`，則在執行&#x200B;**[!UICONTROL Database cleanup]**&#x200B;工作流程時，將會刪除過去180天內未更新的任何非範本傳送。

>[!NOTE]
>
>* 不會刪除行銷或異動傳遞範本。
>
>* 對於循環傳送，不會刪除彙總期間設定為月或年的子傳送。

更新&#x200B;**NmsCleanup_DeliveryPurgeDelay**&#x200B;選項時，建議逐步進行多個反複專案。 例如，您可以先將值設為300天、180天、120天等，確保反複專案之間至少間隔2天。 否則，由於要刪除大量傳遞，**[!UICONTROL Database cleanup]**&#x200B;工作流程可能需要更長的時間。

