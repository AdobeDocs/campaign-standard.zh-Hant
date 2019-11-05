---
title: 推播通知報告
description: 透過「立即可用的推播通知」報表，瞭解推播通知的成功。
page-status-flag: 從未激活
uuid: 5b121a37-1c09-4749-a409-6989978ddc4c
contentOwner: 紹維亞
products: SG_CAMPAIGN/STANDARD
audience: 報告
content-type: 參考
topic-tags: 清單
discoiquuid: a425cd59-edfd-42c5-a6bd-38773c353ff0
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 推播通知報告{#push-notification-report}

>[!CAUTION]
>
>請注意，您必須將量度拖放至表格 **[!UICONTROL Message type]** ，才能依據傳送類型分割資料，在此例中，推播通知傳送。

「推 **播通知** 」報表提供Adobe Campaign推播通知的行銷績效詳細資訊。 這份現成可用的報表將協助您瞭解使用者如何與推播通知、行動應用程式和傳送互動。

在行動應用程式中需要一些設定才能實作推播追蹤，請參閱 [本頁](https://helpx.adobe.com/campaign/kb/push-tracking.html) ，以取得詳細步驟。

![](assets/dynamic_report_push.png)

每個表都由摘要數字和圖表表示。 您可以變更詳細資訊在其各自視覺化設定中的顯示方式。

第一個表格「推 **播通知參與摘要** 」分為三個類別：依日、依行動應用程式和傳送。 它包含接收者對遞送反應的可用資料：

* **[!UICONTROL Processed/sent]**:傳送的推播通知總數。
* **[!UICONTROL Delivered]**:成功傳送的推播通知數，與傳送的推播通知總數相關。
* **[!UICONTROL Impressions]**:推播通知傳送至裝置且未在通知中心受到影響的次數。 在大多數情況下，印象數目應與傳送的數目類似。 這可確保設備收到消息並將該資訊轉發回伺服器。
* **[!UICONTROL Unique impressions]**:收件者的曝光次數。
* **[!UICONTROL Click through rate]**:與推播通知互動的使用者百分比。
* **[!UICONTROL Open rate]**:已開啟推播通知的百分比。

![](assets/dynamic_report_push_2.png)

第二個表格「推 **播通知點按與開啟** 」分為三個類別：依日、依行動應用程式和傳送。 它包含每個傳送的收件者行為可用資料：

* **[!UICONTROL Impressions]**:收件者可看見的推播通知總數。
* **[!UICONTROL Unique impressions]**:收件者的曝光次數。
* **[!UICONTROL Click]**:推播通知傳送至裝置並被使用者點按的次數。 使用者要麼想要檢視通知，然後將其移至「推播開啟」追蹤，要麼將其關閉。
* **[!UICONTROL Unique clicks]**:獨特使用者與推播通知互動的次數，例如點按通知或按鈕。
* **[!UICONTROL Open]**:傳送至裝置並由使用者點按的推播通知總數，以開啟應用程式。 這類似於推播點按，但是當通知關閉時，不會觸發推播開啟。
* **[!UICONTROL Unique Opens]**:開啟傳送的收件者數。

