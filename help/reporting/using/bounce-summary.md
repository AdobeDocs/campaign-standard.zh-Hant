---
title: 退回摘要
description: 使用彈回摘要現成可用報告，瞭解您傳送的行銷活動狀態及其可能遇到的錯誤。
audience: reporting
content-type: reference
topic-tags: list-of-reports
context-tags: bounceReport,main;campaignCirculationReport,main;programCirculationReport,main
feature: Reporting
role: Leader
level: Intermediate
exl-id: 03ea2f20-959c-497e-bd71-4e77132d712e
TQID: https://experienceleague.adobe.com/ggB-q-6kJyPF4GgJJzJGtsOqg6-7MeBhEfiGVY0M7sQ
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: a075b2c1-7748-4328-b7f6-343aa314616a
role_v2: id: f8a45b24-4be7-4f1b-909b-60d06b483a20
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 282
ht-degree: 1%

---

# 退回摘要{#bounce-summary}

此報表詳細說明傳送期間遇到的整體硬式和軟式錯誤，以及自動處理退信（請參閱[瞭解傳送失敗](../../sending/using/understanding-delivery-failures.md)）。

![](assets/campaign_reports_bounces.png)

每個表格都由摘要數字和圖表表示。 您可以變更詳細資訊在其各自視覺效果設定中的顯示方式。

**失敗5重新分割**&#x200B;列出隔離數量最多的五個傳遞：

**退回原因**&#x200B;表格包含造成每個傳遞退回的錯誤型別的可用資料：

* **[!UICONTROL User unknown]**：傳送至無效電子郵件地址時產生的錯誤型別。
* **[!UICONTROL Invalid domain]**：當傳送至網域錯誤或不再存在的電子郵件地址時，產生的錯誤型別。
* **[!UICONTROL Unreachable]**：在訊息傳遞字串中遇到的錯誤型別，例如暫時無法存取網域。
* **[!UICONTROL Account disabled]**：傳送至已不存在的電子郵件地址時產生的錯誤型別。
* **[!UICONTROL Mailbox full]**：收件者的收件匣已滿時產生的錯誤型別。 在產生此錯誤之前，會嘗試五次傳遞訊息。
* **[!UICONTROL Not connected]**：收件者的行動電話已關機或傳送訊息時未連線至網路時產生的錯誤型別。

  >[!NOTE]
  >
  >這類錯誤只與行動裝置頻道上的傳遞有關。

* **[!UICONTROL Refused]**：當網際網路服務提供者(ISP)拒絕位址時產生的錯誤型別。 例如，反垃圾郵件軟體已套用安全性規則時。

**網域重新分割**&#x200B;表格會顯示根據收件者網域進行傳遞時遇到的整體問題。
