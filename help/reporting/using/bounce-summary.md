---
title: 退回摘要
description: 使用彈回摘要現成報告，瞭解您傳送的行銷活動狀態以及他們可能遇到的錯誤。
audience: reporting
content-type: reference
topic-tags: list-of-reports
context-tags: bounceReport,main;campaignCirculationReport,main;programCirculationReport,main
feature: Reporting
role: Leader
level: Intermediate
exl-id: 03ea2f20-959c-497e-bd71-4e77132d712e
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 1%

---

# 退回摘要{#bounce-summary}

此報表詳細說明傳送期間遇到的整體硬式和軟式錯誤，以及自動處理退信(請參閱 [瞭解傳遞失敗](../../sending/using/understanding-delivery-failures.md))。

![](assets/campaign_reports_bounces.png)

每個表格都以摘要數字和圖表表示。 您可以變更詳細資訊在其各自視覺效果設定中的顯示方式。

**失敗5重新分割** 列出隔離數量最多的五個傳送：

此 **退回原因** 表格包含造成每個傳送跳出的錯誤型別的可用資料：

* **[!UICONTROL User unknown]**：傳送至無效電子郵件地址時產生的錯誤型別。
* **[!UICONTROL Invalid domain]**：將傳遞傳送至網域錯誤或不再存在的電子郵件地址時產生的錯誤型別。
* **[!UICONTROL Unreachable]**：訊息傳送字串中遇到的錯誤型別，例如暫時無法存取的網域。
* **[!UICONTROL Account disabled]**：傳送至已不存在的電子郵件地址時產生的錯誤型別。
* **[!UICONTROL Mailbox full]**：收件者的收件匣已滿時產生的錯誤型別。 在產生此錯誤之前，會嘗試傳遞訊息五次。
* **[!UICONTROL Not connected]**：收件者的行動電話關閉或在傳送訊息時未連線至網路時產生的錯誤型別。

   >[!NOTE]
   >
   >這類錯誤只與行動裝置頻道上的傳遞有關。

* **[!UICONTROL Refused]**：網際網路服務提供者(ISP)拒絕位址時產生的錯誤型別。 例如，反垃圾郵件軟體已套用安全性規則時。

此 **網域重新分割** 表格會根據收件者網域顯示傳送期間遇到的整體問題。
