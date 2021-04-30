---
solution: Campaign Standard
product: campaign
title: 追蹤的URL簽名問題
description: 追蹤的URL簽名問題
translation-type: tm+mt
source-git-commit: 830c003e36cec41e5cf480f66812900312609e9f
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 3%

---


# 追蹤的URL簽名問題{#tracked-urls}

在最近變更後，「促銷活動」傳送的追蹤URL可能會失敗。 有些郵箱受到的影響比其他郵箱大，因為有些公司有特定的安全工具，這些工具可能會影響連結並更改URL簽名機制。

因此，Adobe決定停用追蹤連結的簽名機制。 此程式會修正所有追蹤連結。

請注意，取消訂閱連結可能會像其他連結一樣失敗，頻率是從主機到主機的變數，但小於1%。

**您受影響嗎？**

有些Campaign Standard使用者會受到影響，因為[Campaign Standard20.4](release-notes-2020.md#release-20-4---october-2020) - 2020年10月中已引入追蹤電子郵件連結的簽名機制，並依預設為所有客戶啟用。

**如何更新？**

Adobe將與您合作，不久將更新您的配置。 您將會收到電子郵件通知，通知您的升級時間表。

**影響是什麼？**

維護作業最長需要25分鐘的停機時間，在此期間，所有傳送、追蹤連結和API呼叫都無法運作。

更新完成後，所有連結都會如預期般運作。

>[!NOTE]
>
>如對這些變更有任何疑問，請聯絡[Adobe客戶服務](https://helpx.adobe.com/tw/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html)。

