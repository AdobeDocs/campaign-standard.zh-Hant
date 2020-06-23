---
title: 使用中的設定檔案
description: 您可以存取客戶量度的專屬報表，並在促銷活動資料庫中視覺化作用中的個人檔案。
page-status-flag: never-activated
uuid: ee8ac493-c297-49ca-aed4-3976d8a685a4
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-profiles
discoiquuid: e029213f-0b65-41b1-8adf-34fa813b0c70
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 4575c1152f1a33ff18b2200151346cc6e56b45fa
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 19%

---


# 使用中的設定檔案{#active-profiles}

Adobe Campaign提供顯示作用中描述檔數目的報表。 此報告僅提供資訊，對帳單沒有直接影響。 只有管理員才能存取此報表，位於 **[!UICONTROL Administration > Customer metrics]**&#x200B;下。

![](assets/audience_active_profiles1.png)

技 **[!UICONTROL Billing]** 術工作流程每月產生一份報告，其中包含過去12個月滾動期間鎖定的作用中描述檔數目。

在傳遞準備期間 (類型規則，隔離) 被排除的用戶檔案不包含在內。被多個傳遞項目鎖定的用戶檔案將只計算一次。在報表底部，您會找到每個定位維度的作用中描述檔清單。

![](assets/audience_active_profiles2.png)

如果您是在AWS上代管並使用Campaign Standard建置10368，您也可以直接從控制面板監控實例上使用的活動配置檔案數。 有關詳細資訊，請參閱「控 [制面板」文檔](https://docs.adobe.com/content/help/en/control-panel/using/performance-monitoring/active-profiles-monitoring.html)。
