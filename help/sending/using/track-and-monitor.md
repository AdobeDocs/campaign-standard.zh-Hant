---
title: 追蹤及監視訊息
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: y
description: 了解Adobe Campaign如何讓您持續追蹤已傳送的訊息，並了解收件者對您傳送內容的反應
feature: Deliverability
role: User
level: Intermediate
exl-id: dd3bd672-fb9d-4e82-bdf3-d319f372baaa
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 4%

---

# 追蹤和監視 {#track-and-monitor}

您按一下「傳送」按鈕？ 讓我們看看會發生什麼。 傳送後，Adobe Campaign可讓您追蹤已傳送的訊息，並探索收件者對您傳送的反應。 這可協助您改善未來的傳送，並最佳化您的下一個行銷活動。

## 監視傳遞 {#monitoring-deliveries}

若要控制您的行銷活動，您必須確保訊息確實已傳送給收件者。

**提示**

* 您可以控制傳送記錄檔中訊息的狀態。

* 為了追蹤傳送成功或失敗，Adobe Campaign提供電子郵件警報系統，可傳送通知，以通知使用者發生重要的系統活動。

* 從訊息控制面板，您可以存取此特定訊息的數個報表。

如需詳細資訊，請參閱 [監控傳送](../../sending/using/monitoring-a-delivery.md).

## 追蹤 {#tracking-deliveries}

為了更清楚了解目標設定檔的行為，您可以追蹤其對傳送的反應：接收、開啟、點按連結、取消訂閱等。 請參閱 **追蹤記錄** 標籤。

**筆尖**:訊息追蹤預設為啟用。 若要設定URL，請在傳送精靈的下半部選取「顯示URL」選項。 對於訊息的每個URL，您可以選擇是否啟用追蹤。

有關詳細資訊，請參閱 [追蹤訊息](../../sending/using/tracking-messages.md) 區段和 [追蹤指標](../../reporting/using/tracking-indicators.md) 說明。

## 動態報告 {#dyn-reports}

動態報表可讓您建立完全可自訂的即時報表，以監控您的促銷活動。 Dimension、量度和視覺效果可讓您測量行銷活動對收件者的影響和成功。

**筆尖**  — 內建報表可供您監控促銷活動，但您也可以拖放任何量度或維度至報表，以自訂這些報表。

有關詳細資訊，請參閱 [報表指南](../../reporting/using/about-dynamic-reports.md).

## 熱點點擊

「熱點點按」報表會以每個連結的點按百分比呈現訊息內容(HTML和/或文字)。 透過顯示每個動態內容的點按百分比，您可以測量哪些內容最能吸引收件者。

有關詳細資訊，請參閱 [熱點按報表](../../reporting/using/hot-clicks.md).

## 傳遞效能提示 {#performance-tips}

* 請勿在執行個體上將傳送保持為失敗狀態，因為這會維護臨時表格並影響效能。

* 從資料庫中移除不再需要的傳送和非作用中的收件者，以維持位址品質。

* 請勿嘗試將大型傳送排程在一起。 請注意，可能需要5到10分鐘才能將負載均勻地分散到系統上。

**相關主題：**

* [發生故障時接收警示](../../sending/using/receiving-alerts-when-failures-happen.md)
* [報告](../../reporting/using/about-dynamic-reports.md)
