---
title: 早期發行說明
description: 早期發行說明
feature: Overview
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: 25e842d2b012a07b3f1ef1ff5490a6b4afa0e887
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 27%

---


# 早期發行說明 {#e-new-release}

本頁介紹了下一個 Campaign Standard 版本中包含的改善及修正。
>[!CAUTION]
>
> 在預備環境升級日期前，此內容可能會有所變更，恕不另行通知。 請參閱[發行計劃頁面](../../rn/using/release-planning.md)以瞭解更多資訊。

## 版本 23.1 - 2023 春/夏版 {#apr-23}

### 功能改進 {#e-rn-improvements}

* 推播訊息服務已經過現代化，以最佳化維護。 (CAMP-47959)
* SMS訊息服務已經過現代化，以提供改善的穩定性。 (CAMP-52217)
* 現成可用 **報表擴充建立工作流程** 已新增。 從一個例項匯入目標對應至另一個例項後，只要執行工作流程以匯入對應的報表擴充項目。 (CAMP-52452)

### 修補程式{#e-rn-patches}

* 修正顯示 **熱點按** 報表。 (CAMP-51582)
* 修正了無法將整合用於 **位置** 服務。 (CAMP-51923)
* 修正了工作流程排程器無法正常運作的問題。 (CAMP-52003)
* 修正檢視含有大量資料之自訂動態報表的PDF版本時，無法顯示劃分詳細資料的問題。 (CAMP-52178)
* 修正了存取報告時可能顯示錯誤的問題。 (CAMP-52500)
* 修正套用錯誤 **限制此帳戶的MTA例項** SMS連接器參數至所有通道，而非僅套用至SMS。 (CAMP-52640)
