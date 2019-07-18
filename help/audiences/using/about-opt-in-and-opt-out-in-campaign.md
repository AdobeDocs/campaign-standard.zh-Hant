---
title: 關於促銷活動中選擇加入和退出
seo-title: 關於促銷活動中選擇加入和退出
description: 關於促銷活動中選擇加入和退出
seo-description: 選擇退出(或黑名單)會導致設定檔不再受到任何傳送或特定頻道傳送的內容的鎖定。
page-status-flag: 從未啓動
uuid: 501d9485-976b-4de7-b242-6886f2814 c6 c
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 受眾
content-type: reference
topic-tags: 瞭解選擇退出與選擇退出
discoiquuid: 2f26ec22-0809-4541-b2 a1-e84 ff868 ba6 e
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# About opt-in and opt-out in Campaign{#about-opt-in-and-opt-out-in-campaign}

選擇退出(或黑名單)會導致設定檔不再受到任何傳送或特定頻道傳送的內容的鎖定。

若要讓描述檔能夠選擇加入或選擇退出，您必須建立專屬的登陸頁面。For more on this, refer to [Setting up opt-in and opt-out landing pages](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#setting-up-opt-in-and-opt-out-landing-pages).

描述檔也可以由運算元手動選擇或退出。For more on this, refer to [Managing opt-in and opt-out from a profile](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#managing-opt-in-and-opt-out-from-a-profile).

在傳送分析期間會自動排除退出描述檔，以加速傳送(錯誤率對傳送速度有很大的影響)。

>[!NOTE]
>
>Opt-out applies to **Profiles**, as opposed to quarantine which is linked to an **email address** or **phone number**. 因此，選擇退出描述檔會排除所有連結至其的位址。如果使用者在資料庫中有兩個描述檔，則仍會透過傳送定位他，因為只有其中一個描述檔是退出的。為了確保排除他的所有帳戶，請將其新增至四分位數位址。For more on this, refer to [this page](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses-for-the-entire-platform).

For more on services subscriptions, refer to [this page](../../audiences/using/about-subscriptions.md).
