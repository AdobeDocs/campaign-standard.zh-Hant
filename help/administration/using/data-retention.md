---
title: 資料保留
description: 瞭解標準表格的預設保留值
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 01cfa2a0-4ff5-4520-a515-11676de82528
source-git-commit: bd4b6d0d7d8fae6b14a41dc9001027d8154c9222
workflow-type: tm+mt
source-wordcount: '353'
ht-degree: 5%

---

# 資料保留{#data-retention}

>[!NOTE]
>
>資料報表僅提供過去三年的資料。 如需資料保留期的詳細資訊，請聯絡Adobe顧問或您的技術管理員。

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
* **傳遞**： 2年

## 傳遞的保留期 {#deliveries}

<!-- By default, the retention period for deliveries is unlimited.-->

自2025年6月1日起，系統中將僅保留過去兩年的傳遞。 您會在下方找到更多詳細資料：

* 任何超過兩年的傳遞內容將會永久移除且無法再存取。
* 此清理僅包含已傳送和失敗的傳送；循環傳送、草稿傳送和範本不受影響。
* 移除傳遞後，所有連結的追蹤或傳送資訊也會永久刪除。
* 不會刪除行銷或異動傳遞範本。
* 對於循環傳送，不會刪除彙總期間設定為月或年的子傳送。

如果您希望加快&#x200B;**[!UICONTROL Copy headers from delivery templates]**&#x200B;工作流程之類的程式，則可縮短傳遞保留期。 若要這麼做，請洽詢您的Adobe代表。

<!--

However, if there is a high volume of deliveries on your instance, you can update the **NmsCleanup_DeliveryPurgeDelay** option available from the **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** menu.

Each time the **[!UICONTROL Database cleanup]** workflow is run, the deliveries meeting the conditions set for this option will be deleted.

-->

<!--

When updating the **NmsCleanup_DeliveryPurgeDelay** option, it is recommended to proceed gradually with multiple iterations. For example, you can start by setting the value to 300 days, then 180 days, then 120 days, and so on - making sure iterations are at least 2 days apart. Otherwise, the **[!UICONTROL Database cleanup]** workflow may take much longer because of a large number of deliveries to delete.

This action can help speeding up processes such as the **[!UICONTROL Copy headers from delivery templates]** workflow. Learn more on technical workflows in [this section](technical-workflows.md).

The default value for the **NmsCleanup_DeliveryPurgeDelay** option is `-1`. In this case, no delivery is deleted.

For example, if you set it to `180`, any non-template deliveries that have not been updated in the last 180 days will be deleted when the **[!UICONTROL Database cleanup]** workflow is run.

-->


