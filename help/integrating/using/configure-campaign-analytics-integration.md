---
title: 設定 Campaign-Analytics 整合
description: 瞭解如何配置Adobe Analytics整合，以開始衡量您的電子郵件交付成功。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: a6748b4b-36c5-4961-a599-ace73a8504cc
source-git-commit: 26260b9e633d8be1652eeb46c982864a7477da27
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 9%

---

# 設定 Campaign-Analytics 整合{#configure-campaign-analytics-integration}

此整合允許您直接從Adobe Campaign到Adobe Analytics Standard或Premium共用關鍵績效指標資料。

要開始Adobe Campaign Standard和Adobe Analytics之間的整合，您首先需要配置連結到Adobe Analytics的外部帳戶。

外部帳戶和技術工作流只能由平台的功能管理員管理。

1. 從高級菜單中，通過Adobe Campaign徽標選擇 **[!UICONTROL Administration > Application settings > External accounts]**。
1. 選擇 **[!UICONTROL Share KPIs with Adobe Analytics]** 外部帳戶。

   ![](assets/analytics_2.png)

1. 指定 **[!UICONTROL Web services user name]** 和 **[!UICONTROL Web services share secret]** 的 **[!UICONTROL Connection]** 的子菜單。

   通過選擇 **[!UICONTROL Admin > Company settings > Web services]**。

   ![](assets/analytics_1.png)

1. 按一下 **[!UICONTROL Refresh report suites]** 按鈕。
1. 在 **[!UICONTROL Analytics default report suite]** 下拉您想用Adobe Analytics資料豐富的Adobe Campaign報告套件。

   您的外部帳戶已準備好並與Adobe Analytics連結。 您可以通過檢查 **[!UICONTROL Enabled]** 框。

   ![](assets/analytics.png)

的 **[!UICONTROL Share KPIs with Adobe Analytics]** 技術工作流現在將自動啟動，可通過選擇 **[!UICONTROL Administration > Application settings > Workflow]**。 此技術工作流最多可保留6個月的廣播。 請注意，此工作流是增量的，將從前一天推送資料。

![](assets/analytics_3.png)

您的資料現在可在Adobe Analytics獲得。

**相關主題：**

* [外部帳戶](../../administration/using/external-accounts.md)
* [技術工作流程](../../administration/using/technical-workflows.md)
* [共用用於整合市場活動報告的KPI](https://helpx.adobe.com/tw/marketing-cloud/how-to/email-marketing.html) 視頻
