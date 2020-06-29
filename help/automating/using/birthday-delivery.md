---
title: 生日寄送
description: 此範例是生日工作流程。 每天都會傳送電子郵件給當天生日的個人檔案。
page-status-flag: never-activated
uuid: 7de53431-84ae-4d21-8361-2775ad314ed2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: channel-activities
discoiquuid: 5f288cf6-f8ff-4ac9-9c1a-8010260554bb
context-tags: delivery,workflow,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7ffa48365875883a98904d6b344ac005afe26e18
workflow-type: tm+mt
source-wordcount: '172'
ht-degree: 0%

---


# 生日寄送 {#birthday-delivery}

![](assets/wkf_delivery_example_1.png)

此範例是生日工作流程。 每天都會傳送電子郵件給當天生日的個人檔案。

若要建立工作流程，請依照下列步驟進行：

* The [Scheduler](../../automating/using/scheduler.md) allows you to start the workflow ady day of 8 am.

   ![](assets/wkf_delivery_example_2.png)

* 「查 [詢](../../automating/using/query.md) 」活動允許您計算每次執行工作流時，提供電子郵件且其生日是當天的配置檔案。 生日計算是使用查詢編輯工具的浮動視窗中可用的預先定義篩選器來執行。

   ![](assets/wkf_delivery_example_3.png)

* 「電 [子郵件](../../automating/using/email-delivery.md) 」傳送是循環傳送。 傳送會依月份匯總。 因此，一個月內傳送的所有電子郵件都會匯總成單一檢視。 因此，在一年內，會執行365個傳送，但會在Adobe Campaign介面中重新分組為12個檢視(也稱 **為循環執行**)。 歷史記錄和報表詳細資訊會每個月顯示一次，而非每次傳送。

   ![](assets/wkf_delivery_example_4.png)
