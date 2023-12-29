---
title: 追蹤和監視訊息
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: y
description: 瞭解Adobe Campaign如何讓您追蹤已傳送的訊息，並探索收件者對您的傳送有何反應
feature: Deliverability
role: User
level: Intermediate
exl-id: dd3bd672-fb9d-4e82-bdf3-d319f372baaa
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '433'
ht-degree: 3%

---

# 追蹤和監視 {#track-and-monitor}

您按下「傳送」按鈕了嗎？ 讓我們看看會發生什麼事。 傳送後，Adobe Campaign可讓您追蹤已傳送的訊息，並探索收件者對傳送的反應。 這有助於您改善未來的傳送，並最佳化您的後續行銷活動。

## 監視傳遞 {#monitoring-deliveries}

若要控制您的行銷活動，您必須確保訊息確實已傳送給收件者。

**提示**

* 您可以在傳送記錄檔中控制訊息的狀態。

* 為了追蹤傳送成功或失敗，Adobe Campaign提供電子郵件警報系統，如此可傳送通知，以通知使用者發生重要的系統活動。

* 從訊息控制面板，您可以存取此特定訊息的數個報表。

如需詳細資訊，請參閱 [監視傳遞](../../sending/using/monitoring-a-delivery.md).

## 追蹤 {#tracking-deliveries}

若要更清楚瞭解目標設定檔的行為，您可以追蹤其對傳送的反應：接收、開啟、點選連結、取消訂閱等。 請參閱 **追蹤記錄** 傳遞的索引標籤。

**秘訣**：訊息追蹤預設為啟用。 若要設定URL，請選取傳送精靈下方的顯示URL選項。 對於訊息的每個URL，您可以選擇是否啟動追蹤。

有關詳細資訊，請參閱 [追蹤訊息](../../sending/using/tracking-messages.md) 區段和 [追蹤指標](../../reporting/using/tracking-indicators.md) 說明。

## 動態報告 {#dyn-reports}

動態報告可讓您建立完全可自訂的即時報告，以監控您的行銷活動。 Dimension、量度和視覺效果可讓您評估行銷活動對收件者的影響和成功。

**秘訣**  — 您可使用內建報表來監視行銷活動，但也可以將任何量度或維度拖放至報表中來自訂這些報表。

有關詳細資訊，請參閱 [報告指南](../../reporting/using/about-dynamic-reports.md).

## 熱點點擊

「熱點點按」報表會顯示訊息內容(HTML和/或文字)以及每個連結的點按百分比。 藉由顯示每個動態內容的點按百分比，您可以測量哪些內容最能吸引收件者。

有關詳細資訊，請參閱 [熱門點選報告](../../reporting/using/hot-clicks.md).

## 傳遞效能提示 {#performance-tips}

* 請勿將傳遞在執行個體上維持在失敗狀態，因為這會維護臨時表格並影響效能。

* 從資料庫移除不再需要的傳遞及非作用中的收件者，以維持地址品質。

* 請勿嘗試一起排程大型傳遞。 請注意，可能需要5到10分鐘的時間才能將負載均勻分散到系統上。

**相關主題：**

* [發生故障時接收警示](../../sending/using/receiving-alerts-when-failures-happen.md)
* [報告](../../reporting/using/about-dynamic-reports.md)
