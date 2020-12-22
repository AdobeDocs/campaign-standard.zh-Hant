---
solution: Campaign Standard
product: campaign
title: 退回摘要
description: 透過「彈回數摘要現成可用」報表，瞭解您所傳送之促銷活動的狀態，以及他們可能遇到的錯誤。
audience: reporting
content-type: reference
topic-tags: list-of-reports
context-tags: bounceReport,main;campaignCirculationReport,main;programCirculationReport,main
translation-type: tm+mt
source-git-commit: 2bc5eae996dfa3ecdde3540f3a4f759c668e93ec
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 1%

---


# 退回摘要{#bounce-summary}

此報表詳細說明在傳送期間遇到的整體硬錯誤和軟錯誤，以及自動處理彈回數（請參閱[瞭解傳送失敗](../../sending/using/understanding-delivery-failures.md)）。

![](assets/campaign_reports_bounces.png)

每個表都由摘要數字和圖表表示。 您可以變更詳細資訊在其各自視覺化設定中的顯示方式。

**第5次** 重新分離會議列出了5次隔離率最高的遞送：

**彈回數原因**&#x200B;表格包含導致每次傳送彈回的錯誤類型的可用資料：

* **[!UICONTROL User unknown]**:傳送內容傳送至無效電子郵件地址時產生的錯誤類型。
* **[!UICONTROL Invalid domain]**:傳送內容傳送至網域錯誤或不再存在之電子郵件地址時產生的錯誤類型。
* **[!UICONTROL Unreachable]**:訊息傳送字串中遇到的錯誤類型，例如暫時無法存取網域。
* **[!UICONTROL Account disabled]**:傳送內容傳送至已不存在的電子郵件地址時產生的錯誤類型。
* **[!UICONTROL Mailbox full]**:收件者收件匣已滿時產生的錯誤類型。在產生此錯誤之前，有5次嘗試傳送訊息。
* **[!UICONTROL Not connected]**:當收件者的行動電話關閉或訊息傳送時未連線至網路時，產生的錯誤類型。

   >[!NOTE]
   >
   >此類錯誤只涉及行動頻道的傳送。

* **[!UICONTROL Refused]**:當Internet服務提供商(ISP)拒絕地址時生成的錯誤類型。例如，當防垃圾郵件軟體應用了安全規則時。

**Domain repartition**&#x200B;表格會根據收件者網域顯示傳送期間所遇到的整體問題。
