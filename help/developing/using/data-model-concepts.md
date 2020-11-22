---
solution: Campaign Standard
product: campaign
title: 資料模型概念
description: 瞭解 Adobe Campaign 資料模型以及如何修改它。
audience: developing
content-type: reference
topic-tags: about-custom-resources
context-tags: cusResource,overview;eventCusResource,overview
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 84%

---


# 資料模型概念{#data-model-concepts}

Adobe Campaign 隨附預先定義的資料模型。[管理員](../../administration/using/users-management.md#functional-administrators)可以修改此資料模型，以便將新資源或擴充功能新增至現有資源。

>[!CAUTION]
>
>建立和修改資源是敏感操作，僅由專家使用者執行。

「**[!UICONTROL Administration]** > **[!UICONTROL Development]**」功能表（透過 Adobe Campaign 標誌存取）可讓您管理&#x200B;**自訂資源**、**發佈**，以及&#x200B;**存取診斷工具**。

Adobe Campaign 使用的資料是透過不同的資源來定義。您可以透過建立自訂資源（例如購買或產品表格）來&#x200B;**豐富資料範本**。

無法修改內建資源（例如促銷活動、電子郵件或對象）。不過，自訂資源可以延伸，以新增欄位。

擴充欄位會產生前置詞，以免與內建欄位衝突。

>[!NOTE]
>
>您可以在[此頁](../../developing/using/datamodel-introduction.md)中找到內建資源的資料模型陳述。

您也可以在與所建立資源對應的畫面中[設定導覽](configuring-the-screen-definition.md)。

您可以&#x200B;**匯出和匯入**&#x200B;自訂資源，例如從開發環境匯入生產環境。如需詳細資訊，請參閱此[逐步使用案例](../../automating/using/exporting-importing-custom-resources.md)。

>[!CAUTION]
>
>只有具有角色 [和所有單位](../../administration/using/users-management.md#functional-administrators)存取權的職能管理員 **[!UICONTROL Administration]****** ，才能存取傳送記錄、訊息記錄、追蹤記錄、排除或訂閱記錄。 非管理員使用者可以定位這些記錄檔，但是從連結的表格（描述檔、傳送）開始。
