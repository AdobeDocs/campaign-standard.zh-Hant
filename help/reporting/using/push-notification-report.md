---
title: 推播通知報告
description: 透過現成可用的推播通知報表，了解推播通知的成功。
audience: reporting
content-type: reference
topic-tags: list-of-reports
feature: Reporting
role: Leader
level: Intermediate
exl-id: acfe0b9c-77a4-46ad-8151-7bf9c21fa4b0
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '383'
ht-degree: 1%

---

# 推播通知報告{#push-notification-report}

>[!CAUTION]
>
>請注意，您必須將&#x200B;**[!UICONTROL Message type]**&#x200B;量度拖放至表格，才能根據您的傳送類型分割資料，在此情況下，是推播通知傳送。

**推播通知**&#x200B;報表提供Adobe Campaign中推播通知的行銷績效詳細資訊。 此現成報表可協助您了解使用者如何與推播通知、行動應用程式和傳遞互動。

行動應用程式中需要一些設定才能實作推播追蹤，如需詳細步驟，請參閱此[page](../../administration/using/push-tracking.md)。

![](assets/dynamic_report_push.png)

每個表由摘要數字和圖表表示。 您可以變更詳細資料在其個別視覺效果設定中的顯示方式。

第一個表格&#x200B;**推播通知參與摘要**&#x200B;分為三個類別：依日、行動應用程式和傳送。 它包含收件者重新活動至傳送的可用資料：

* **[!UICONTROL Processed/sent]**:傳送的推播通知總數。
* **[!UICONTROL Delivered]**:成功傳送的推播通知數，與已傳送的推播通知總數相關。
* **[!UICONTROL Impressions]**:推播通知已傳送至裝置且未在通知中心中動作的次數。在大多數情況下，曝光次數應與傳送的次數類似。 這可確保設備獲取消息並將該資訊轉發回伺服器。
* **[!UICONTROL Unique impressions]**:收件者的曝光次數。
* **[!UICONTROL Click through rate]**:與推播通知互動的使用者百分比。
* **[!UICONTROL Open rate]**:已開啟推播通知的百分比。

![](assets/dynamic_report_push_2.png)

第二個表格&#x200B;**推播通知點按與開啟**&#x200B;分為三個類別：依日、行動應用程式和傳送。 它包含每個傳送的收件者行為可用資料：

* **[!UICONTROL Impressions]**:收件者看到的推播通知總數。
* **[!UICONTROL Unique impressions]**:收件者的曝光次數。
* **[!UICONTROL Click]**:推播通知傳送至裝置並由使用者點按的次數。使用者要麼想要檢視通知，然後將其移至「推播開啟」追蹤，要麼將其關閉。
* **[!UICONTROL Unique clicks]**:不重複使用者與推播通知互動的次數，例如點按通知或按鈕。
* **[!UICONTROL Open]**:傳送至裝置並由使用者點按以開啟應用程式的推播通知總數。這類似於推播點擊，但若關閉通知，則不會觸發推播開啟。
* **[!UICONTROL Unique Opens]**:開啟傳遞的收件者人數。
