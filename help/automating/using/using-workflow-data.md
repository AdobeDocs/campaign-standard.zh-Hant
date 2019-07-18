---
title: 使用工作流程資料
seo-title: 使用工作流程資料
description: 使用工作流程資料
seo-description: 瞭解使用您匯入或定位之資料的不同可能性。
page-status-flag: 從未啓動
uuid: 3dd66ab-3a26-4214-b6 a0-2-2c2 b7 fbc49
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: reference
topic-tags: 工作流程一般運作
discoiquuid: 90b250f1-f32 d-4256-83ea-4c0627628610
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Using workflow data{#using-workflow-data}

資料經識別並準備後，可用於下列上下文：

* **[!UICONTROL Update data]** 活動可讓您對資料庫中的欄位執行大量更新。
* **[!UICONTROL Save audience]** 此活動可讓您更新現有對象，或從工作流程上游計算的人口族群建立新觀眾。The audiences created or updated from this activity are **List** or **File** audiences. 此活動也可讓您將描述檔匯出為Adobe Experience Cloud觀眾/區段。
* **[!UICONTROL Subscription Services]** 活動可讓您大量擷取個人檔案，並訂閱服務或取消訂閱服務。
* **[!UICONTROL Extract file]** 活動可讓您以外部檔案的形式從Adobe Campaign匯出資料。

定義描述檔目標後，您可以使用數個活動來建立和傳送傳送：

* **[!UICONTROL Email delivery]** 活動可讓您設定工作流程中的電子郵件。This can be a **single send** email and sent just once, or it can be a **recurring** email.
* **[!UICONTROL SMS delivery]** 此活動可讓您設定工作流程中的SMS。This can be a **single send** SMS and sent just once, or it can be a **recurring** SMS.
* **[!UICONTROL Mobile app delivery]** 此活動可讓您設定在工作流程中傳送推播通知。This can be a **single send** notification and sent just once, or it can be a **recurring** notification.

