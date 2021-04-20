---
solution: Campaign Standard
product: campaign
title: 追蹤及監控訊息
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: y
description: 瞭解Adobe Campaign如何讓您追蹤已傳送的訊息，並瞭解收件者對您的傳送有何反應
feature: Deliverability
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '436'
ht-degree: 4%

---


# 追蹤和監視 {#track-and-monitor}

您按了「傳送」按鈕？ 讓我們看看會發生什麼。 傳送後，Adobe Campaign可讓您追蹤傳送的訊息，並瞭解收件者對傳送的反應。 這可協助您改善未來的傳送方式，並最佳化您的下一個促銷活動。

## 監視傳遞{#monitoring-deliveries}

若要控制您的促銷活動，您必須確保訊息確實已傳送給收件者。

**提示**

* 您可以控制傳送記錄檔中訊息的狀態。

* 為了追蹤傳送成功或失敗的情況，Adobe Campaign提供電子郵件警報系統，可傳送通知，告知使用者重要的系統活動。

* 從訊息控制面板，您可以存取此特定訊息的數個報表。

有關詳細資訊，請參閱[監視傳送](../../sending/using/monitoring-a-delivery.md)。

## 追蹤 {#tracking-deliveries}

為了更清楚瞭解目標描述檔的行為，您可以追蹤他們對傳送的反應：接收、開啟、點按連結、取消訂閱等。 請參閱傳送的&#x200B;**追蹤記錄**&#x200B;標籤。

**提示**:預設會啟用訊息追蹤。若要設定URL，請在傳送精靈的下方區段中選取「顯示URL」選項。 對於訊息的每個URL，您可以選擇是否啟用追蹤。

有關詳細資訊，請參閱[跟蹤消息](../../sending/using/tracking-messages.md)部分和[跟蹤指示符](../../reporting/using/tracking-indicators.md)說明。

## 動態報告{#dyn-reports}

動態報表可讓您建立可完全自訂的即時報表，以監控您的促銷活動。 Dimension、量度和視覺化可讓您評估促銷活動對收件者的影響和成功。

**提示** -內建報表可供您監控促銷活動，但您也可以將任何度量或維度拖放至報表，以自訂這些報表。

有關詳細資訊，請參閱[報告指南](../../reporting/using/about-dynamic-reports.md)。

## 熱點點按

「熱點點按」報表會以每個連結的點按百分比呈現訊息內容（HTML和／或文字）。 透過顯示每個動態內容的點按百分比，您可以測量哪些內容最吸引收件者。

有關詳細資訊，請參閱[熱按一下報告](../../reporting/using/hot-clicks.md)。

## 傳送效能提示{#performance-tips}

* 請勿在實例上將交貨保持為失敗狀態，因為這會維護臨時表並影響效能。

* 從資料庫移除不再需要的傳送和非作用中收件者，以維持位址品質。

* 請勿嘗試排程大型傳送。 請注意，在系統上均勻分配負載可能需要5到10分鐘。

**相關主題：**

* [發生故障時收到警報](../../sending/using/receiving-alerts-when-failures-happen.md)
* [報告](../../reporting/using/about-dynamic-reports.md)
