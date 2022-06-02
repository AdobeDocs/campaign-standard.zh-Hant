---
title: 早期發行說明
description: 早期發行說明
feature: Overview
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: 75bc042701ac29d2e525884dc929063147c1cdce
workflow-type: tm+mt
source-wordcount: '383'
ht-degree: 37%

---

# 早期發行說明 {#new-release}

本頁說明下一版 Campaign Standard 中包含的新功能、改善和修正。

>[!CAUTION]
>
> 在預備環境升級日期前，此內容可能會有所變更，恕不另行通知。 請參閱[發行計劃頁面](../../rn/using/release-planning.md)以瞭解更多資訊。

## 發行版本 22.2 – 2022 年 6 月 {#rn-2022}

**改進**

* **Adobe Notification Service** - Adobe Notification Service 促銷活動，允許 Experience Cloud 解決方案提醒 Experience Cloud 的使用者注意對他們來說很重要的活動。從 22.2 版開始，改善使用者體驗：依照優先順序通知，產品產生的通知與 Adobe 狀態公告分開。 此外，當特定的工作流程通知時，您可以直接從電子郵件或產品通知存取對應的工作流程。  如需 Adobe Campaign 通知的詳細資訊，請參閱 [Adobe Campaign 通知](../../administration/using/sending-internal-notifications.md)。

* **工作流啟動中的優化** -Adobe添加了一項新功能，可以調整同時啟動的工作流數。 這將有助於防止可能導致服務中斷或停機的CPU尖峰。 Adobe將在22.2版後啟用它。 客戶沒有關於此問題的其他措施項。

**安全性升級**

* Apache Tomcat已從7版升級到8.5版。

**修補程式**

* 已修復由於重複密鑰錯誤而導致的開單技術工作流問題。 (CAMP-51029)
* 已在跟蹤報告中添加缺少的Microsoft邊緣瀏覽器類別。 之前，他們被歸為MicrosoftChrome開張。 (CAMP-51165)
* 修復了未從子表中刪除資料的GDPR請求的問題。 (CAMP-48276)
* 已修復電子郵件設計器中導致事務性消息模板中不保存片段的可見性條件的問題。 (CAMP-50338)
* 已修復「市場活動報表」中導致日期範圍未被考慮的問題。 (CAMP-50991)
* 修復了導致計畫電子郵件失敗的錯誤：無法啟動傳遞分析，因為傳遞仍處於「重試掛起」狀態。 (CAMP-50302)
* 在使用配置檔案替代預覽電子郵件時，已修復電子郵件設計器中的問題。 (CAMP-49312)
* 已修復自定義枚舉中值為空的問題：當使用文本枚舉且只包含一個值的欄位建立自定義資源時，預設情況下現在會設定此值，以便您可以以簡單請求的形式在此欄位上建立查詢。 (CAMP-50606)
