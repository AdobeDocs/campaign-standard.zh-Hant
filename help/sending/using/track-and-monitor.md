---
title: 跟蹤和監視消息
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: y
description: 瞭解Adobe Campaign如何使您能夠跟蹤已發送的郵件並瞭解收件人對您的傳遞有何反應
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

您按一下了「發送」按鈕？ 讓我們看看會發生什麼。 發送後，Adobe Campaign將使您能夠跟蹤已發送的郵件並瞭解收件人對您的發送有何反應。 這有助於您改進未來的發送和優化下一次活動。

## 監視傳遞 {#monitoring-deliveries}

要控制您的市場活動，您必須確保郵件確實已發送給您的收件人。

**提示**

* 您可以控制傳遞日誌中消息的狀態。

* 為了跟蹤交付成功或失敗的情況，Adobe Campaign公司提供了一個電子郵件警報系統，該系統發送通知，以通知用戶重要的系統活動。

* 在消息儀表板中，您可以訪問此特定消息的多個報告。

有關詳細資訊，請參閱 [監控交付](../../sending/using/monitoring-a-delivery.md)。

## 追蹤 {#tracking-deliveries}

為了更好地瞭解目標配置檔案的行為，您可以跟蹤他們對交付的反應：接收、開啟、點擊連結、取消訂閱等。 請參閱 **跟蹤日誌** 的子菜單。

**提示**:預設情況下啟用消息跟蹤。 要配置URL，請在傳遞嚮導的下半部分選擇「顯示URL」選項。 對於消息的每個URL，您可以選擇是否激活跟蹤。

有關詳細資訊，請參閱 [跟蹤消息](../../sending/using/tracking-messages.md) 的 [跟蹤指標](../../reporting/using/tracking-indicators.md) 說明。

## 動態報告 {#dyn-reports}

動態報告允許您建立完全可定製的即時報告來監控您的市場活動。 Dimension、度量和可視化功能使您能夠衡量市場活動對收件人的影響和成功。

**提示**  — 內置報表可用於監視市場活動，但也可以通過將任何指標或維拖放到報表中來自定義這些報表。

有關詳細資訊，請參閱 [報告指南](../../reporting/using/about-dynamic-reports.md)。

## 熱點點擊

「熱點按一下」報告以每個連結上的按一下百分比顯示消息內容(HTML和/或文本)。 通過顯示每個動態內容上的點擊率，您可以衡量哪些內容最吸引收件人。

有關詳細資訊，請參閱 [熱按一下報告](../../reporting/using/hot-clicks.md)。

## 交付效能提示 {#performance-tips}

* 不要在實例上將交貨保持為失敗狀態，因為這會維護臨時表並影響效能。

* 從資料庫中刪除不再需要的遞送和非活動收件人以保持地址質量。

* 不要嘗試將大型交貨安排在一起。 請注意，可能需要5到10分鐘才能將負載均勻地分佈在系統上。

**相關主題：**

* [發生故障時接收警示](../../sending/using/receiving-alerts-when-failures-happen.md)
* [報告](../../reporting/using/about-dynamic-reports.md)
