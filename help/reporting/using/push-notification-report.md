---
solution: Campaign Standard
product: campaign
title: 推播通知報告
description: 透過「立即可用的推播通知」報表，瞭解推播通知的成功。
audience: reporting
content-type: reference
topic-tags: list-of-reports
feature: 報告
role: 領導者
level: 中級
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 1%

---


# 推播通知報告{#push-notification-report}

>[!CAUTION]
>
>請注意，您必須將&#x200B;**[!UICONTROL Message type]**&#x200B;量度拖放至表格，才能依您的傳送類型分割資料，在此情況下，推送通知傳送。

**推播通知**&#x200B;報表提供Adobe Campaign推播通知的行銷績效詳細資訊。 這份現成可用的報表將協助您瞭解使用者如何與推播通知、行動應用程式和傳送互動。

行動應用程式中需要一些設定才能實施推播追蹤，請參閱此[page](../../administration/using/push-tracking.md)以取得詳細步驟。

![](assets/dynamic_report_push.png)

每個表都由摘要數字和圖表表示。 您可以變更詳細資訊在其各自視覺化設定中的顯示方式。

第一個表&#x200B;**推播通知參與摘要**&#x200B;分為三類：依日、依行動應用程式和傳送。 它包含接收者對遞送反應的可用資料：

* **[!UICONTROL Processed/sent]**:傳送的推播通知總數。
* **[!UICONTROL Delivered]**:成功傳送的推播通知數，與傳送的推播通知總數相關。
* **[!UICONTROL Impressions]**:推播通知傳送至裝置且未在通知中心受到影響的次數。在大多數情況下，印象數目應與傳送的數目類似。 這可確保設備收到消息並將該資訊轉發回伺服器。
* **[!UICONTROL Unique impressions]**:收件者的曝光次數。
* **[!UICONTROL Click through rate]**:與推播通知互動的使用者百分比。
* **[!UICONTROL Open rate]**:已開啟推播通知的百分比。

![](assets/dynamic_report_push_2.png)

第二個表格&#x200B;**推播通知點按與開啟**&#x200B;分為三個類別：依日、依行動應用程式和傳送。 它包含每個傳送的收件者行為可用資料：

* **[!UICONTROL Impressions]**:收件者可看見的推播通知總數。
* **[!UICONTROL Unique impressions]**:收件者的曝光次數。
* **[!UICONTROL Click]**:推播通知傳送至裝置並被使用者點按的次數。使用者要麼想要檢視通知，然後將其移至「推播開啟」追蹤，要麼將其關閉。
* **[!UICONTROL Unique clicks]**:獨特使用者與推播通知互動的次數，例如點按通知或按鈕。
* **[!UICONTROL Open]**:傳送至裝置並由使用者點按的推播通知總數，以開啟應用程式。這類似於推播點按，但是當通知關閉時，不會觸發推播開啟。
* **[!UICONTROL Unique Opens]**:開啟傳送的收件者數。

