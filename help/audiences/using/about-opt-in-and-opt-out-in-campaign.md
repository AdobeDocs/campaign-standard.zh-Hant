---
title: 關於 Campaign 中的選擇加入和選擇退出
description: 選擇退出會導致設定檔不再被任何傳送或特定頻道的傳送設為目標。
audience: audiences
content-type: reference
topic-tags: understanding-opt-in-and-opt-out-processes
feature: Audiences
role: User
level: Beginner
exl-id: ccb35aeb-2b32-4444-969b-50021111a0d6
TQID: 'https://experienceleague.adobe.com/9fzQiPrBRAFlTxX5EKo-Qvph3nYZYoA29kMrm6cXVLs'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: afa4204e-6d08-4e29-bc35-26aafb656d48
    internal-label: Profiles and audiences
subfeature_v2:
  - id: d6330382-c886-4f7a-a4f7-74e3f36c0d9c
    internal-label: Audiences
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 10%
---
# 關於 Campaign 中的選擇加入和選擇退出{#about-opt-in-and-opt-out-in-campaign}

選擇退出會導致設定檔不再被任何傳送或特定頻道的傳送設為目標。

若要讓設定檔能夠選擇加入或選擇退出，您必須建立專用的登陸頁面。 如需詳細資訊，請參閱[設定選擇加入和選擇退出登入頁面](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#setting-up-opt-in-and-opt-out-landing-pages)。

操作員也可以手動選擇加入或退出設定檔。 如需詳細資訊，請參閱[管理設定檔的選擇加入和選擇退出](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#managing-opt-in-and-opt-out-from-a-profile)。

在傳送分析期間會自動排除選擇退出設定檔，以加快傳送速度（錯誤率對傳送速度有顯著影響）。

>[!NOTE]
>
>選擇退出適用於&#x200B;**設定檔**，而非連結至&#x200B;**電子郵件地址**&#x200B;或&#x200B;**電話號碼**&#x200B;的隔離區。 因此，選擇退出設定檔將會從傳遞中排除連結至設定檔的所有地址。 但是，如果使用者在資料庫中有兩個設定檔，由於僅會選擇退出其中一個設定檔，因此傳遞仍會鎖定此使用者。 為確保將其所有地址排除，請將其新增至隔離地址。 如需詳細資訊，請參閱[此頁面](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses-for-the-entire-platform)。

如需服務訂閱的詳細資訊，請參閱[此頁面](../../audiences/using/about-subscriptions.md)。
