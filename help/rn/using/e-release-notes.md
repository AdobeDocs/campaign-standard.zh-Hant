---
title: 早期發行說明
description: 早期發行說明
feature: Overview
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: 66aed3668dc0eb2041312dcbaebe7c36f54b13a5
workflow-type: ht
source-wordcount: '0'
ht-degree: 100%

---

# 早期發行說明 {#new-release}

本頁說明下一版 Campaign Standard 中包含的新功能、改善和修正。

>[!CAUTION]
>
> 在預備環境升級日期前，此內容可能會有所變更，恕不另行通知。 請參閱[發行計劃頁面](../../rn/using/release-planning.md)以瞭解更多資訊。

## 發行版本 22.2 – 2022 年 6 月 {#rn-2022}

**功能改進**

* **Adobe Notification Service** - Adobe Notification Service 促銷活動，允許 Experience Cloud 解決方案提醒 Experience Cloud 的使用者注意對他們來說很重要的活動。從 22.2 版開始，改善使用者體驗：依照優先順序通知，產品產生的通知與 Adobe 狀態公告分開。 此外，當特定的工作流程通知時，您可以直接從電子郵件或產品通知存取對應的工作流程。  如需 Adobe Campaign 通知的詳細資訊，請參閱 [Adobe Campaign 通知](../../administration/using/sending-internal-notifications.md)。

* **啟動最佳化工作流程** - Adobe 新增了一項新功能，可以調整同時啟動的工作流程數量。 這將有助於防止可能導致服務中斷或停止工作的 CPU 峰值。 Adobe 將在 22.2 之後的版本啟用。 沒有關於客戶對於相同問題的進一步動作項目。

* **協助工具** - Adobe 為提高應用程式的整體易用性修復了許多協助工具。 這些功能目前僅對一部分早期採用者啟用，並將在 ACS 22.3 版本首次向所有客戶提供。 協助工具的功能改善範例包括：

   * 確保每個螢幕上的聚焦元件都有可見的聚焦指示器
   * 建立頁面地標讓導覽更輕鬆
   * 新增許多控制項名稱、角色、值和狀態
   * 修復主螢幕動態焦點順序所遇到的問題


**修補程式**

* 已修復由於重複金鑰錯誤而造成的帳單技術工作流程問題。 (CAMP-51029)
* 已在追蹤報告中新增缺少的 Microsoft Edge 瀏覽器類別。 之前是透過 Microsoft Chrome opens 進行分類的。(CAMP-51165)
* 針對 GDPR 的要求，修復未從子表格中刪除資料的問題。 (CAMP-48276)
* 修復電子郵件設計工具的問題，其中會使異動訊息範本無法儲存片段的可見度狀況。 (CAMP-50338)
* 已修復 Campaign 報告未考慮日期範圍的問題。 (CAMP-50991)
* 已修復造成排程電子郵件失敗的錯誤：因傳遞仍處於「重試擱置」狀態而無法開始傳遞分析。 (CAMP-50302)
* 針對當預覽包含設定檔替代的電子郵件時，修復電子郵件設計工具所發生的問題。(CAMP-49312)
* 修復自訂分項清單的空值問題：當使用文字分項清單且只包含一個值的欄位建立自訂資源時，在預設情況下會設定此值，以便您可以在此欄位上簡單請求建立查詢。 (CAMP-50606)
