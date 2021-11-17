---
title: 關於 Campaign 中的選擇加入和選擇退出
description: 選擇退出會導致設定檔不再被任何傳送或特定通道的傳送鎖定。
audience: audiences
content-type: reference
topic-tags: understanding-opt-in-and-opt-out-processes
feature: Audiences
role: User
level: Beginner
exl-id: ccb35aeb-2b32-4444-969b-50021111a0d6
source-git-commit: 8be43668d1a4610c3388ad27e493a689925dc88c
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 8%

---

# 關於 Campaign 中的選擇加入和選擇退出{#about-opt-in-and-opt-out-in-campaign}

選擇退出會導致設定檔不再被任何傳送或特定通道的傳送鎖定。

若要讓設定檔能夠選擇加入或選擇退出，您必須建立專用的登錄頁面。 有關詳細資訊，請參閱 [設定選擇加入和選擇退出登錄頁面](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#setting-up-opt-in-and-opt-out-landing-pages).

運算子也可以手動選擇加入或退出設定檔。 有關詳細資訊，請參閱 [管理設定檔的加入和退出](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#managing-opt-in-and-opt-out-from-a-profile).

在傳送分析期間會自動排除退出設定檔，以加快傳送（錯誤率對傳送速度有顯著影響）。

>[!NOTE]
>
>退出套用至 **設定檔**，而非連結至 **電子郵件地址** 或 **電話號碼**. 因此，選擇退出設定檔會排除所有連結至該設定檔的位址。 不過，如果使用者在資料庫中有兩個設定檔，則傳送仍會鎖定此使用者，因為只有其中一個設定檔會退出。 若要確認已排除其所有位址，請將其新增至隔離的位址。 如需詳細資訊，請參閱[此頁面](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses-for-the-entire-platform)。

有關服務訂閱的詳細資訊，請參閱 [本頁](../../audiences/using/about-subscriptions.md).
