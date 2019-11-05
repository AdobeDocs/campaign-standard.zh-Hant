---
title: 工作流程作業原則
description: 瞭解工作流程的主要方面。
page-status-flag: 從未激活
uuid: 85755e85-617b-4a9b-bb30-96ba833f4f0
contentOwner: 紹維亞
products: SG_CAMPAIGN/STANDARD
audience: 自動化
content-type: 參考
topic-tags: about-workflows-and-data-management
discoiquuid: 3a13785d-1ef7-4043-9927-2d495b83709f
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 工作流程作業原則{#workflow-operating-principles}

工作流是可配 **置活動的序列**。 每個活動在進程中都具有特定角色。 每個活動的結果通過一個轉換（用箭頭表示） **轉發**&#x200B;到以下活動。

在一個活動和另一個活動之間交換的資料類型可能會影響以下活動的配置方式。 例如，如果在電子郵件傳送活動之前建立了人口族群，則可當成相關電子郵件的目標。

您可以在執行工作流之前或之後開啟活動以檢查或編輯參數。

您可以開啟轉場來檢查在執行工作流程期間或之後傳送的資料是否正確。 若要存取轉場的詳細檢視，您必須勾選工作 **[!UICONTROL Keep interim results]** 流程屬性 **[!UICONTROL Execution]** 區段中的選項。

![](assets/workflow_overview.png)

