---
title: 早期發行說明
description: 早期發行說明
feature: Overview
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: 46c5454ad712910c88bfda7c067fda0337b043d9
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 83%

---


# 早期發行說明 {#e-new-release}

本頁介紹了下一個 Campaign Standard 版本中包含的改善及修正。

>[!CAUTION]
>
> 在預備環境升級日期前，此內容可能會有所變更，恕不另行通知。 請參閱[發行計劃頁面](../../rn/using/release-planning.md)以瞭解更多資訊。

## 版本 23.2 - 2023 年秋冬發布內容 {#fall-23}

>[!AVAILABILITY]
>
>此版本僅適用於一組組織 (可用性限制)。 如需詳細資訊，請聯絡您的 Adobe 代表。

### 功能改進 {#e-rn-improvements}

* **集成 Adobe Experience Manager**。在 Adobe Experience Manager 中建立交易型訊息的個人化傳遞範本時，您現在可以選取並使用下拉式清單中 Campaign Standard 定義的個人化欄位。

* **Cookie 有效期** — 預設 Cookie 有效期限現已設定為 6 個月，以符合法國資料保護局 (CNIL) 的建議。

* **設定檔搜尋改進** — 已最佳化設定檔搜尋，以便減少搜尋逾時情況

* **本地化** — 指稱一組設定檔以接收訊息時，「對象」一詞的翻譯在下列語言的所有數位體驗產品中得到協調：

   * 德文：Zielgruppe
   * 巴西葡萄牙文：público-alvo
   * 西班牙文：público destinatario

  這些變更將在下一個 UI 和文件版本中逐步推出。

### 其他變更 {#e-rn-other-changes}

* 異動訊息現在支援使用多個以逗號分隔的親和度。

### 修正 {#e-rn-fixes}

* 修正了在使用大型工作流程時，可能導致效能問題的回歸。 (CAMP-53369)
* 修正工作流程警報或通知中的電子郵件連結無法運作的問題。 (CAMP-51874)
