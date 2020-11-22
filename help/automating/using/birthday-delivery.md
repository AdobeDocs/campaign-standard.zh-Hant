---
solution: Campaign Standard
product: campaign
title: 生日傳遞
description: 此範例是生日工作流程。每天都會傳送電子郵件給當天生日的設定檔。
audience: automating
content-type: reference
topic-tags: channel-activities
context-tags: delivery,workflow,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '172'
ht-degree: 69%

---


# 生日傳遞 {#birthday-delivery}

![](assets/wkf_delivery_example_1.png)

此範例是生日工作流程。每天都會傳送電子郵件給當天生日的設定檔。

若要建立工作流程，請依照下列步驟進行：

* The [Scheduler](../../automating/using/scheduler.md) allows you to start the workflow every day at 8am.

   ![](assets/wkf_delivery_example_2.png)

* The [Query](../../automating/using/query.md) activity allows you to calculate the profiles who have provided an email and whose birthday it is on the current day, every time the workflow is executed. 生日計算是使用查詢編輯工具浮動視窗中可用的預先定義篩選器來執行。

   ![](assets/wkf_delivery_example_3.png)

* 「電 [子郵件](../../automating/using/email-delivery.md) 」傳送會重複。 傳送會依月份匯總。所以，在一個月內傳送的所有電子郵件都會彙總成單一檢視。因此，在一年內，會執行 365 個傳送，但會在 Adobe Campaign 介面中重新分組為 12 個檢視（也稱為 **recurring executions**)。歷史記錄和報表詳細資訊會每個月顯示一次，而非每次傳送。

   ![](assets/wkf_delivery_example_4.png)
