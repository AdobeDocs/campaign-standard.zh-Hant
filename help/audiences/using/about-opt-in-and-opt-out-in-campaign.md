---
title: 關於 Campaign 中的加入和退出
description: 選擇退出（或黑名單）會導致描述檔不再受任何傳送或特定渠道的傳送所定位。
page-status-flag: 從未激活
uuid: 501d9485-976b-4de7-b242-6886f2814c6c
contentOwner: 紹維亞
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: 參考
topic-tags: 瞭解——選擇加入——選擇退出流程
discoiquuid: 2f26ec22-0809-4541-b2a1-e84ff868ba6e
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 關於 Campaign 中的加入和退出{#about-opt-in-and-opt-out-in-campaign}

選擇退出（或黑名單）會導致描述檔不再受任何傳送或特定渠道的傳送所定位。

若要讓描述檔能夠選擇加入或選擇退出，您必須建立專屬的登陸頁面。 如需詳細資訊，請參 [閱「設定選擇加入和選擇退出登陸頁面」](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#setting-up-opt-in-and-opt-out-landing-pages)。

運算子也可以手動選擇加入或退出描述檔。 如需詳細資訊，請參 [閱管理描述檔的選擇加入和選擇退出](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#managing-opt-in-and-opt-out-from-a-profile)。

在傳送分析期間會自動排除退出描述檔，以加速傳送（錯誤率對傳送速度有顯著影響）。

>[!NOTE]
>
>選擇退出適用於「 **設定檔**」，而非連結至電子郵件位址或電話 **號碼的隔** 離 ****。 因此，選擇退出配置檔案將排除所有連結到配置檔案的地址的傳送。 如果使用者在資料庫中有兩個描述檔，他仍會被傳送鎖定，因為只有一個描述檔是選擇退出。 為了確保所有地址都被排除，請將其添加到隔離地址。 有關詳細資訊，請參見[此頁面](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses-for-the-entire-platform)。

For more on services subscriptions, refer to [this page](../../audiences/using/about-subscriptions.md).
