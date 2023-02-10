---
title: 在 ISP 中斷後更新跳出資格
description: 了解如何在ISP中斷後更新退信資格。
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

如果ISP中斷，透過Campaign傳送的電子郵件無法成功傳送給其收件者：這些電子郵件會錯誤標示為退信。

2020年12月，Gmail的全球問題導致傳送至有效Gmail電子郵件地址的部分電子郵件訊息錯誤地硬退信，因為Gmail伺服器所提供的無效電子郵件地址，並回信如下： *&quot;550-5.1.1您嘗試訪問的電子郵件帳戶不存在。&quot;*

Google表示，造成此問題的Gmail中斷和中斷始於12月14日早上6:55，並於12月15日東部時間下午6:09結束。 我們的資料分析還顯示，美國東部標準時間12月16日凌晨2:06,Gmail彈回數出現非常短的尖峰，其中大部分發生在美國東部標準時間下午2:00至6:30之間的12月15日。

>[!NOTE]
>
>您可以在「Google工作區狀態控制面板」上查看 [本頁](https://www.google.com/appsstatus#hl=en&amp;v=status).


根據標準退信處理邏輯，Adobe Campaign會使用 **[!UICONTROL Status]** 設定 **[!UICONTROL Quarantine]**. 若要修正此問題，您需要尋找和移除這些收件者，或變更其，以更新Campaign中的隔離表格 **[!UICONTROL Status]** to **[!UICONTROL Valid]** 以便夜間清理工作流程將其移除。

若要尋找受此Gmail問題影響的收件者，或若此情況再次發生於其他ISP，請參閱下列指示。

## 更新流程

您需要在隔離表格上執行查詢，以篩選掉所有可能受到中斷影響的Gmail（或其他ISP）收件者，以便從隔離清單中移除這些收件者，並納入未來的Campaign電子郵件傳送中。

根據事件的時間範圍，以下是此查詢的建議准則。

>[!IMPORTANT]
>
>這些日期/時間以東部標準時區(EST)為基礎。 請根據您執行個體的時區進行調整。

若是具有SMTP退信回應資訊的促銷活動例項，請參閱 **[!UICONTROL Error text]** 隔離清單欄位：

* **錯誤文本（隔離文本）** 包含「550-5.1.1您嘗試觸及的電子郵件帳戶不存在」和 **錯誤文本（隔離文本）** 包含&quot;support.google.com&quot; **
* **更新狀態(@lastModified)** 12/14/2020 6:55:00 AM
* **更新狀態(@lastModified)** 12/16/2020 6:00:00 AM

取得受影響收件者的清單後，您就可以將其設為 **[!UICONTROL Valid]** 以便將其從隔離清單中由 **[!UICONTROL Database cleanup]** 工作流程，或只是從表格中刪除。

**相關主題：**
* [了解傳送失敗](../../sending/using/understanding-delivery-failures.md)
* [退回郵件資格](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification)
