---
solution: Campaign Standard
product: campaign
title: 設定 Campaign-Analytics 整合
description: 瞭解如何設定Adobe Analytics整合，以開始測量電子郵件傳送的成功。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 9%

---


# 設定 Campaign-Analytics 整合{#configure-campaign-analytics-integration}

此整合可讓您直接從Adobe Campaign將關鍵績效指標資料分享至Adobe Analytics Standard或Premium。

若要開始整合Adobe Campaign Standard和Adobe Analytics，您必須先設定連結至Adobe Analytics的外部帳戶。

外部帳戶和技術工作流程只能由平台的功能管理員管理。

1. 從進階功能表，透過Adobe Campaign標誌，選取&#x200B;**[!UICONTROL Administration > Application settings > External accounts]**。
1. 選擇&#x200B;**[!UICONTROL Share KPIs with Adobe Analytics]**&#x200B;外部帳戶。

   ![](assets/analytics_2.png)

1. 在&#x200B;**[!UICONTROL Connection]**&#x200B;欄位中指定&#x200B;**[!UICONTROL Web services user name]**&#x200B;和&#x200B;**[!UICONTROL Web services share secret]**。

   您可在Analytics中選取&#x200B;**[!UICONTROL Admin > Company settings > Web services]**&#x200B;來找到這些參數。

   ![](assets/analytics_1.png)

1. 按一下 **[!UICONTROL Refresh report suites]** 按鈕。
1. 在&#x200B;**[!UICONTROL Analytics default report suite]**&#x200B;下拉式清單中，選取您要使用Adobe Campaign資料豐富的Adobe Analytics報表套裝。

   您的外部帳戶現已準備就緒，並可與Adobe Analytics連結。 您可以隨時勾選&#x200B;**[!UICONTROL Enabled]**&#x200B;方塊以停用它。

   ![](assets/analytics.png)

**[!UICONTROL Share KPIs with Adobe Analytics]**&#x200B;技術工作流程現在會自動啟動，並可從進階功能表選取&#x200B;**[!UICONTROL Administration > Application settings > Workflow]**&#x200B;來檢視。 此技術工作流程將每15分鐘自動執行一次，並在Adobe Analytics中推播最多6個月的舊資料。

![](assets/analytics_3.png)

您的資料現在可在Adobe Analytics中使用。

**相關主題：**

* [外部帳戶](../../administration/using/external-accounts.md)
* [技術工作流程](../../administration/using/technical-workflows.md)
* [共用整合式促銷活動報告視訊的KPI(關](https://helpx.adobe.com/tw/marketing-cloud/how-to/email-marketing.html) 鍵績效指標)

