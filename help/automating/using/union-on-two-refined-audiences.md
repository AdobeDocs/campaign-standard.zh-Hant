---
title: 結合兩個精美受眾
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
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7ffa48365875883a98904d6b344ac005afe26e18
workflow-type: tm+mt
source-wordcount: '150'
ht-degree: 0%

---


# 結合兩個精美受眾 {#example--union-on-two-refined-audiences}

此示例中定義的工作流顯示了兩個活動的 **[!UICONTROL Read audience]** 合併。 此工作流程的目標是傳送電子郵件給年齡在18到30歲之間的金級或銀級會員。 系統中已建立特定對象，以追蹤金級和銀級會員。

工作流設計如下：

![](assets/readaudience_activity_example1.png)

* 第一個 [讀取觀眾](../../automating/using/read-audience.md) ，可擷取金級會員觀眾，並只選取18到30歲的個人檔案來調整觀眾。
* 第二個 **[!UICONTROL Read audience]** 活動會擷取銀色會員觀眾，並只選取18到30歲的設定檔，以調整觀眾。
* 聯合 [國的活動](../../automating/using/union.md) ，將兩個活動中的人口 **[!UICONTROL Read audiences]** 統一為一個最終人口。
* 電子郵件 [傳送活動](../../automating/using/email-delivery.md) ，會將電子郵件傳送至來自活動的 **[!UICONTROL Union]** 人口。
