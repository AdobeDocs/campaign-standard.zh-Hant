---
title: 關於 Campaign 中的選擇加入和選擇退出
description: 選擇退出導致配置檔案不再被任何遞送或特定渠道遞送瞄準。
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

選擇退出導致配置檔案不再被任何遞送或特定渠道遞送瞄準。

要使配置檔案能夠選擇加入或選擇退出，您必須建立專用登錄頁。 有關此內容的詳細資訊，請參閱 [設定選擇加入和選擇退出登錄頁](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#setting-up-opt-in-and-opt-out-landing-pages)。

操作員也可以手動選擇配置式進出。 有關此內容的詳細資訊，請參閱 [管理配置檔案中的選擇加入和選擇退出](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#managing-opt-in-and-opt-out-from-a-profile)。

在交貨分析期間自動排除選擇退貨配置檔案以加快交貨速度（錯誤率對交貨速度有顯著影響）。

>[!NOTE]
>
>退出適用於 **配置檔案**，而不是連結到 **電子郵件地址** 或 **電話號碼**。 因此，選擇配置檔案將排除與其連結的所有地址。 但是，如果用戶在資料庫中有兩個配置檔案，則此用戶仍會被遞送鎖定，因為只有一個配置檔案被排除。 要確保排除其所有地址，請將其添加到隔離地址。 如需詳細資訊，請參閱[此頁面](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses-for-the-entire-platform)。

有關服務訂閱的詳細資訊，請參閱 [此頁](../../audiences/using/about-subscriptions.md)。
