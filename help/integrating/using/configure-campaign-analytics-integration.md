---
title: 設定Campaign-Analytics整合
seo-title: 設定Campaign-Analytics整合
description: 設定Campaign-Analytics整合
seo-description: 瞭解如何設定Adobe Analytics整合，以開始評估電子郵件傳送是否成功。
page-status-flag: 從未啓動
uuid: bda00b0-7445-469c-8268-1d06c53ce2b0
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 整合
content-type: reference
topic-tags: 使用促銷活動與分析
discoiquuid: 92b9004c-cba0-41fd-a035-32bee1 d6 a42 c
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 698466596fdacd005dc4d72b8071208c8c39f77d

---


# Configure Campaign-Analytics integration{#configure-campaign-analytics-integration}

此項整合可讓您直接從Adobe Campaign將關鍵績效指標資料分享至Adobe Analytics Standard或Premium。

若要開始Adobe Campaign Standard和Adobe Analytics之間的整合，您必須先設定連結至Adobe Analytics的外部帳戶。

外部帳戶和技術工作流程只能由平台的功能管理員管理。

1. From the advanced menu, via the Adobe Campaign logo, select **[!UICONTROL Administration > Application settings > External accounts]**.
1. Select the **[!UICONTROL Share KPIs with Adobe Analytics]** external account.

   ![](assets/analytics_2.png)

1. Specify your **[!UICONTROL Web services user name]** and **[!UICONTROL Web services share secret]** in the **[!UICONTROL Connection]** field.

   These parameters can be found in Analytics by selecting **[!UICONTROL Admin > Company settings > Web services]**.

   ![](assets/analytics_1.png)

1. Click the **[!UICONTROL Refresh report suites]** button.
1. Select in the **[!UICONTROL Analytics default report suite]** drop-down the Adobe Analytics report suite you want to enrich with Adobe Campaign data.

   您的外部帳戶現已就緒，並已與Adobe Analytics連結。You can disable it at any time by checking the **[!UICONTROL Enabled]** box.

   ![](assets/analytics.png)

**[!UICONTROL Share KPIs with Adobe Analytics]** 技術工作流程現在會自動啓動，並可透過選取 **[!UICONTROL Administration > Application settings > Workflow]**&#x200B;的進階功能表來檢視。此技術工作流程將每15分鐘自動執行一次，最多可在Adobe Analytics中推送個月的資料。

![](assets/analytics_3.png)

您的資料現在可以在Adobe Analytics中使用。

**相關主題：**

* [外部帳戶](../../administration/using/external-accounts.md)
* [技術工作流程](../../administration/using/technical-workflows.md)
* [共用KPI以用於整合的促銷活動報表](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html) 視訊

