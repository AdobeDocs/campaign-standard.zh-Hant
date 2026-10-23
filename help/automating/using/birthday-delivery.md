---
title: 生日傳遞
description: 此範例是生日工作流程。 每天都會傳送電子郵件給當天生日的設定檔。
audience: automating
content-type: reference
topic-tags: channel-activities
context-tags: delivery,workflow,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 535ddbce-d8ba-4578-9e37-10604291c95d
TQID: 'https://experienceleague.adobe.com/LXiYfz5VXaY7j0pOHWUCGJzp5F4bCsSCmFzEqsQG18E'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 52%
---
# 生日傳遞 {#birthday-delivery}

![](assets/wkf_delivery_example_1.png)

此範例是生日工作流程。 每天都會傳送電子郵件給當天生日的設定檔。

若要建置工作流程，請遵循下列步驟：

* [排程器](../../automating/using/scheduler.md)可讓您每天上午8點啟動工作流程。

  ![](assets/wkf_delivery_example_2.png)

* [查詢](../../automating/using/query.md)活動可讓您計算每次執行工作流程時，提供電子郵件的設定檔及其生日。 生日計算是使用查詢編輯工具浮動視窗中可用的預先定義篩選器來執行。

  ![](assets/wkf_delivery_example_3.png)

* [電子郵件傳遞](../../automating/using/email-delivery.md)是週期性的。 傳送會依月份匯總。 所以，在一個月內傳送的所有電子郵件都會彙總成單一檢視。 因此，在一年內，會執行 365 個傳送，但會在 Adobe Campaign 介面中重新分組為 12 個檢視（也稱為 **recurring executions**)。 歷史記錄和報表詳細資訊會每個月顯示一次，而非每次傳送。

  ![](assets/wkf_delivery_example_4.png)
