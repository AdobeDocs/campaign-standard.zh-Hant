---
title: 依網域劃分
description: 使用依網域劃分的現成可用報表，可依據客戶的每個網域瞭解傳送的效能資料。
audience: reporting
content-type: reference
topic-tags: list-of-reports
context-tags: deliveryDomainBreakdownReport,main;campaignDomainBreakdownReport,main;programDomainBreakdownReport,main
feature: Reporting
role: Leader
level: Intermediate
exl-id: 513d74ae-10c0-4d41-a7d1-8ed655e1a2d1
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 3%

---

# 依網域劃分{#breakdown-by-domains}

此報表包含電子郵件傳遞對象中代表之每個網域的效能資料。 如果是行銷活動或方案報表，則效能資料可供多個對象使用。 此資料可讓您分析每個網域在回應特定事件時的行為。 例如，連結顯示、封鎖清單上的URL等。

![](assets/delivery_reports_6.png)

資料表&#x200B;**廣播統計資料**&#x200B;包含每個網域可能發生的錯誤的可用資料，例如：

* **已處理/傳送**：已傳送的電子郵件數目。
* **已傳遞**：已傳遞的電子郵件數目。
* **退信+錯誤**：無法傳遞的訊息數。
* **硬退信**：永久錯誤的總數，例如錯誤的電子郵件地址。
* **軟退信**：暫時性錯誤的總數，例如完整的收件匣。

第二個資料表&#x200B;**追蹤統計資料**&#x200B;包含可用於傳遞的收件者反應性資料，例如：

* **已傳遞**：已傳遞的電子郵件數目
* **開啟**：傳遞中開啟郵件的次數。
* **點按**：內容在傳遞中被點按的次數。
* **已取消訂閱**：對訂閱連結的點按次數。
* **映象頁面**：映象頁面連結的點按次數。
* **在封鎖清單上**：已將電子郵件宣告為垃圾郵件或垃圾郵件的收件者人數。 [了解更多](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)
