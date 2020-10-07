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
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 使用中的設定檔案{#active-profiles}

Adobe Campaign提供顯示作用中描述檔數目的報表。 此報告僅提供資訊，對帳單沒有直接影響。 只有管理員才能存取此報表，位於 **[!UICONTROL Administration > Customer metrics]**&#x200B;下。

![](assets/audience_active_profiles1.png)

>[!NOTE]
>
>如果您是在AWS上代管並使用Campaign Standard建置10368，您也可以直接從控制面板監控實例上使用的活動配置檔案數。 For more on this, refer to the [Control Panel documentation](https://docs.adobe.com/content/help/en/control-panel/using/performance-monitoring/active-profiles-monitoring.html).
>
>請注意，「作用中」描述檔度量僅適用於 **Marketing例項** 。 它不適用於執行實例，即MID（中間採購）和RT（消息中心／即時消息）實例。


交貨準備期間排除的設定檔（類型學規則、隔離、控制群組）不會納入考量。 被多個傳遞項目鎖定的用戶檔案將只計算一次。在報表底部，您會找到每個定位維度的作用中描述檔清單。

此報告由技術工作流程每月 **[!UICONTROL Billing]** 產生。 它包含在最近12個月滾動期間定位的活動配置檔案數。

請注意，在準備交貨期間排除的設定檔（分類規則、隔離）不會納入考量。 此外，已由數個遞送鎖定的描述檔只會計算一次。

![](assets/audience_active_profiles2.png)

在報表底部，您會找到帳單工作流程處理的作用中描述檔清單：

* 來 **[!UICONTROL NmsRecipient]** 源包括使用其Campaign Standard設定檔中的資訊聯絡的所有客戶。

* 另一方面，僅使用特定資訊（電子郵件地址、電話號碼）的目標客戶（與其促銷活動設定檔無關），將歸來源所 **[!UICONTROL anonymous]** 有。
