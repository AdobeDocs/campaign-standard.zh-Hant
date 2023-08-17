---
title: 聯合兩個完善的對象
description: 此使用案例顯示兩個讀取對象活動的聯合。
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: readAudience,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 6261f800-11bd-4b02-a587-49ddb0da240f
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '150'
ht-degree: 58%

---

# 聯合兩個完善的對象 {#example--union-on-two-refined-audiences}

此範例中定義的工作流程會顯示兩個 **[!UICONTROL Read audience]** 活動的聯合。此工作流程的目標是傳送電子郵件給年齡介於 18 至 30 歲之間的金級或銀級會員。系統中已建立特定對象，以追蹤金級和銀級會員。

工作流設計如下：

![](assets/readaudience_activity_example1.png)

* 第一個 [讀取對象](../../automating/using/read-audience.md) 活動，只要選取介於18至30歲的設定檔，即可擷取和改良金級會員對象。
* 第二個 **[!UICONTROL Read audience]** 活動，只要選取介於 18 至 30 歲的設定檔，即可擷取和改良銀級會員對象。
* A [聯集](../../automating/using/union.md) 活動可從兩者聯合母體 **[!UICONTROL Read audiences]** 活動會整合為一個最終母體。
* 一個 [電子郵件傳遞](../../automating/using/email-delivery.md) 活動會將電子郵件傳送至來自的母體 **[!UICONTROL Union]** 活動。
