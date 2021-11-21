---
title: 依網域劃分
description: 透過「依網域劃分」現成可用的報表，了解您所傳送的效能資料（視每個客戶的網域而定）。
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

此報表包含電子郵件傳送對象中所呈現之每個網域的效能資料。 如果是行銷活動或方案報表，則效能資料可供多個對象使用。 此資料可讓您分析每個網域的行為以回應特定事件。 例如連結顯示、封鎖清單上的URL等。

![](assets/delivery_reports_6.png)

表格 **廣播統計** 包含每個網域可能發生錯誤的可用資料，例如：

* **已處理/已傳送**:已傳送的電子郵件數。
* **傳遞**:已傳送的電子郵件數。
* **跳出數+錯誤**:無法傳遞的郵件數。
* **硬跳出**:永久錯誤的總數，例如錯誤的電子郵件地址。
* **軟跳出**:臨時錯誤（如完整收件箱）的總數。

第二張表， **追蹤統計資料**，包含收件者重新活動至傳送的可用資料，例如：

* **傳遞**:已傳送的電子郵件數
* **開啟**:傳遞中開啟訊息的次數。
* **按一下**:傳送中內容的點按次數。
* **已取消訂閱**:訂閱連結的點按次數。
* **鏡像頁**:鏡像頁面連結上的點按次數。
* **封鎖清單上**:宣告電子郵件為垃圾郵件或垃圾郵件的收件人數。 [了解更多](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)
