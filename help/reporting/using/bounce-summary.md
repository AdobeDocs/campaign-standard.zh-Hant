---
title: 反彈摘要
seo-title: 反彈摘要
description: 反彈摘要
seo-description: 使用「反彈摘要」立即可用報表，瞭解已傳送促銷活動的狀態和可能發生的錯誤。
page-status-flag: 從未啓動
uuid: 90087311-4236-4df9-ae7 d-4a15 c00 c70 ab
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 報告功能
content-type: reference
topic-tags: 報表清單
discoiquuid: 5ae561b4-03cf-4541-87ff-47f1027d53b
context-tags: BoouncePort，主要；campaignPultiationReport，main；ProgramstationReport，主要
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 77b0933bcd004cedc6a58f80717a4284b284e0cd

---


# Bounce summary{#bounce-summary}

此報告詳細說明傳送期間遇到的整體硬體和柔和錯誤，以及彈回數的自動處理。

![](assets/campaign_reports_bounces.png)

每個表格都以摘要數字和圖表表示。您可以變更詳細資料在其各自視覺化設定中的顯示方式。

**Flop重新分區** 列出五個具有最高四分位數的傳送：

**反彈原因** 表格包含造成每個傳送彈回數之錯誤類型的可用資料：

* **[!UICONTROL User unknown]**：傳送傳送至無效電子郵件地址時產生的錯誤類型。
* **[!UICONTROL Invalid domain]**：傳送傳送至網域故障或不再存在的電子郵件地址時產生的錯誤類型。
* **[!UICONTROL Unreachable]**：訊息傳送字串中遇到的錯誤類型。例如，SMTP繼電器事件、網域暫時無法連線等等。
* **[!UICONTROL Account disabled]**：傳送傳送至不再存在的電子郵件地址時產生的錯誤類型。
* **[!UICONTROL Mailbox full]**：收件者收件匣滿時產生的錯誤類型。有五個嘗試在此錯誤產生之前傳遞訊息。
* **[!UICONTROL Not connected]**：收件者行動電話關閉或在傳送訊息時未連線至網路的錯誤類型。

   >[!NOTE]
   >
   >此類型的錯誤僅關心行動管道上的傳送。

* **[!UICONTROL Refused]**：Internet服務供應商(ISP)拒絕地址時產生的錯誤類型。例如，當安全性規則已由防垃圾郵件軟體套用時。

**網域重新分區** 表格會根據收件者網域顯示傳送期間出現的整體問題。
