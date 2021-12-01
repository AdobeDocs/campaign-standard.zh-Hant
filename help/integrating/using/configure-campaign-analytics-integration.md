---
title: 設定 Campaign-Analytics 整合
description: 了解如何設定Adobe Analytics整合，以開始測量電子郵件傳送的成功程度。
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

此整合可讓您直接從Adobe Campaign與Adobe Analytics Standard或Premium共用關鍵績效指標資料。

若要開始Adobe Campaign Standard與Adobe Analytics之間的整合，您必須先設定連結至Adobe Analytics的外部帳戶。

外部帳戶和技術工作流程只能由平台的功能管理員管理。

1. 從進階功能表，透過Adobe Campaign標誌，選取 **[!UICONTROL Administration > Application settings > External accounts]**.
1. 選取 **[!UICONTROL Share KPIs with Adobe Analytics]** 外部帳戶。

   ![](assets/analytics_2.png)

1. 指定您的 **[!UICONTROL Web services user name]** 和 **[!UICONTROL Web services share secret]** 在 **[!UICONTROL Connection]** 欄位。

   您可以在Analytics中選取 **[!UICONTROL Admin > Company settings > Web services]**.

   ![](assets/analytics_1.png)

1. 按一下 **[!UICONTROL Refresh report suites]** 按鈕。
1. 在 **[!UICONTROL Analytics default report suite]** 下拉式清單中，列出您要以Adobe Analytics資料豐富的Adobe Campaign報表套裝。

   您的外部帳戶現已準備就緒，且已與Adobe Analytics連結。 您可以隨時透過核取 **[!UICONTROL Enabled]** 框。

   ![](assets/analytics.png)

此 **[!UICONTROL Share KPIs with Adobe Analytics]** 技術工作流程現在會自動啟動，並可透過選取 **[!UICONTROL Administration > Application settings > Workflow]**. 此技術工作流程最多可保留6個月的舊broadlog。 請注意，此工作流程是增量式的，且會推送前一天的資料。

![](assets/analytics_3.png)

您的資料現在可在Adobe Analytics中使用。

**相關主題：**

* [外部帳戶](../../administration/using/external-accounts.md)
* [技術工作流程](../../administration/using/technical-workflows.md)
* [共用KPI以進行整合式行銷活動報告](https://helpx.adobe.com/tw/marketing-cloud/how-to/email-marketing.html) 影片
