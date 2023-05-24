---
title: 在 ISP 中斷後更新跳出資格
description: 瞭解如何在ISP停機後更新退貨資格。
audience: delivery
hidefromtoc: true
exl-id: b06e9009-70c7-459f-8a9f-d5b7020d662f
source-git-commit: f81b8a3b076a6e29b697f21ea4d99fa7d5b6788c
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 4%

---

# 在 ISP 中斷後更新跳出資格 {#update-bounce-qualification.md}

## 內容

在ISP中斷時，無法將通過Campaign發送的電子郵件成功發送給其收件人：這些電子郵件會被錯誤地標籤為回報。

2020年12月，Gmail出現全球性問題，導致一些發送到有效Gmail電子郵件地址的電子郵件被錯誤地硬彈回，因為Gmail伺服器的無效電子郵件地址出現以下反彈： *&quot;550-5.1.1您嘗試訪問的電子郵件帳戶不存在。&quot;*

Google表示，導致此問題的Gmail中斷和中斷始於12月14日早6:55，截止於12月15日東部時間下午6:09 我們的資料分析還顯示，Gmail在東部時間12月16日凌晨2點06分出現了短暫的激增，其中大部分發生在東部時間12月15日下午2點至6點30分之間。

>[!NOTE]
>
>可以在上檢查Google工作區狀態儀表板 [此頁](https://www.google.com/appsstatus#hl=en&amp;v=status)。


根據標準彈出處理邏輯，Adobe Campaign自動將這些收件人添加到隔離清單中， **[!UICONTROL Status]** 設定 **[!UICONTROL Quarantine]**。 要更正此問題，您需要通過查找和刪除這些收件人或更改其來更新市場活動中的隔離表 **[!UICONTROL Status]** 至 **[!UICONTROL Valid]** 這樣夜間清理工作流就會刪除它們。

要查找受此Gmail問題影響的收件人，或在其他ISP再次出現此情況時，請參閱以下說明。

## 要更新的進程

您需要在隔離表上運行查詢，以過濾掉所有可能受中斷影響的Gmail（或其他ISP）收件人，以便從隔離清單中刪除這些收件人，並將其包括在將來的市場活動電子郵件中。

根據事件的時間範圍，以下是此查詢的建議准則。

>[!IMPORTANT]
>
>這些日期/時間基於東部標準時區(EST)。 請根據實例的時區進行調整。

對於具有SMTP彈出響應資訊的市場活動實例 **[!UICONTROL Error text]** 隔離清單的欄位：

* **錯誤文本（隔離文本）** 包含「550-5.1.1您嘗試訪問的電子郵件帳戶不存在」AND **錯誤文本（隔離文本）** 包含&quot;support.google.com&quot;**
* **更新狀態(@lastModified)** 12/14/2020 6後:55:上午00點
* **更新狀態(@lastModified)** 在12/16/2020 6之前:00:上午00點

一旦您擁有受影響的收件人清單，您就可以將其設定為 **[!UICONTROL Valid]** 這樣它們就會被 **[!UICONTROL Database cleanup]** 工作流，或者只是從表中刪除它們。

**相關主題：**
* [瞭解交付失敗](../../sending/using/understanding-delivery-failures.md)
* [退回郵件資格](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification)
