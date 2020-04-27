---
title: 資料模型概念
description: 瞭解Adobe Campaign資料模型以及如何修改它。
page-status-flag: never-activated
uuid: cacd563f-6936-4b3e-83e3-5d4ae31d44e8
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: about-custom-resources
discoiquuid: 4e0468da-3052-4ce5-8174-45aba1f5c4ed
context-tags: cusResource,overview;eventCusResource,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 8852adb5edeb42eba1acf2911c988071104f1401

---


# 資料模型概念{#data-model-concepts}

Adobe Campaign隨附預先定義的資料模型。 管理員可以修改此資 [料模型](../../administration/using/users-management.md#functional-administrators) ，以便將新資源或擴充功能新增至現有資源。

>[!CAUTION]
>
>建立和修改資源是敏感操作，僅由專家用戶執行。

>功 **[!UICONTROL Administration]** 能表 **[!UICONTROL Development]** （透過Adobe Campaign標誌存取）可讓您管理自訂資 **源**、 **發佈** ，以及 ****&#x200B;存取診斷工具。

Adobe Campaign使用的資料是透過不同的資源來定義。 您可以 **透過建立自訂資源** （例如購買或產品表格）來豐富資料範本。

無法修改內建資源（例如促銷活動、電子郵件或對象）。 不過，自訂資源可以延伸，以新增欄位。

副檔名欄位會產生前置詞，以免與內建欄位衝突。

>[!NOTE]
>
>您可以在此頁中找到建置資源的資料模 [型表示](../../developing/using/datamodel-introduction.md)。

您也可以 [在與所建立資源對應的畫面中](configuring-the-screen-definition.md) ，設定導覽。

您可以匯出 **和匯入自訂資源** ，例如從開發環境匯入生產環境。 如需詳細資訊，請參閱 [此逐步使用案例](../../automating/using/exporting-importing-custom-resources.md)。
