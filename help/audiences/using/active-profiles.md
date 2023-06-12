---
title: 行銷活動作用中設定檔
description: 瞭解如何存取客戶量度和作用中設定檔
feature: Profiles
role: User
level: Intermediate
exl-id: 22516348-7695-4579-99eb-480e5b723ccc
source-git-commit: 0ae2501b5c3ecf6dc9562bb53b5354c52aff7323
workflow-type: tm+mt
source-wordcount: '266'
ht-degree: 6%

---

# 使用中的設定檔案{#active-profiles}

您可以從以下位置存取作用中設定檔詳細資訊： **[!UICONTROL Customer metrics]** 報告。 此報表僅供Campaign功能管理員使用。 若要存取此報表，請按一下左側的Adobe Campaign圖示， [使用者介面](../../start/using/interface-description.md#advanced-menu)，並瀏覽至 **[!UICONTROL Administration > Customer metrics]**.

![](assets/audience_customer_metrics.png)

此報表每月由產生 **[!UICONTROL Billing]** 技術工作流程與顯示數量 **作用中設定檔**. 進一步瞭解中的技術工作流程 [此頁面](../../administration/using/technical-workflows.md).

「設定檔」是代表最終客戶、潛在客戶或潛在客戶的資訊記錄。 會考量設定檔 **作用中** 過去12個月內，是否曾透過任何管道將Campaign傳遞作為目標。

根據您的合約，您的每個Campaign執行個體都會布建特定數量的作用中設定檔。 如需瞭解已購買的使用中設定檔數目，請參閱您的授權合約。

![](assets/audience_active_profiles_list.png)



* 在傳送準備期間（例如依型別規則或隔離機制）排除的設定檔不會納入考量。

* 交易式訊息收件者會計入作用中設定檔。

* 被多個傳遞項目鎖定的用戶檔案將只計算一次。

* 此報告僅提供資訊，對帳單沒有直接影響。

在頁面底部，會列出目標維度以及每個維度的設定檔數量。 交易式訊息的收件者會與 **匿名** 維度。

>[!NOTE]
>
>身為管理員使用者，您也可以直接從「控制面板」監控執行個體上使用的作用中設定檔數目。 如需詳細資訊，請參閱 [控制面板檔案](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/active-profiles-monitoring.html).
