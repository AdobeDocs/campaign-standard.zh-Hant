---
title: 聯合兩個完善的對象
description: 此使用案例顯示兩個「已讀取」對象活動的結合。
page-status-flag: never-activated
uuid: 58c54e71-f4a7-4ae9-80a3-33c379ab1db9
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 674684e5-8830-4d2f-ba97-59ed4ba7422f
context-tags: readAudience,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 聯合兩個完善的對象 {#example--union-on-two-refined-audiences}

此範例中定義的工作流程會顯示兩個 **[!UICONTROL Read audience]** 活動的聯合。此工作流程的目標是傳送電子郵件給年齡介於 18 至 30 歲之間的金級或銀級會員。系統中已建立特定對象，以追蹤金級和銀級會員。

工作流設計如下：

![](assets/readaudience_activity_example1.png)

* A first [Read audience](../../automating/using/read-audience.md) activity that retrieves the Gold members audience and refines it by selecting only profiles that are between 18 and 30 years old.
* 第二個 **[!UICONTROL Read audience]** 活動，只要選取介於 18 至 30 歲的設定檔，即可擷取和改良銀級會員對象。
* A [Union](../../automating/using/union.md) activity that unites populations from both **[!UICONTROL Read audiences]** activities into one final population.
* An [Email delivery](../../automating/using/email-delivery.md) activity that sends the email to the population coming from the **[!UICONTROL Union]** activity.
