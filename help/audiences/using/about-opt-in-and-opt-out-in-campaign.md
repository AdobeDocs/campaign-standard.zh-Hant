---
solution: Campaign Standard
product: campaign
title: 關於 Campaign 中的加入和退出
description: 選擇退出會導致描述檔不再受任何傳送或特定渠道的傳送所定位。
audience: audiences
content-type: reference
topic-tags: understanding-opt-in-and-opt-out-processes
feature: 受眾
role: 業務從業人員
level: 初學者
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 9%

---


# 關於 Campaign 中的加入和退出{#about-opt-in-and-opt-out-in-campaign}

選擇退出會導致描述檔不再受任何傳送或特定渠道的傳送所定位。

若要讓描述檔能夠選擇加入或選擇退出，您必須建立專屬的登陸頁面。 如需詳細資訊，請參閱[設定選擇加入和選擇退出登陸頁面](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#setting-up-opt-in-and-opt-out-landing-pages)。

運算子也可以手動選擇加入或退出描述檔。 如需詳細資訊，請參閱[管理描述檔的加入和退出。](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#managing-opt-in-and-opt-out-from-a-profile)

在傳送分析期間會自動排除退出描述檔，以加速傳送（錯誤率對傳送速度有顯著影響）。

>[!NOTE]
>
>選擇退出適用於&#x200B;**Profiles**，而非連結至&#x200B;**電子郵件地址**&#x200B;或&#x200B;**電話號碼**&#x200B;的隔離。 因此，選擇退出配置檔案將排除所有連結到配置檔案的地址的傳送。 如果使用者在資料庫中有兩個描述檔，他仍會被傳送鎖定，因為只有一個描述檔是選擇退出。 為了確保所有地址都被排除，請將其添加到隔離地址。 有關詳細資訊，請參見[此頁面](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses-for-the-entire-platform)。

有關服務訂閱的詳細資訊，請參閱[本頁](../../audiences/using/about-subscriptions.md)。
