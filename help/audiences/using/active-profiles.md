---
title: 促銷活動作用中設定檔
description: 了解如何存取客戶量度和作用中設定檔
feature: Profiles
role: User
level: Intermediate
exl-id: 22516348-7695-4579-99eb-480e5b723ccc
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 7%

---

# 使用中的設定檔案{#active-profiles}

Campaign功能管理員可從&#x200B;**[!UICONTROL Administration > Customer metrics]**&#x200B;存取&#x200B;**[!UICONTROL Customer metrics]**&#x200B;報表。

![](assets/audience_customer_metrics.png)

此報告由&#x200B;**[!UICONTROL Billing]**&#x200B;技術工作流程每月產生，並顯示&#x200B;**作用中設定檔**&#x200B;的數量。

「設定檔」是代表最終客戶、潛在客戶或潛在客戶的資訊記錄。 如果設定檔在過去12個月內透過任何管道被促銷活動傳送鎖定，則會將其視為&#x200B;**active**。

根據您的合約，您的每個Campaign執行個體都布建了特定數量的作用中設定檔。 請參閱您的授權合約，以參考已購買作用中設定檔的數量。

![](assets/audience_active_profiles_list.png)



* 傳送準備期間排除的設定檔（例如，依類型規則或隔離機制）不會納入考量。

* 交易式訊息收件者會計入作用中設定檔。

* 被多個傳遞項目鎖定的用戶檔案將只計算一次。

* 此報表僅提供資訊，對帳單沒有直接影響。

在頁面底部，會列出目標維度及每個維度的設定檔數量。 交易式訊息的收件者會與&#x200B;**Anonymous**&#x200B;維度相關聯。

>[!NOTE]
>
>身為管理員使用者，您也可以直接從「控制面板」監控執行個體上使用的作用中設定檔數目。 有關詳細資訊，請參閱[控制面板檔案](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/active-profiles-monitoring.html)。
