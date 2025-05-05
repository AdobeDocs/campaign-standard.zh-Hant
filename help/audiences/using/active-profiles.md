---
title: 行銷活動作用中設定檔
description: 瞭解如何存取客戶量度和作用中設定檔
feature: Profiles
role: User
level: Intermediate
exl-id: 22516348-7695-4579-99eb-480e5b723ccc
source-git-commit: 0ae2501b5c3ecf6dc9562bb53b5354c52aff7323
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 6%

---

# 使用中的設定檔案{#active-profiles}

您可以從&#x200B;**[!UICONTROL Customer metrics]**&#x200B;報告存取作用中設定檔詳細資料。 此報表僅限Campaign功能管理員使用。 若要存取此報告，請按一下[使用者介面](../../start/using/interface-description.md#advanced-menu)左上角的Adobe Campaign圖示，並瀏覽至&#x200B;**[!UICONTROL Administration > Customer metrics]**。

![](assets/audience_customer_metrics.png)

此報告每月由&#x200B;**[!UICONTROL Billing]**&#x200B;技術工作流程產生，並顯示&#x200B;**作用中設定檔**&#x200B;的數量。 在[此頁面](../../administration/using/technical-workflows.md)中進一步瞭解技術工作流程。

「設定檔」是代表最終客戶、潛在客戶或潛在客戶的資訊記錄。 如果設定檔在過去12個月內透過任何通道被Campaign傳遞設為目標，則會視為&#x200B;**作用中**。

根據您的合約，您的每個Campaign執行個體都已布建特定數量的作用中設定檔。 請參閱您的授權合約，以參考已購買作用中設定檔數目。

![](assets/audience_active_profiles_list.png)



* 在傳送準備期間被排除的設定檔（例如依型別規則或隔離機制）不會納入考量。

* 交易式訊息收件者計入作用中設定檔。

* 被多個傳遞項目鎖定的用戶檔案將只計算一次。

* 此報告僅提供資訊，對帳單沒有直接影響。

在頁面底部，目標維度會與每個維度的設定檔數量一起列出。 交易式訊息的收件者與&#x200B;**匿名**&#x200B;維度相關聯。

>[!NOTE]
>
>身為管理員使用者，您也可以直接從「控制面板」監視執行個體上使用的作用中設定檔數目。 如需詳細資訊，請參閱[控制面板檔案](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/active-profiles-monitoring.html?lang=zh-Hant)。
>
