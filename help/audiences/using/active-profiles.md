---
solution: Campaign Standard
product: campaign
title: 促銷活動中設定檔
description: 瞭解如何存取客戶指標和作用中的個人檔案
feature: 設定檔
role: Business Practitioner
level: Intermediate
exl-id: 22516348-7695-4579-99eb-480e5b723ccc
source-git-commit: d2fcf2ca22bb5fe3632280f922dfed0972f6eb09
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 5%

---

# 客戶量度{#customer-metrics}

促銷活動功能管理員可從&#x200B;**[!UICONTROL Administration > Customer metrics]**&#x200B;存取&#x200B;**[!UICONTROL Customer metrics]**&#x200B;報表。

![](assets/audience_active_profiles1.png)

此時會顯示報表：

* Experience CloudID
* IMS組織ID
* **活動配置檔案數**
* 例項中可用的定位維度清單

此報告由&#x200B;**[!UICONTROL Billing]**&#x200B;技術工作流程每月產生。

## 使用中的設定檔案{#active-profiles}

根據您的合約，您的每個促銷活動例項都會布建特定數目的作用中描述檔。 請參閱您的授權合約，以取得已購買之有效設定檔數目的參考。

>[!NOTE]
>
>身為管理員使用者，您也可以直接從「控制面板」監視執行個體上使用的作用中描述檔數目。 有關詳細資訊，請參閱[控制面板文檔](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/active-profiles-monitoring.html)。


「個人檔案」是代表最終客戶、潛在客戶或潛在客戶的資訊記錄。 如果描述檔已在過去12個月內透過任何渠道被促銷活動傳送定位，則會將其視為&#x200B;**active**。 交付準備期間排除的配置檔案（例如，通過分類規則或隔離機制）不會被考慮在內。 被多個傳遞項目鎖定的用戶檔案將只計算一次。此報告僅提供資訊，對帳單沒有直接影響。

![](assets/audience_active_profiles2.png)

在報表底部，您會找到每個定位維度的作用中描述檔清單。 它顯示過去12個月滾動期間定位的作用中描述檔數。

* **[!UICONTROL NmsRecipient]**&#x200B;源包含使用其Campaign Standard配置檔案中的資訊聯繫的所有配置檔案。

* 客戶&#x200B;**[!UICONTROL anonymous]**&#x200B;來源僅顯示使用特定資訊（電子郵件地址、電話號碼）進行定位的設定檔數目，與其促銷活動設定檔無關。
