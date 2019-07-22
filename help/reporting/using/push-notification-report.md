---
title: 推播通知報表
seo-title: 推播通知報表
description: 推播通知報表
seo-description: 透過「推播通知」立即可用的報告，瞭解推播通知是否成功。
page-status-flag: 從未啓動
uuid: 5b121a37-1c09-4749-a409-6989978ddc4 c
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 報告功能
content-type: reference
topic-tags: 報表清單
discoiquuid: a425cd59-eddd-42c5-a6 bd-38773c353 ff0
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7102ed308f94985f8924a13aab2583e50b6c68e4

---


# Push notification report{#push-notification-report}

>[!CAUTION]
>
>Please note that you have to drag and drop the **[!UICONTROL Message type]** metrics to your tables to split your data depending on your delivery types, in this case push notification deliveries.

**推播通知** 報表提供Adobe Campaign推播通知行銷效能的詳細資訊。此立即可用的報告將協助您瞭解使用者如何與推播通知、行動應用程式和傳送互動。

Some configuration is required in the mobile application to implement push tracking, refer to this [page](https://helpx.adobe.com/campaign/kb/push-tracking.html) for the detailed steps.

![](assets/dynamic_report_push.png)

每個表格都以摘要數字和圖表表示。您可以變更詳細資料在其各自視覺化設定中的顯示方式。

The first table **Push notification Engagement Summary** is split into three categories: by day, by mobile app and by delivery. 它包含可供收件者重新活動的可用資料：

* **[!UICONTROL Processed/sent]**：傳送的推播通知總數。
* **[!UICONTROL Delivered]**：與傳送的推播通知總數相關的推播通知數目成功。
* **[!UICONTROL Impressions]**：推播通知傳送至裝置並在通知中心未受干擾的次數。在大多數情況下，曝光次數應類似於傳送的數字。如此可確保裝置取得訊息，並將該資訊傳回伺服器。
* **[!UICONTROL Unique impressions]**：收件者的印象數。
* **[!UICONTROL Click through rate]**：與推播通知互動的使用者百分比。
* **[!UICONTROL Open rate]**：開啓推播通知的百分比。

![](assets/dynamic_report_push_2.png)

The second table **Push notification Clicks &amp; opens** is split into three categories: by day, by mobile app and by delivery. 它包含每個傳送之收件者行為的可用資料：

* **[!UICONTROL Impressions]**：收件者看到的推播通知總數。
* **[!UICONTROL Unique impressions]**：收件者的印象數。
* **[!UICONTROL Click]**：推播通知傳送至裝置並由使用者點按的次數。使用者會想要檢視通知，然後將通知移至推送開啓追蹤或關閉。
* **[!UICONTROL Unique clicks]**：獨特使用者與推播通知互動的次數，例如按一下通知或按鈕的次數。
* **[!UICONTROL Open]**：傳送至裝置的推播通知總數，並由使用者按一下開啓應用程式。這類似於推送點按除外，除非通知已關閉，否則無法觸發推送開啓。
* **[!UICONTROL Unique Opens]**：開啓此傳送的收件者人數。

