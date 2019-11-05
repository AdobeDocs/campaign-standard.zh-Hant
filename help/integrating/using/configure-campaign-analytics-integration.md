---
title: 設定 Campaign-Analytics 整合
description: 瞭解如何設定Adobe Analytics整合，以開始測量電子郵件傳送的成功。
page-status-flag: 從未激活
uuid: bdaa00b0-7445-469c-8268-9d06c53ce2b0
contentOwner: 紹維亞
products: SG_CAMPAIGN/STANDARD
audience: 整合
content-type: 參考
topic-tags: 搭配促銷活動與分析
discoiquuid: 92b9004c-cba0-41fd-a035-32bee1d6a42c
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 設定 Campaign-Analytics 整合{#configure-campaign-analytics-integration}

此整合可讓您直接從Adobe Campaign將關鍵績效指標資料分享至Adobe Analytics Standard或Premium。

若要開始整合Adobe Campaign Standard和Adobe Analytics，您必須先設定連結至Adobe Analytics的外部帳戶。

外部帳戶和技術工作流程只能由平台的功能管理員管理。

1. 從進階功能表，透過Adobe Campaign標誌，選取 **[!UICONTROL Administration > Application settings > External accounts]**。
1. 選擇外 **[!UICONTROL Share KPIs with Adobe Analytics]** 部帳戶。

   ![](assets/analytics_2.png)

1. 在欄位 **[!UICONTROL Web services user name]** 中指 **[!UICONTROL Web services share secret]** 定您的 **[!UICONTROL Connection]** 和。

   您可在Analytics中選取這些參數 **[!UICONTROL Admin > Company settings > Web services]**。

   ![](assets/analytics_1.png)

1. Click the **[!UICONTROL Refresh report suites]** button.
1. 從下拉式 **[!UICONTROL Analytics default report suite]** 清單中選取您要使用Adobe Campaign資料豐富的Adobe Analytics報表套裝。

   您的外部帳戶現已準備就緒，並可與Adobe Analytics連結。 您可以隨時勾選方塊來停用 **[!UICONTROL Enabled]** 它。

   ![](assets/analytics.png)

技術 **[!UICONTROL Share KPIs with Adobe Analytics]** 工作流程現在會自動啟動，並可從進階選單中選取以檢視 **[!UICONTROL Administration > Application settings > Workflow]**。 此技術工作流程將每15分鐘自動執行一次，並在Adobe Analytics中推播最多6個月的舊資料。

![](assets/analytics_3.png)

您的資料現在可在Adobe Analytics中使用。

**相關主題：**

* [外部帳戶](../../administration/using/external-accounts.md)
* [技術工作流程](../../administration/using/technical-workflows.md)
* [共用整合式促銷活動報告視訊的KPI](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html)

