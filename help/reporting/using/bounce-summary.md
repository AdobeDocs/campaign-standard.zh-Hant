---
title: 退回摘要
description: 使用「退貨」摘要現成報表，瞭解您已發送的市場活動的狀態和可能遇到的錯誤。
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

此報表詳細列出在交貨期間遇到的總體硬錯誤和軟錯誤以及邊界的自動處理(請參閱 [瞭解交付失敗](../../sending/using/understanding-delivery-failures.md))。

![](assets/campaign_reports_bounces.png)

每個表都由摘要數字和圖表表示。 您可以更改詳細資訊在其各自的可視化設定中的顯示方式。

**Flop 5重新分區** 列出了五個檢疫次數最多的交貨：

的 **彈跳原因** 表包含導致每個交貨的退貨的錯誤類型的可用資料：

* **[!UICONTROL User unknown]**:將傳遞發送到無效電子郵件地址時生成的錯誤類型。
* **[!UICONTROL Invalid domain]**:將傳遞發送到其域錯誤或不再存在的電子郵件地址時生成的錯誤類型。
* **[!UICONTROL Unreachable]**:消息傳遞字串中遇到的錯誤類型，例如暫時無法訪問域。
* **[!UICONTROL Account disabled]**:將傳遞發送到不再存在的電子郵件地址時生成的錯誤類型。
* **[!UICONTROL Mailbox full]**:收件者收件箱已滿時生成的錯誤類型。 在生成此錯誤之前，有五次嘗試傳遞消息。
* **[!UICONTROL Not connected]**:當收件人的行動電話關閉或在發送消息時未連接到網路時生成的錯誤類型。

   >[!NOTE]
   >
   >此類錯誤僅涉及移動通道上的交付。

* **[!UICONTROL Refused]**:當Internet服務提供商(ISP)拒絕地址時生成的錯誤類型。 例如，當反垃圾郵件軟體應用了安全規則時。

的 **域重新分區** 表顯示根據收件人域在交付過程中遇到的總體問題。
