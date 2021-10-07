---
title: 追蹤的 URL 簽名問題
description: 追蹤的 URL 簽名問題
hidefromtoc: true
hide: true
exl-id: 8c2725a8-2c3a-448a-8c04-c0c2a5950574
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: ht
source-wordcount: '199'
ht-degree: 100%

---

# 追蹤的 URL 簽名問題 {#tracked-urls}

在最近變更後，Campaign 傳送的追蹤 URL 可能會失敗。 有些信件匣受到的影響比其他信件匣大，因為有些公司有特定的安全工具，這些工具可能會影響連結並替代 URL 簽名機制。

因此，Adobe 決定停用追蹤連結的簽名機制。 此程式會修正所有追蹤連結。

請注意，取消訂閱的連結可能會像其他連結一樣失效，頻率根據每台主機而定，但機率小於 1%。

**您有受到影響嗎？**

有些 Campaign Standard 使用者會受到影響，因為 [Campaign Standard 20.4](release-notes-2020.md#release-20-4---october-2020) - 2020 年 10 月中已引進追蹤電子郵件連結的簽名機制，並依預設為所有客戶啟用。

**如何更新？**

Adobe 將與您合作，盡快更新您的設定。 您將會收到電子郵件通知，說明升級時程安排。

**會有什麼影響？**

維護作業最長需要 25 分鐘的停機時間，在此期間，所有傳送、追蹤連結和 API 呼叫都無法運作。

更新完成後，所有連結都會如預期恢復運作。

>[!NOTE]
>
>如對這些變更有任何疑問，請聯絡 [Adobe 客戶服務](https://helpx.adobe.com/tw/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html)。
