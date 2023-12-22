---
title: 早期發行說明
description: 早期發行說明
feature: Overview
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: 602aca18af81625b9756a8f2020b5bc636199b96
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 68%

---


# 早期發行說明 {#e-new-release}

本頁介紹了下一個 Campaign Standard 版本中包含的改善及修正。

>[!CAUTION]
>
> 在預備環境升級日期前，此內容可能會有所變更，恕不另行通知。 請參閱[發行計劃頁面](../../rn/using/release-planning.md)以瞭解更多資訊。

## 版本 24.1 - 2024 年冬季發布內容 {#winter-24}

>[!AVAILABILITY]
>
>此版本僅適用於一組組織 (可用性限制)。 如需詳細資訊，請聯絡您的 Adobe 代表。

### 功能改進 {#e-rn-improvements}

Adobe Campaign Standard 24.1使用HTTP v1 API傳送Android推播通知訊息，以確保與即將推出的FCM變更相容。 若要了解詳細資訊，請參閱[此技術說明](../../administration/using/push-technote.md)。


### 修正 {#e-rn-fixes}

* 修正傳送警報工作流程因下列錯誤而停止的問題： `division by zero`. (CAMP-49786)
