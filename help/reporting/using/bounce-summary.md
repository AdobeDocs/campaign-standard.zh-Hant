---
title: 退回摘要
description: 透過「退回摘要」現成可用的報表，了解已傳送促銷活動的狀態，以及他們可能遇到的錯誤。
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

此報表詳細說明傳送期間遇到的整體硬式和軟式錯誤，以及自動處理退信（請參閱[了解傳送失敗](../../sending/using/understanding-delivery-failures.md)）。

![](assets/campaign_reports_bounces.png)

每個表由摘要數字和圖表表示。 您可以變更詳細資料在其個別視覺效果設定中的顯示方式。

**第5次** 重新分割會列出隔離數量最多的5個傳送：

**退信原因**&#x200B;表格包含導致每次傳送退信的錯誤類型的可用資料：

* **[!UICONTROL User unknown]**:傳送至無效電子郵件地址時產生的錯誤類型。
* **[!UICONTROL Invalid domain]**:將傳送傳送至其網域錯誤或已不存在的電子郵件地址時產生的錯誤類型。
* **[!UICONTROL Unreachable]**:訊息傳送字串中遇到的錯誤類型，例如暫時無法存取網域。
* **[!UICONTROL Account disabled]**:將傳送傳送至已不存在的電子郵件地址時產生的錯誤類型。
* **[!UICONTROL Mailbox full]**:收件者收件匣已滿時產生的錯誤類型。在生成此錯誤之前，有五次嘗試傳送郵件。
* **[!UICONTROL Not connected]**:當收件者的行動電話關閉或在傳送訊息時未連線至網路時產生的錯誤類型。

   >[!NOTE]
   >
   >此類錯誤只與行動通道上的傳送有關。

* **[!UICONTROL Refused]**:當地址被網際網路服務提供商(ISP)拒絕時產生的錯誤類型。例如，當反垃圾郵件軟體應用了安全規則時。

**網域重新分區**&#x200B;表格會根據收件者網域顯示傳送期間遇到的整體問題。
